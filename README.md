# INSE6120-Winter2024-Project-Group6
Tools 

SiGploit
SiGploit a signaling security testing framework dedicated to Telecom Security professionals and researchers to pentest and exploit vulnerabilities in the signaling protocols used in mobile operators regardless of the generation being in use. SiGploit aims to cover all used protocols used in the operators interconnects SS7, GTP (3G), Diameter (4G) or even SIP for IMS and VoLTE infrastructures used in the access layer and SS7 message encapsulation into SIP-T. Recommendations for each vulnerability will be provided to guide the tester and the operator the steps that should be done to enhance their security posture.
SiGploit is developed on several versions.
Note: In order to test SS7 attacks, you need to have an SS7 access, or you can test in the virtual lab with the provided server sides of the attacks, the used values are provided.
Version 1: SS7
SiGploit will initially start with SS7 vulnerabilities providing the messages used to test the below attacking scenarios A- Location Tracking B- Call and SMS Interception C- Fraud
Version 2: GTP
This Version will focus on the data roaming attacks that occur on the IPX/GRX interconnects.
Version 3: Diameter
This Version will focus on the attacks occurring on the LTE roaming interconnects using Diameter as the signaling protocol.
Version 4: SIP
This is Version will be concerned with SIP as the signaling protocol used in the access layer for voice over LTE(VoLTE) and IMS infrastructure. Also, SIP will be used to encapsulate SS7 messages (ISUP) to be relayed over VoIP providers to SS7 networks taking advantage of SIP-T protocol, a protocol extension for SIP to provide intercompatability between VoIP and SS7 networks.
Version 5: Reporting
This last Version will introduce the reporting feature. A comprehensive report with the tests done along with the recommendations provided for each vulnerability that has been exploited.
BETA Version of SiGploit will have the Location Tracking attacks of the SS7 phase 1
Installation and requirements
The requirements for this project are:
1) Python 2.7
2) Java version 1.7 +
3) Linux machine (Windows doesn’t support SCTP)
To run use
cd SigPloit

python sigploit.py

Installation and requirements

Frist, we cloned it onto our system.

Using git clone https://github.com/sigploiter/sigploit.git
Cd sigploit
Pip3 install -r requirements.txt
chmod +x sigploit.py

Problems

We are using Python 3 so we updated the whole code to be compatible with python 3

python sigploit.py




since we don’t have the hardware, we will simulate the hardware using jss7-attack-simulator, which is based on RestComm's jss7 framework. This simulator is implemented in Java and can be used to demonstrate various publicly disclosed attacks on the SS7 network.


Jss7 -attack-simulator.
I did a [quick search](https://chat.openai.com/backend-api/bing/redirect?query=simulate%20SS7%20attack%20without%20hardware) for more information and here's what I discovered.

Yes, you can simulate an SS7 attack without using specialized hardware. There are software-based simulators available that can simulate SS7 attacks. One such tool is the `jss7-attack-simulator`, which is based on RestComm's jss7 framework. This simulator is implemented in Java and can be used to demonstrate various publicly disclosed attacks on the SS7 network.

The `jss7-attack-simulator` supports two primary modes:
- A simple mode for demonstrating specific SS7 attacks.
- A more complex mode that allows for a more detailed simulation of SS7 attacks.

This simulator is open source and available on GitHub, making it accessible for educational and research purposes. Using such a simulator can be valuable for understanding the vulnerabilities and potential impact of attacks on the SS7 network, which is a critical component of global telecommunications infrastructure.

To use the simulator, you would typically need a working Java environment and some familiarity with SS7 network principles and Java programming. It's important to note that simulating network attacks should be done responsibly and ethically, ideally in a controlled environment for learning or testing purposes only.

For more detailed information and access to the simulator, you can visit the repositories on GitHub:
- [jss7-attack-simulator by denklewer](https://github.com/denklewer/jss7-attack-simulator)
- [jss7-attack-simulator by polarking](https://github.com/polarking/jss7-attack-simulator)

Remember to adhere to ethical guidelines and legal requirements when using such tools.


SS7 Attack Simulator based on RestComm's jss7.
Introduction
This project is currenlty not maintained and may not build, I've made available the latest build here.
Open Source Java SS7 attack simulator that makes it possible to simulate some publicly disclosed attacks on the SS7 network.
This project is part of an ongoing Master Thesis at NTNU Gjøvik, Norway.
The simulator supports two modes:
•	Simple mode: Used to demonstrate some SS7 attacks.
•	Complex mode: Includes a full network simulation containing 3 operators, where one of the subscribers is the victim of attacks by an adversary with access to the SS7 network. In this mode several nodes communicate using 13 standard procedures per the 3GPP MAP standard. After a mercy period, there will be launched attacks against the subscriber with the goal of obtaining the subscribers location and intercept SMS originally sent to this subscriber.
Traffic is generated using the SCTP protocol and all data is sent on the lo interface.
License
SS7 Attack Simulator is licensed under the Free Open Source GNU Affero GPL v3.0.
Downloads
The latest build can be downloaded from here.
Instructions
How to run the simulator:
•	The simulator needs a working Java environment.
•	Make sure you have SCTP support installed on Linux:
o	Fedora: lksctp-tools and kernel-modules-extra.
o	Ubuntu: libsctp1 and lksctp-tools.
•	Download latest build here.
•	Unzip the file.
•	The simulator is launched with the script:
RELEASE_FOLDER/ss7/restcomm-ss7-simulator/bin/run.sh
•	Run
run.sh help 
or
run.sh attack_simulator help 
for help on how to run the simulator.
The currently supported simple attacks are:
•	location:ati
•	location:psi
•	intercept:sms
Build From Source
Building from source can be done by using the instructions for jSS7, which can be found here



Running on Kali

If you're looking to set up an SS7 attack simulator based on RestComm's jSS7 stack on Kali Linux, you're delving into a more specialized and technical aspect of network security and simulation. RestComm's jSS7 is an open-source Java-based implementation of SS7 stack components, providing a robust framework for developing SS7 applications and services. This can be used for educational, testing, and development purposes to simulate SS7 network scenarios, including potential vulnerabilities and attacks within a controlled environment.

Here's a general outline of steps you might follow to set up an SS7 attack simulator using RestComm's jSS7 on Kali Linux. Remember, these activities should only be conducted within a legal and ethical framework, such as a lab setup for security research or educational purposes, with all necessary permissions obtained.

### Preparing the Environment

1. **Install Java Development Kit (JDK)**: jSS7 requires Java, so ensure you have the JDK installed on your Kali Linux. You can install it via apt-get or another package manager.
   
   ```bash
   sudo apt update
   sudo apt install default-jdk
   ```

2. **Verify Java Installation**: Ensure Java is correctly installed by checking the version.
   
   ```bash
   java -version
   ```

3. **Download RestComm jSS7**: Clone the jSS7 repository from GitHub to get the latest version of the stack.
   
   ```bash
   git clone https://github.com/RestComm/jss7.git
   ```

### Setting Up jSS7

4. **Navigate to the jSS7 Directory**: Change into the cloned repository's directory.
   
   ```bash
   cd jss7
   ```

5. **Build jSS7**: Use Maven to build jSS7. If you don't have Maven installed, you will need to install it first.
   
   ```bash
   sudo apt install maven
   mvn clean install
   ```

   This process may take some time as it compiles the source code and builds the necessary components.

### Configuring the SS7 Simulator

6. **Configuration**: You'll need to configure the stack for simulation. This involves setting up the SS7 layer configurations, such as Point Codes, Network Indicators, Service Indicators, and routing configurations. These settings are found in the configuration files within the jSS7 stack. You may need to refer to the jSS7 documentation for detailed configuration instructions.

7. **Running the Simulator**: With everything set up and configured, you can start the SS7 simulator. This typically involves running a Java application that uses the jSS7 stack. You might need to create or modify a Java class that initiates the stack and starts the simulation, based on your specific testing or development requirements.

### Legal and Ethical Considerations

- Consent and Permission: Make sure that you have all necessary permissions and are compliant with laws and ethical guidelines when setting up and using an SS7 simulator.

- Security and Privacy: Be mindful of the potential impact on privacy and security. The knowledge gained should be used to enhance security measures and protect against vulnerabilities.

### Advanced Usage

As you become more familiar with the jSS7 stack and SS7 network simulations, you may explore more advanced scenarios, including developing custom SS7 applications, testing network defenses against SS7 vulnerabilities, or contributing to the jSS7 project with improvements or bug fixes.

Remember, the goal of such a setup should be to further understanding of SS7 security, develop protective measures, and contribute to the security community's knowledge.

### Configuring the SS7 Simulator ###
Configuring the SS7 layer for simulation with tools like SigPloit involves setting parameters that define how your simulation interacts with the SS7 network components. This configuration is crucial for accurately simulating the behavior of SS7 messages and protocols. While SigPloit provides an environment to exploit vulnerabilities within the SS7 network for educational and testing purposes, configuring the underlying SS7 stack (like RestComm's jSS7) requires an understanding of SS7 network architecture and parameters.

### Basic Concepts for SS7 Configuration:

- Point Codes (PCs): Unique addresses within the SS7 network used to identify network elements.
- Network Indicators (NIs): Indicate the type of network (e.g., national, international) the message is intended for.
- Service Indicators (SIs): Define the type of service or part of the SS7 network a message should be routed to (e.g., ISUP for call setup, SCCP for more complex routing).
- Routing Configurations: Define how messages are routed between different components in the SS7 network.

### Steps to Configure SS7 Layer in jSS7 for Simulation:

1. Download and Setup jSS7:
   Ensure you have jSS7 and its dependencies set up as discussed earlier. This might involve cloning the jSS7 repository and building it with Maven.

2. Identify Configuration Files:
   jSS7 configuration files are usually XML or property files located in the project's `resources` or a specific configuration directory. Look for files named similarly to `ss7-config.xml`, `m3ua-config.xml`, or `sctp-config.xml`.

3. **Edit Configuration Files**:
   Open the configuration files in a text editor to set up your simulation parameters. Here's what you might need to configure:
	Point Codes of the local and remote nodes.
	Network Indicators to specify the type of SS7 network.
	Service Indicators for routing to the correct SS7 service.
	DPC (Destination Point Code), OPC (Originating Point Code), and SSN (Sub-System Number) values for message routing.

4. **Configure SCTP** (Stream Control Transmission Protocol):
   - SCTP is used as a transport layer for SS7 over IP (SIGTRAN). Configure local and remote IP addresses and ports for SCTP associations.

5. **Configure M3UA** (MTP3 User Adaptation Layer):
   - M3UA enables SS7 MTP3 layer services over IP networks. Configure the ASP (Application Server Process) and AS (Application Server) settings, including the routing context and traffic mode type.

6. **Configure Higher Layers**:
   Depending on your simulation needs, configure higher layers like SCCP, TCAP, MAP, or ISUP with appropriate service indicators, addressing, and service configurations.

7. **Testing and Validation**:
   After configuring, test your setup using provided test scripts or by running your own simulations. Ensure messages are correctly routed and received as expected.

### Using SigPloit for SS7 Simulation:

If you're using SigPloit in conjunction with jSS7 for simulation, SigPloit will likely interface with the jSS7 stack you've configured. Ensure SigPloit points to the correct configuration files and that any specific SigPloit configurations align with your jSS7 setup.

- **SigPloit Configuration**: Review SigPloit's documentation or configuration files for specifics on how it interfaces with SS7 stacks and any additional settings required for simulation.

### Important Notes:

- **Legal and Ethical Considerations**: Always ensure your testing is legal, ethical, and authorized. Unauthorized use of SS7 capabilities can be illegal and harmful.
- **Documentation**: Refer to the jSS7 and SigPloit documentation for the most accurate and detailed configuration instructions.

This overview gives you a starting point for configuring the SS7 layer for simulation. Given the complexity of SS7 and variations in setups, you may need to adjust configurations based on your specific requirements and the documentation of the tools you're using.

Problem 
   
The error messages you're seeing indicate that the Java compiler version specified for the project is no longer supported. Specifically, the errors:

```
[ERROR] Source option 5 is no longer supported. Use 7 or later.
[ERROR] Target option 5 is no longer supported. Use 7 or later.
```

mean that the project is configured to use Java 5 (also known as 1.5), but the version of the Java Development Kit (JDK) you are using does not support compiling to Java 5. Modern versions of JDK require at least Java 7 or later for the source and target versions.

To resolve this issue, you need to update the Maven `pom.xml` file(s) of the jSS7 project to specify a newer Java version for both source and target compilation. Here's how you can do it:

1. **Locate the `pom.xml` File(s):** You'll need to find the `pom.xml` file for the `scheduler` module that is failing, as well as any parent `pom.xml` files that might specify the Java version for the project.

2. **Edit the `pom.xml` File(s):** Open the `pom.xml` file(s) in a text editor. Look for the `<properties>` section where the Java version is specified, typically with `maven.compiler.source` and `maven.compiler.target` properties.

3. **Update Java Version:** Change the values of `maven.compiler.source` and `maven.compiler.target` to a supported version, such as 7 or higher. For example, to set the project to use Java 8, you would make the following changes:

   ```xml
   <properties>
       ...
       <maven.compiler.source>1.8</maven.compiler.source>
       <maven.compiler.target>1.8</maven.compiler.target>
       ...
   </properties>
   ```

4. **Save the Changes:** After updating the `pom.xml` file(s), save your changes.

5. **Re-run Maven Build:** Go back to the terminal and re-run the Maven build command. If you were in the middle of a build process, you can resume it with the command provided by Maven in the error output, or simply start a new build:

   ```bash
   mvn clean install
   ```

This should resolve the compilation errors related to the unsupported Java version. If you encounter further issues, it may be necessary to adjust other parts of the project configuration or resolve additional dependencies compatible with the newer Java version you've selected.


Sloved

Based on the content of the `pom.xml` file you've provided, the configuration specifies Java 1.5 for both the source and target versions in the `maven-compiler-plugin` section. Given the error messages you encountered, you'll need to update these versions to at least Java 7, although Java 8 or newer is recommended if compatible with the rest of your project and dependencies.

Here's how you can update the `pom.xml` to use Java 8, which is widely supported and provides a good balance of modern features and compatibility:

```xml
<build>
    <plugins>
        <plugin>
            <groupId>org.apache.maven.plugins</groupId>
            <artifactId>maven-compiler-plugin</artifactId>
            <configuration>
                <source>1.8</source> <!-- Updated from 1.5 to 1.8 -->
                <target>1.8</target> <!-- Updated from 1.5 to 1.8 -->
            </configuration>
        </plugin>
        ...
    </plugins>
    ...
</build>
```

Make sure to replace the `<source>1.5</source>` and `<target>1.5</target>` lines with the updated version as shown above. After making these changes, save the `pom.xml` file.

Next, you should attempt to rebuild the project. Navigate to your project's root directory in the terminal (ensure you're at the root where the `pom.xml` file is located or specify the path to it) and run:

```bash
mvn clean install
```

This command cleans any compiled files you have (ensuring a fresh start), then compiles your project and runs any tests. If everything is configured correctly, this should resolve the compilation errors related to the unsupported source and target Java versions.

If you encounter any more errors during the build, they may be related to other aspects of your project's configuration or dependencies that also need to be updated for compatibility with Java 8. Keep an eye on the Maven output for any such issues and address them accordingly. 

 
 




Using it in Linux.
Now we set up have finished sigploit 



GSMEvil2
What are the types of SS7 attacks?

SS7 attacks can be roughly divided into four categories.
1.	Tracking
2.	Interception
3.	Denial of service 
4.	Fraud



Implementing attacks on the SS7 (Signaling System No. 7) protocol in an emulated environment requires a multi-step process, including understanding the legal and ethical implications. First and foremost, it's important to highlight that attempting unauthorized access or attacks on communication networks is illegal and unethical. My guidance will be purely educational and theoretical, meant for understanding security concepts in a controlled, legal, and ethical setting, such as a cybersecurity research lab.

### Understanding SS7

SS7 is a set of telephony signaling protocols used to set up and tear down most of the world's public switched telephone network (PSTN) telephone calls. It also performs various other functions, including number translation, prepaid billing, Short Message Service (SMS), and other mass market services.

### Legal and Ethical Considerations

- **Permission**: Ensure you have explicit permission to use all hardware and software involved in your tests.
- **Purpose**: The purpose of this setup should be for security research, training, or defensive cybersecurity practices.

### Setting Up an Emulated Environment

1. **Research SS7**: Understand the architecture and protocols involved in SS7, including MTP (Message Transfer Part), SCCP (Signaling Connection Control Part), and others.

2. **Choose an Emulation Tool**: Tools like srsLTE or OpenAirInterface can emulate cellular networks, but they might not fully support SS7. A more specialized tool like SigPloit might be needed.

3. **Hardware Requirements**: You might need specific hardware like Software Defined Radios (SDRs) if you plan to include actual radio communications in your emulation.

4. **Software Setup**: Install the necessary software on appropriate machines. This often involves Linux-based systems.

5. **Network Configuration**: Set up a virtual network that isolates your emulation from real-world networks. This is crucial to prevent unintended interactions with real-world systems.

6. **Implementing SS7 Components**: Use your emulation tool to set up the various components of the SS7 network, including STPs (Signal Transfer Points), SCPs (Service Control Points), and SSPs (Service Switching Points).

### Conducting Ethical Attacks

1. **Define Scope and Goals**: Clearly define what you aim to achieve. For instance, you might want to test how SS7 can be exploited to intercept SMS messages or calls.

2. **Simulate Attacks**: Within your emulated environment, you can simulate various known SS7 attacks, such as location tracking, SMS interception, or fraud.

3. **Monitoring and Analysis**: Use network monitoring tools to analyze the traffic and understand how the attacks work.

4. **Reporting**: Document your findings, including potential vulnerabilities and how they might be mitigated.

### Learning and Mitigation

- Use this knowledge to understand the vulnerabilities in SS7 and how they can be mitigated.
- Share your findings with the community (if appropriate and legal) to contribute to the overall security of telecommunication networks.

### Final Notes

- **Stay Informed**: Ensure you are up-to-date with the legal and ethical guidelines in your country or region regarding cybersecurity research.
- **Collaborate**: Working with academic or research institutions can provide additional resources and ensure the legality of your work.
- **Purpose**: Remember, the goal is to improve security, not to exploit it for unauthorized purposes. 

### Resources for Learning

- Books, academic papers, and official documentation on SS7 and telecommunications security.
- Online courses and workshops on network security and ethical hacking. 

Always prioritize learning and improving security over the temptation to exploit vulnerabilities.

chrome-extension://efaidnbmnnnibpcajpcglclefindmkaj/https://www.gta.ufrj.br/ftp/gta/TechReports/CaCa23.pdf




Wire Shark 
•	Wireshark with SS7 Plugins
Overview: Wireshark is a well-known network protocol analyzer that can be extended with plugins to support SS7.
Capabilities: While not an emulation tool per se, Wireshark can be invaluable for analyzing SS7 traffic and understanding how SS7 messages are structured and flow across a network.
Use Case: Ideal for monitoring and analyzing SS7 traffic in a test environment.

OpenSS7
SS7MAPer


List of Contributors
•	Tweneboah Kodua Kofi Anyimadu.
•	Kizito
![image](https://github.com/Fami21/INSE6120-Winter2024-Project-Group6/assets/33865697/71146552-5e57-4c8b-8aa7-653d3ed13026)
