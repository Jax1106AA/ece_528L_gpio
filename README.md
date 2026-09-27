\# ECE 528/L - Robotics and Embedded Systems Lab



\*\*California State University, Northridge\*\*  

\*\*Department of Electrical and Computer Engineering\*\*



\## Lab 0: GPIO



\### Overview



This lab introduced GPIO programming using the TI MSP432P401R LaunchPad. The program configures built-in LEDs, push buttons, a PMOD SWT module, and a PMOD 8LD module. Button and switch inputs are used to select several LED patterns, including binary counters, ring counters, and a Johnson counter. The GPIO direction and drive-strength registers were also examined through the Code Composer Studio debugger.



\### Components Used



\- TI MSP432P401R LaunchPad

\- PMOD SWT module with four slide switches

\- PMOD 8LD module with eight LEDs

\- USB-A to Micro-USB cable

\- Jumper wires

\- Code Composer Studio

\- Git and GitHub



\### Analysis and Results



The GPIO peripherals were initialized and tested successfully. The two built-in push buttons controlled LED1, the RGB LED, and the PMOD 8LD when all PMOD switches were off.



The completed program included the following operating modes:



\- \*\*No switches enabled:\*\* The push buttons control the built-in LEDs and alternating LEDs on the PMOD 8LD.

\- \*\*SWT1 enabled:\*\* The PMOD 8LD displays an 8-bit binary up counter from 0 to 255 with a 100 ms delay.

\- \*\*SWT2 enabled:\*\* The PMOD 8LD displays an 8-bit binary down counter from 255 to 0 with a 100 ms delay.

\- \*\*SWT3 enabled:\*\* The PMOD 8LD displays a left-shifting ring counter with a 200 ms delay.

\- \*\*SWT4 enabled:\*\* The PMOD 8LD displays a right-shifting ring counter with a 200 ms delay.

\- \*\*SWT1 and SWT2 enabled:\*\* The PMOD 8LD displays an 8-bit Johnson counter with a 200 ms delay.



The following register values were observed during debugging:



| Port | Register | Observed Value | Purpose |

|---|---|---:|---|

| Port 1 | P1DIR | `0x01` | Configures LED1 as an output |

| Port 2 | P2DIR | `0x07` | Configures the RGB LED pins as outputs |

| Port 2 | P2DS | `0x07` | Enables high drive strength for the RGB LED pins |

| Port 9 | P9DIR | `0xFF` | Configures all eight PMOD 8LD pins as outputs |

| Port 10 | P10DIR | `0x00` | Configures the PMOD SWT pins as inputs |



\### Register Screenshots



\#### Port 1



!\[Port 1 register configuration](Screenshots/ece528L\_lab0\_gpio\_port1.png)



\#### Port 2



!\[Port 2 register configuration](Screenshots/ece528L\_lab0\_gpio\_port2.png)



\#### Port 9



!\[Port 9 register configuration](Screenshots/ece528L\_lab0\_gpio\_port9.png)



\#### Port 10



!\[Port 10 register configuration](Screenshots/ece528L\_lab0\_gpio\_port10.png)



\### Known Issues or Limitations



No known issues were observed during the final hardware test. Each pattern depends on the PMOD modules being connected to the correct MSP432 pins. Selecting a switch combination that is not assigned to a pattern returns the program to its default behavior.



\### Author Contributions



\- \*\*Aolany Acosta:\*\* Assisted with GPIO testing, register verification, screenshots, repository organization, documentation, and GitHub submission.

\- \*\*Hernan Zapien Robles:\*\* Implemented and tested the GPIO LED patterns and verified their operation on the MSP432 hardware.

\- Both partners contributed to testing the completed project and reviewing the results.



\### References



\- ECE 528/L, \*Lab 0: GPIO\*, California State University, Northridge, Fall 2026.

\- ECE 528/L, \*Lecture and Lab Syllabus\*, California State University, Northridge, Fall 2026.

\- Texas Instruments, \*MSP432P401R SimpleLink Microcontroller LaunchPad Development Kit User’s Guide\*.

\- Digilent, \[Pmod SWT Reference Manual](https://digilent.com/reference/pmod/pmodswt/reference-manual).

\- Digilent, \[Pmod 8LD Reference Manual](https://digilent.com/reference/pmod/pmod8ld/reference-manual).

\- OpenAI, ChatGPT, assistance with debugging, Git workflow, and README organization, accessed September 27, 2026, \[https://chatgpt.com](https://chatgpt.com).

