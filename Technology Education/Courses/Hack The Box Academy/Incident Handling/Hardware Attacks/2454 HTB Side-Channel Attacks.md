# Side-Channel Attacks

Cryptanalysis Side-Channel Attacks refer to the exploitation of data leaked during cryptographic algorithm execution. Flaws in algorithm math are discovered and then physically attacked to leverage information like timing data, power usage, electromagnetic emissions, and acoustic signals. Collecting this data can lead to attackers working around established algorithms.

There are two types of Side-Channel attacks:

- Passive - attackers monitor the system without interacting. Data leaks like power consumption, timing, and electromagnetic emissions are part of normal system operations. 
- Active - deliberate interaction from the attacker to provoke changes in the normal system operations by manipulating power supplies or introducing new inputs to observe output.

### Timing Attacks

Timing attacks use input methods to observe the amount of time it takes to process these inputs. The computational time is measured to make educated guesses about the secret key based on encryption times. This is an exploitation and observance of the different time durations required to execute inputs on a target. 

A simple way of explaining this is to determine if the target takes different time to process a '1' than a '0', which would allow them to interpret and decrypt data on the target.

This was demonstrated in 1996 by Paul Kocher using SSL web servers where he inferred the data of a private key bit by bit. 

Mitigating these attacks can be done with constant-time algorithms that ensure 0's and 1's are processed with the same duration so that a correlation cannot be observed.

### Power-Monitoring

Power-Monitoring or Power-Analysis attacks are exploitations of the power consumption of a device when it is processing sensitive information. Observation of power levels during cryptographic processes paired with statistical analysis reveal the secret keys as they are processed. 

There are two types of Power-Monitoring attacks:

- Simple Power Analysis ( #SPA) - attacker observes and interprets power consumption and looks for spikes in power usage to determine the occurrence of cryptographic analysis.

- Differential Power Analysis ( #DPA) - a more involved style of attack where power consumption data for various processes is collected and bit value is associated with the rate of consumption.

Power-Analysis attacks were demonstrated in 1999 by Paul Kocher, Joshua Jaffe, and Benjamin Jun where they extracted a secret key from a smart card.

Mitigating these attacks is a complicated process that involved management of software and hardware. Power regulation and randomization must be employed on the hardware to obfuscate power usage. 

### Acoustic Cryptanalysis

Acoustic Cryptanalysis analyzes sound emissions from a device in order to extract data from it. These acoustic signals correlate to internal processes of the device. This is the sounds of fans, CPU, and internal components that engage and disengage during use of the device. 

Acoustic analysis of keyboard strokes and determine what people are typing as different keys make different recognizable sounds. These sounds can be recorded and interpreted to act as a form of remote keylogger.

In 2014, Daniel Genkin, Adi Shamir, and Eran Tromer demonstrated acoustic cryptanalysis techniques where they showed that a CPU would emit specific sounds during cryptographic processes.

Georgi Gerganov demonstrated keyboard acoustic analysis, also known as KeyTap. This was published to his GitHub where he recorded keyboard sounds on a mechanical keyboard and successfully interpreted keystrokes.

Mitigating Acoustic Cryptanalysis requires configuration of both hardware and software. Sound deadening materials can be incorporated into devices to reduce the noise they produce. Software can be configured to introduce randomized noises and actions.

