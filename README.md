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







Using it in Linux.





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




List of Contributors
•	Tweneboah Kodua Kofi Anyimadu.
•	Kizito
