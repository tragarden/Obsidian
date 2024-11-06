# Microprocessors

Microprocessors are integrated circuits ( #IC) that encapsulate central processing unit ( #CPU) functions within a single chip. A microprocessor is a type of CPU, but not all CPUs are microprocessors. Powerful CPUs may use many ICs, while a PC CPU will typically use a single IC.

Microprocessors can contain vulnerabilities that allow threat actors to gain and execute unauthorized actions on a target. These vulnerabilities might be accidental, but occasionally an intentionally included backdoor might become accessible to attackers.

Microprocessor architecture involves several components:

- Control Unit ( #CU) - part of a CPU that dictates operation of the processor. It determines how memory usage, logic units, and output devices will respond to processor commands.

- Arithmetic Logic Unit ( #ALU) - the computational instrument of the CPU that performs arithmetic and logical operations.

- Instruction Set Architecture ( #ISA) - an abstracted model of a computer that defines data types, register sets, memory addressing, and machine language commands executable by the computer.

- Transistors - electricity switches that toggle between on an off to indicate the different binary states of 1 and 0. Transistors store and manipulate binary data during the fetch-decode-execute cycle.

	- The control unit interprets combinations of binary values to initialized and execute command and interpret data.

	- The arithmetic logic unit interacts with transistors based on interpreted instructions from the control unit to perform it's arithmetic processes. 

	- The more transistors available, the more processing power available, which means increased processing speed and performance.

### Design

Microprocessor design involved multiple design stages that can each have their own unique vulnerabilities. Any of the following parts of the design process may introduce vulnerabilities.

#### Architecture

Architecture defines the instruction set architecture ( #ISA) and this stage has great impact on performance, power use, and cost. There are two common types of architecture:

- Complex Instruction Set Architecture ( #CISA) offers many general tools. This has a lot of influence over what the processor is capable of.

- Reduced Instruction Set Architecture ( #RISA) offers a single specialized tool. This is a low impact implementation for specific purposes.

#### Logic

Logic design refers to how the architecture is translated into logical operations via Boolean algebra and digital logic. These principles are used to create a schematic known as a logic gate. During this process, a data path is created to perform logical operations and control units are used to manage the flow of data. This results in a register-transfer level ( #RTL) that functions as a blueprint for circuitry. 

### Circuits

Circuits convert the register-transfer level blueprint into electronic circuits. Each logic gate will be assigned transistors, resistors, and capacitors to accomodate their function. This process is intended for optimization of speed, amount of silicon, and power consumption. An AND gate is commonly implemented with two transistors in series.

#### Physical

Physical design relates to the layout of silicon and components on a produced chip. In this phase, component placement is determined and electrical pathing is routed. Reliability and performance of the chip is ultimately determined by it's ability to dissipate heat and distribute power, which is dependent on the physical layout of the chip.

#### Verification

Verification design ensures that the chip functions properly via static timing analysis that evaluates logic functions to verify that they occur within the defined clock cycle times. This is a development phase that identifies and mitigate issues prior to production.

### Optimization

Optimization refers to methods used to improve performance and efficiency. The main goals are improving speed while reducing power consumption. Execution and data transfer directly benefit from optimization of microprocessors.

#### Pipelining

Pipelining refers to the improvement of execution throughput by breaking the execution into smaller steps that can be simultaneously executed. This happens in a sequential way - typically in the order of instruction fetching, instruction decoding, execution, memory access, and then write back. This optimized the usage of processor resources.

#### Speculative Execution

Speculative Execution refers to improving processing speed with the help of educated guessing about program direction and conditional branching. Before a correct path is known, the processor predicts the most likely path and execution conditions in order to prepare for execution, which hopefully saves processing time. This requires a rollback mechanism however, in the case that the prediction made by the processor is incorrect. This will discard the prediction and revert to a pre-speculation state.

#### Caching

Caching is used to increase the speed at which data is retreived using small memory units between the CPU and memory. These fast acting memory units store recently or frequently accessed data.

Caches are organized in a level hierarchy indicated by L1, L2, and L3. L1 is the fastest and smallest cache, which is directly accessible by the CPU. The subsequent levels are slower and larger. 

While caching increases processor performance, it introduces security vulnerabilities like side-channel attacks based on timing differences in cache access.