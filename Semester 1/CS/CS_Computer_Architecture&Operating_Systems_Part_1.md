# Computer Science | Computer Architecture and Operating Systems | Part 1

## Table of Contents

1. [Most important questions](#most-important-questions)
    1. [Why do we need text encodings?](#1-why-do-we-need-text-encodings)
    2. [What is UTF-8 good for and when is it better than ASCII?](#2-what-is-utf-8-good-for-and-when-is-it-better-than-ascii)
    3. [How do we address a machine on the internet and how do we address a process?](#3-how-do-we-address-a-machine-on-the-internet-and-how-do-we-address-a-process)
    4. [Which problems of IP data transmission are solved by TCP?](#4-which-problems-of-ip-data-transmission-are-solved-by-tcp)
    5. [Explain how reliable transmission of data is achieved with TCP?](#5-explain-how-reliable-transmission-of-data-is-achieved-with-tcp)
    6. [Which types of applications don’t work optimally with TCP and why?](#6-which-types-of-applications-dont-work-optimally-with-tcp-and-why)
    7. [What is the purpose of the Domain Name Service (DNS)?](#7-what-is-the-purpose-of-the-domain-name-service-dns)
    8. [Explain the structure (Elements and Roles) of DNS.](#8-explain-the-structure-elements-and-roles-of-dns)
2. [Fundamentals](#fundamentals)
    1. [Name the two values Boolean Algebra is typically based on.](#1-name-the-two-values-boolean-algebra-is-typically-based-on)
    2. [Explain the Boolean operator OR.](#2-explain-the-boolean-operator-or)
    3. [What are the most and least significant digits (bits) of a binary number?](#3-what-are-the-most-and-least-significant-digits-bits-of-a-binary-number)
    4. [Convert the binary number 1101 into a decimal number (positive integer).](#4-convert-the-binary-number-1101-into-a-decimal-number-positive-integer)
    5. [Which are the rules you have to apply when adding binary digits of two binary numbers?](#5-which-are-the-rules-you-have-to-apply-when-adding-binary-digits-of-two-binary-numbers)
    6. [How can I represent a signed number in binary notation?](#6-how-can-i-represent-a-signed-number-in-binary-notation)
    7. [What is a floating point value?](#7-what-is-a-floating-point-value)
    8. [What is a character set?](#8-what-is-a-character-set)
    9. [What is character encoding?](#9-what-is-character-encoding)
    10. [Why is UTF-8 better than ASCII / the ISO-8859-1 family of character encodings?](#10-why-is-utf-8-better-than-ascii--the-iso-8859-1-family-of-character-encodings)
3. [Computers + OS](#computers--os)
    1. [What is the instruction set of a CPU?](#1-what-is-the-instruction-set-of-a-cpu)
    2. [Explain the difference between a program and a process.](#2-explain-the-difference-between-a-program-and-a-process)
    3. [Why do we need operating systems for modern multi-purpose computers?](#3-why-do-we-need-operating-systems-for-modern-multi-purpose-computers)
    4. [What are programming languages and why do we use them?](#4-what-are-programming-languages-and-why-do-we-use-them)
    5. [What is the difference between a compiler and an interpreter?](#5-what-is-the-difference-between-a-compiler-and-an-interpreter)
    6. [Explain how distributed software systems work in general.](#6-explain-how-distributed-software-systems-work-in-general)
    7. [What is the Command Line Interface (CLI) of an operating system?](#7-what-is-the-command-line-interface-cli-of-an-operating-system)
4. [Signals](#signals)
    1. [What is a signal?](#1-what-is-a-signal)
    2. [Name three mediums we use to transmit signals.](#2-name-three-mediums-we-use-to-transmit-signals)
    3. [Does the signal transmission method rely on the type of medium?](#3-does-the-signal-transmission-method-rely-on-the-type-of-medium)
    4. [How do we encode binary data on a binary signal? Describe an exemplary solution.](#4-how-do-we-encode-binary-data-on-a-binary-signal-describe-an-exemplary-solution)
    5. [How do we encode binary data on an analog signal?](#5-how-do-we-encode-binary-data-on-an-analog-signal)
    6. [What is multiplexing and why do we need it?](#6-what-is-multiplexing-and-why-do-we-need-it)
    7. [Communication systems rely on networks. Explain why.](#7-communication-systems-rely-on-networks-explain-why)
    8. [With which terms do we describe the elements of a network?](#8-with-which-terms-do-we-describe-the-elements-of-a-network)
5. [Internet Protocol](#internet-protocol)
    1. [Where did the Internet get its name from?](#1-where-did-the-internet-get-its-name-from)
    2. [What is the idea of the OSI model?](#2-what-is-the-idea-of-the-osi-model)
    3. [How many layers does the OSI Model define? What is the role of the network layer aka Internet Protocol (IP) in the OSI Model?](#3-how-many-layers-does-the-osi-model-define-what-is-the-role-of-the-network-layer-aka-internet-protocol-ip-in-the-osi-model)
    4. [Which information do we find in an IP Packet?](#4-which-information-do-we-find-in-an-ip-packet)
    5. [True or False:](#5-true-or-false)
    6. [What is an IP address?](#6-what-is-an-ip-address)
    7. [Where does the address 127.0.0.1 point to?](#7-where-does-the-address-127001-point-to)
6. [TCP](#tcp)
    1. [Name four important fields of an IP packet.](#1-name-four-important-fields-of-an-ip-packet)
    2. [How much data payload can an IP packet transport at most?](#2-how-much-data-payload-can-an-ip-packet-transport-at-most)
    3. [Explain briefly how reliable transmission works in TCP.](#3-explain-briefly-how-reliable-transmission-works-in-tcp)
    4. [For which types of applications is TCP not the best choice for an OSI Layer 4 protocol (transport), and why?](#4-for-which-types-of-applications-is-tcp-not-the-best-choice-for-an-osi-layer-4-protocol-transport-and-why)
    5. [How do I recognize an IPv4 address?](#5-how-do-i-recognize-an-ipv4-address)
    6. [How do I recognize an IPv6 address?](#6-how-do-i-recognize-an-ipv6-address)
7. [HTTP](#http)
    1. [What is HTTP, and what is its primary purpose?](#1-what-is-http-and-what-is-its-primary-purpose)
    2. [What are resources on the web, and how are they represented?](#2-what-are-resources-on-the-web-and-how-are-they-represented)
    3. [How does HTTP interact with resources? Name the basic HTTP methods.](#3-how-does-http-interact-with-resources-name-the-basic-http-methods)
    4. [What is a URL, and what are its components?](#4-what-is-a-url-and-what-are-its-components)
    5. [What are the key features of HTTP/2 compared to HTTP/1.1?](#5-what-are-the-key-features-of-http2-compared-to-http11)
    6. [Explain the structure of an HTTP message.](#6-explain-the-structure-of-an-http-message)
    7. [What do the HTTP status code groups indicate, and what are key examples?](#7-what-do-the-http-status-code-groups-indicate-and-what-are-key-examples)
    8. [Why is character encoding important in HTTP?](#8-why-is-character-encoding-important-in-http)
    9. [What is the role of proxies and gateways in HTTP communication?](#9-what-is-the-role-of-proxies-and-gateways-in-http-communication)
    10. [What is the purpose of headers like `Content-Type` and `Content-Length`?](#10-what-is-the-purpose-of-headers-like-content-type-and-content-length)
    11. [How is HTML structured, and what are its key purposes?](#11-how-is-html-structured-and-what-are-its-key-purposes)
    12. [What are the layers of web content formats?](#12-what-are-the-layers-of-web-content-formats)
    13. [What is the difference between GET and POST in HTTP?](#13-what-is-the-difference-between-get-and-post-in-http)
    14. [What is the significance of `127.0.0.1` in HTTP testing?](#14-what-is-the-significance-of-127001-in-http-testing)

## Most important questions

### 1. Why do we need text encodings?

> 💡 Text encodings are needed to map characters (letters, numbers, symbols) to **binary data** so that computers can store, process, and transmit text.  

Different systems (operating systems, software, etc.) may use different character sets, so encoding standardization ensures text can be read and exchanged across platforms and regions without misinterpretation.

### 2. What is UTF-8 good for and when is it better than ASCII?

> 💡 **UTF-8** is a **character encoding** capable of encoding all characters in the Unicode standard using a variable-length sequence of 1 to 4 bytes per character.

#### Benefits of UTF-8

- **Supports multiple languages and symbols** (e.g., Greek, Cyrillic, Chinese, emojis).
- **Backward compatible with ASCII:** ASCII characters (0-127) are represented by a single byte in UTF-8, making it ideal for systems that also need to handle other languages and symbols.

#### When is it better than ASCII?

- When dealing with **non-English text** or special characters (like accented letters, emojis, or symbols).
- ASCII is limited to **128 characters**, while UTF-8 can handle over **1 million** characters, making it far more versatile.

### 3. How do we address a machine on the internet and how do we address a process?

- **Machine Addressing (Device):**

    We use an **IP address** (e.g., IPv4 or IPv6) to identify a device on the internet. An IP address is unique to each device and is used for routing data between machines.

- **Process Addressing (Application):**

    Processes are addressed using **port numbers**. Each running application or service on a machine listens on a specific port (e.g., HTTP on port 80, HTTPS on port 443). A combination of the **IP address and port number** forms a **socket address** to route data to the correct process on the machine.

### 4. Which problems of IP data transmission are solved by TCP?

TCP solves several issues of IP data transmission:

- **Reliability:** TCP ensures that all packets are delivered successfully and in the correct order.
- **Error Detection:** It includes checksums to ensure data integrity.
- **Flow Control:** Prevents a fast sender from overwhelming a slow receiver by using mechanisms like window size.
- **Congestion Control:** Prevents network congestion by adjusting the transmission rate based on network conditions.

### 5. Explain how reliable transmission of data is achieved with TCP?

Reliable transmission in TCP is achieved through:

1. **Three-Way Handshake:** Establishes a connection before data transfer, ensuring both sides are ready.
2. **Acknowledgments (ACKs):** The receiver sends an ACK for each successfully received packet, allowing the sender to confirm delivery.
3. **Sequence Numbers:** Each byte of data has a unique sequence number, ensuring correct ordering and detecting any lost packets.
4. **Retransmissions:** If an ACK is not received within a certain time, TCP retransmits the data.
5. **Checksums:** Each segment is validated for integrity using checksums. If the data is corrupted, it’s discarded, and a retransmission is triggered.

### 6. Which types of applications don’t work optimally with TCP and why?

Applications that require low latency or real-time communication do not work optimally with TCP due to its reliability features, which introduce delays:

1. **Video Streaming:** Delay from retransmissions and the overhead of error correction make it less suited for real-time video streams.
2. **Voice over IP (VoIP):** Any delay caused by retransmissions disrupts the real-time communication of audio.
3. **Online Gaming:** Real-time gameplay requires fast, uninterrupted data transfer. TCP’s error correction and packet ordering can introduce lag.

For these applications, **UDP** is preferred, as it has lower latency and doesn’t wait for ACKs or retransmit lost packets, sacrificing reliability for speed.

### 7. What is the purpose of the Domain Name Service (DNS)?

> 💡 The **Domain Name Service (DNS)** translates human-readable domain names (like **`www.example.com`**) into **IP addresses** (e.g., `192.0.2.1`). This allows users to access websites using easy-to-remember names rather than numerical IP addresses.

**DNS simplifies access to the Internet** by enabling users to type in friendly URLs instead of needing to remember IP addresses.

### 8. Explain the structure (Elements and Roles) of DNS.

The structure of DNS includes several key elements that work together to resolve domain names:

1. **DNS Resolver:**
    - The client-side component that queries the DNS server to resolve domain names into IP addresses.
    - Often provided by your ISP or public DNS services (e.g., Google DNS, OpenDNS).
2. **Root DNS Servers:**
    - The highest level of DNS servers that know where to find **top-level domain (TLD) servers** (e.g., `.com`, `.org`).
3. **TLD Servers:**
    - These servers are responsible for storing information about second-level domains (e.g., `example.com`).
4. **Authoritative DNS Servers:**
    - These servers store the actual **DNS records** for domains (e.g., IP addresses, mail server info). They provide the final answer to a DNS query.
5. **DNS Records (Types):**
    - **A (Address) Record:** Maps a domain to an IPv4 address.
    - **AAAA Record:** Maps a domain to an IPv6 address.
    - **MX (Mail Exchange) Record:** Directs email traffic to the correct mail servers.
    - **CNAME (Canonical Name) Record:** Maps an alias domain to the true domain name.
    - **TXT Record:** Stores text-based information, such as SPF records for email validation.

**DNS Resolution Process:**

1. A user queries the **DNS resolver**.
2. If the resolver doesn’t have the answer cached, it sends a query to the **root DNS servers**.
3. The root server redirects the query to the appropriate **TLD server**, which then points to the **authoritative server** for the domain.
4. The **authoritative server** provides the IP address (or other record) back to the resolver, which sends the result to the user’s browser or application.

## Fundamentals

### 1. Name the two values Boolean Algebra is typically based on.

Boolean Algebra is based on two values:

- **True (1)**
- **False (0)**

### 2. Explain the Boolean operator OR.

> 💡 The **OR** operator in Boolean Algebra outputs **True (1)** if **at least one** of the inputs is **True (1)**.

**Truth Table:**

| **A** | **B** | **A OR B** |
|:-----:|:-----:|:----------:|
|   0   |   0   |      0     |
|   0   |   1   |      1     |
|   1   |   0   |      1     |
|   1   |   1   |      1     |

### 3. What are the most and least significant digits (bits) of a binary number?

- **Most Significant Bit (MSB):** The leftmost bit in a binary number. It has the **highest value** or weight in the number.
- **Least Significant Bit (LSB):** The rightmost bit in a binary number. It has the **lowest value** or weight in the number.

For example, in **1011**,

- MSB = **1** (leftmost)
- LSB = **1** (rightmost)

### 4. Convert the binary number 1101 into a decimal number (positive integer).

To convert binary to decimal:

$$
1101=(1\times2^3)+(1\times2^2)+(0\times2^1)+(1\times2^0)\\1101=8+4+0+1=13
$$

**Decimal Equivalent:** **13**

### 5. Which are the rules you have to apply when adding binary digits of two binary numbers?

Binary addition rules:

1. $0 + 0 = 0$
2. $0 + 1 = 1$
3. $1 + 0 = 1$
4. $1 + 1 = 10$ (write 0 and carry 1 to the next higher bit)
5. $1 + 1 + 1 = 11$ (write 1 and carry 1)

### 6. How can I represent a signed number in binary notation?

> 💡 Signed numbers in binary can be represented using three common methods: **naive approach**, **one's complement**, and **two's complement**.                        |                                                |

#### Naive Approach (Sign-Magnitude Representation)

In this method, the **first bit (MSB)** represents the sign:

- **0** indicates a positive number.
- **1** indicates a negative number.
The remaining bits represent the absolute value of the number in binary.

**Example: Represent +5 and 5 in an 8-bit binary:**

- **+5**: The sign bit is 0, and the binary representation of 5 is **00000101** → **0 00000101**.
- **-5**: The sign bit is 1, and the binary representation of 5 is **00000101** → **1 00000101**.

|    **Advantages:**    |                                               **Disadvantages:**                                               |
|:---------------------:|:--------------------------------------------------------------------------------------------------------------:|
| Simple and intuitive. | Arithmetic operations (addition, subtraction) become <br> complex because the sign bit needs special handling. |

#### One's Complement

In this method, negative numbers are represented by **inverting all the bits** of the binary representation of their absolute value.

**Example: Represent +5 and 5 in an 8-bit binary:**

- **+5**: **00000101** (unchanged).
- **5**: Invert all bits of **+5** → **11111010**.

|   **Advantages:**  |                                      **Disadvantages:**                                     |
|:------------------:|:-------------------------------------------------------------------------------------------:|
| Simple to compute. | Two representations of zero:<br> **00000000** (positive zero) and **11111111** (negative zero). |

#### Two's Complement (Most Common Method)

> 🚩 This **wasn’t** discussed on lesson, it’s my additional contribution.

In two's complement, negative numbers are represented by:

1. Writing the binary representation of the absolute value.
2. Inverting all the bits.
3. Adding **1** to the result.

**Example: Represent +5 and 5 in an 8-bit binary:**

- **+5**: **00000101** (unchanged).
- **5**:
    1. Start with **00000101**.
    2. Invert the bits → **11111010**.
    3. Add 1 → **11111011**.

|                 **Advantages:**                 |           **Disadvantages:**           |
|:-----------------------------------------------:|:--------------------------------------:|
|        Simplifies arithmetic operations.        | Slightly less intuitive for beginners. |
| Only one representation of zero (**00000000**). |                                        |

#### Comparison of Representations for -5 (8 bits)

| Representation Method | Binary for -5 | Notes |
|:-----------------------------------------------:|:-----------------------------------------------:|:-----------------------------------------------:|
| Naive (Sign-Magnitude) | **1 00000101** | MSB as sign bit, rest as absolute value. |
| One's Complement | **11111010** | Inverted bits of absolute value. |
| Two's Complement | **11111011** | Inverted bits + 1. |

### 7. What is a floating point value?

> 💡 A **floating point value** represents real numbers (including fractions and decimals) in a format that uses:

- **Sign** (positive or negative)
- **Exponent** (range of the value)
- **Mantissa** (precision of the value)

For example, $3.14$ in scientific notation is $1.314 × 10^1$, and in floating-point binary representation, it is stored as a combination of exponent and mantissa.

### 8. What is a character set?

> 💡 A **character set** is a collection of characters that a computer can recognize and process. It includes:

- Letters (A-Z, a-z)
- Digits (0-9)
- Special characters (!, @, etc.)
- Control characters (newline, tab, etc.)

Examples: ASCII, Unicode.

### 9. What is character encoding?

> 💡 **Character encoding** is the system that maps characters from a character set to their corresponding binary values.

For example:

- In **ASCII**, the character **A** is encoded as **01000001** (binary).
- In **UTF-8**, characters from multiple languages can be encoded.

### 10. Why is UTF-8 better than ASCII / the ISO-8859-1 family of character encodings?

UTF-8 is better because:

1. **Wide Range:** It supports over 1.1 million characters from multiple languages, including emojis, unlike ASCII or ISO-8859-1.
2. **Backward Compatibility:** UTF-8 is compatible with ASCII for the first 128 characters.
3. **Efficient Storage:** UTF-8 uses variable-length encoding (1-4 bytes), conserving space for common characters (like English letters).
4. **Universal Standard:** It is the most widely used character encoding on the web and supports multilingual text seamlessly.

## Computers + OS

### 1. What is the instruction set of a CPU?

> 💡 The **instruction set** of a CPU is the complete set of machine-level commands that the processor understands and can execute.

- These instructions control the CPU's operations, such as arithmetic calculations, data movement, logical operations, and control flow.
- Examples of instructions: **ADD (addition), SUB (substract), MOV (copy), JMP (”jump” to a specified location in the code), CMP (compare two values)**.
- Instruction sets are specific to the CPU architecture (e.g., x86, ARM).

### 2. Explain the difference between a program and a process.

#### Program:

- A static set of instructions written in a programming language.
- It resides on storage (e.g., a hard disk) as a file.
- Example: An `.exe` file on Windows or a `.sh` script on Linux.

#### Process:

- A program in **execution**.
- A process is dynamic and includes the program’s code, allocated resources (e.g., memory, CPU time), and execution state.
- Multiple processes can run instances of the same program simultaneously.

### 3. Why do we need operating systems for modern multi-purpose computers?

> 💡 An **Operating System (OS)** is essential because it serves as a bridge between hardware and applications, providing a platform for efficient and user-friendly operation.

#### Five key features of an operating system

1. **Resource Management:** Manages CPU, memory, disk, and other resources.
2. **Process Management:** Handles the creation, scheduling, and termination of processes.
3. **File System Management:** Organizes data in files and directories for storage and retrieval.
4. **Security and Access Control:** Protects system resources and user data from unauthorized access.
5. **User Interface:** Provides interfaces like **CLI (C**ommand **L**ine **I**nterface**)** or **GUI** (**G**raphical **U**ser **I**nterface**) for users to interact with the computer.

### 4. What are programming languages and why do we use them?

> 💡 **Programming languages** are structured systems of communication that allow developers to write instructions (code) for computers to execute tasks.

#### Examples

**Python**

```python
def main():
    print("Hello, World!")

if __name__ == "__main__":
    main()
```

**C++**

```cpp
#include <iostream>

int main() {
    std::cout << "Hello, World!" << std::endl;
    return 0;
}
```

**Java**

```java
public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hello, World!");
    }
}
```

#### Why we use them:

1. Computers only understand binary (machine language), and programming languages provide a more human-readable way to communicate with them.
2. They increase productivity by offering abstractions for complex operations.
3. They are designed for various use cases, e.g., web development (JavaScript), data analysis (Python), or system programming (C).

### 5. What is the difference between a compiler and an interpreter?

#### Compiler:

- Translates the entire source code into machine code **before execution**.
- Output: An independent executable file.
- Example: C, C++ (compiled into `.exe`).
- **Advantage:** Faster execution after compilation.
- **Disadvantage:** Debugging is harder because errors are reported after compilation.

#### Interpreter:

- Translates and executes source code **line by line**.
- No independent executable file is created.
- Example: Python, JavaScript.
- **Advantage:** Easier debugging as errors are identified immediately.
- **Disadvantage:** Slower execution due to real-time interpretation.

### 6. Explain how distributed software systems work in general.

> 💡 **Distributed software systems** consist of multiple independent components running on different computers (nodes) that work together to achieve a common goal.

#### Key characteristics:

1. **Resource Sharing:** Nodes share hardware, data, and software resources.
2. **Communication:** Nodes communicate via a network (e.g., LAN, WAN, the internet).
3. **Fault Tolerance:** The system can continue functioning even if some nodes fail.
4. **Scalability:** New nodes can be added to handle increased demand.
5. **Examples:** Cloud computing platforms, web applications, and peer-to-peer systems.

#### General Workflow

1. A client sends a request.
2. The request is processed by one or more servers/nodes.
3. The nodes collaborate to return the result to the client.

### 7. What is the Command Line Interface (CLI) of an operating system?

> 💡 The **Command Line Interface (CLI)** is a text-based interface where users interact with the operating system by typing commands.

#### Features

1. Allows users to execute tasks like file manipulation, process management, and network configuration.
2. Requires specific commands and syntax (e.g., `ls`, `cd`, `mkdir` in Linux).
3. Often used by advanced users for automation, troubleshooting, and precise control.

|                **Advantages**                |               **Disadvantages**               |
|:--------------------------------------------:|:---------------------------------------------:|
|    Lightweight and faster compared to GUI.   |       Requires memorization of commands.      |
| Provides access to powerful scripting tools. | Less user-friendly than graphical interfaces. |

## Signals

### 1. What is a signal?

> 💡 A **signal** is a representation of data used to transmit information between devices.

Signals can be:

- **Analog:** Continuous signals that vary over time (e.g., sound waves, radio waves).
- **Digital:** Discrete signals, usually represented as binary values (0s and 1s).

### 2. Name three mediums we use to transmit signals.

1. **Copper Cables** (e.g., twisted pair, coaxial cables): Electrical signals.
2. **Fiber Optic Cables:** Light signals.
3. **Wireless Mediums** (e.g., radio waves, microwaves): Electromagnetic signals.

### 3. Does the signal transmission method rely on the type of medium?

Yes, the signal transmission method relies on the type of medium because different mediums are suited to specific types of signals:

- **Copper cables:** Transmit electrical signals, which are suitable for short to medium distances.
- **Fiber optic cables:** Transmit light signals, ideal for high-speed and long-distance communication with minimal loss.
- **Wireless mediums:** Transmit electromagnetic waves, useful for mobile communication and environments where cables are impractical.

Each medium has distinct properties (e.g., bandwidth, attenuation, noise susceptibility), determining the signal type and transmission method used.

### 4. How do we encode binary data on a binary signal? Describe an exemplary solution.

To encode binary data on a binary signal, we map binary values (0 and 1) to **specific signal states**.

#### Exemplary Solution: **Non-Return-to-Zero (NRZ) Encoding**

- **Binary 1:** Represented by a high voltage level.
- **Binary 0:** Represented by a low voltage level.

##### Example

Binary data: **10110**

NRZ Signal: High → Low → High → High → Low

Other encoding techniques include Manchester encoding and NRZ-Inverted.

### 5. How do we encode binary data on an analog signal?

> 💡 To encode binary data on an analog signal, we use **modulation techniques** to alter specific characteristics of the analog wave (amplitude, frequency, or phase) based on binary input.

#### Amplitude Modulation (AM)

In AM, the **amplitude** of the analog wave varies based on the binary input:

- Binary 1: Higher amplitude.
- Binary 0: Lower amplitude.

**Example:**

Binary Data: **101**

- Binary 1 → Analog wave with **high amplitude**.
- Binary 0 → Analog wave with **low amplitude**.

**Signal Representation:**

```
101 → (High Amplitude) (Low Amplitude) (High Amplitude)
```

**Real-Life Use:**

AM radio signals transmit audio data by modulating the amplitude of the carrier wave.

#### Frequency Modulation (FM)

In FM, the **frequency** of the analog wave changes based on the binary input:

- Binary 1: Higher frequency (waves are closer together).
- Binary 0: Lower frequency (waves are farther apart).

**Example:**

Binary Data: **101**

- Binary 1 → Analog wave with **higher frequency**.
- Binary 0 → Analog wave with **lower frequency**.

**Signal Representation:**

```
101 → (High Frequency) (Low Frequency) (High Frequency)
```

**Real-Life Use:**

FM radio stations transmit audio by modulating the frequency of the carrier wave.

#### Phase-Shift Keying (PSK)

In PSK, the **phase** of the analog wave shifts to represent binary data:

- Binary 1: Phase shift occurs (e.g., 180°).
- Binary 0: No phase shift (wave continues as is).

**Example:**

Binary Data: **101**

- Binary 1 → Analog wave shifts phase.
- Binary 0 → No phase shift.

**Signal Representation:**

```
101 → (Shift Phase) (No Shift) (Shift Phase)
```

**Real-Life Use:**

Wi-Fi and cellular communication (e.g., 4G, 5G) use variations of PSK for efficient data encoding.

#### Comparison Table of Encoding Methods

|         **Method**        | **Binary 1 Representation** | **Binary 0 Representation** |      **Example Use**     |
|:-------------------------:|:---------------------------:|:---------------------------:|:------------------------:|
| Amplitude Modulation (AM) |       Higher Amplitude      |       Lower Amplitude       |         AM radio         |
| Frequency Modulation (FM) |       Higher Frequency      |       Lower Frequency       |         FM radio         |
|  Phase-Shift Keying (PSK) |   Phase Shift (e.g., 180°)  |        No Phase Shift       | Wi-Fi, cellular networks |

### 6. What is multiplexing and why do we need it?

> 💡 **Multiplexing** is a technique used to combine multiple signals and transmit them over a single communication channel.

#### Why is it needed?

1. **Efficient Utilization:** Maximizes the use of available bandwidth.
2. **Cost Reduction:** Reduces the need for separate channels for each signal.
3. **Scalability:** Enables multiple users or data streams to share the same medium.

#### Types of Multiplexing

- **Time Division Multiplexing (TDM):** Signals share the channel by taking turns in time slots.
- **Frequency Division Multiplexing (FDM):** Signals occupy separate frequency bands.
- **Wavelength Division Multiplexing (WDM):** Used in fiber optics, signals are separated by light wavelengths.

### 7. Communication systems rely on networks. Explain why.

Networks enable communication systems to:

1. **Facilitate Connectivity:** Link multiple devices (e.g., computers, smartphones) for data exchange.
2. **Share Resources:** Allow shared access to printers, servers, and the internet.
3. **Enable Scalability:** Support growth by adding new devices.
4. **Ensure Reliability:** Use redundant paths to maintain communication even if part of the network fails.
5. **Enhance Communication:** Enable real-time interactions (e.g., VoIP, video conferencing).

Without networks, communication would be limited to isolated devices, reducing efficiency and functionality.

### 8. With which terms do we describe the elements of a network?

1. **Nodes:** Devices connected to the network (e.g., computers, routers, switches).
2. **Links:** Physical or logical connections between nodes (e.g., cables, wireless signals).
3. **Topology:** The arrangement of nodes and links (e.g., star, bus, ring).
4. **Protocols:** Rules governing communication between devices (e.g., TCP/IP, HTTP).
5. **Bandwidth:** The maximum data rate a network link can handle.
6. **Latency:** The delay in transmitting data from source to destination.

## Internet Protocol

### 1. Where did the Internet get its name from?

> 💡 The name **"Internet"** comes from the term **"inter-networking"**, which refers to connecting multiple computer networks together using standardized communication protocols.

- It evolved from research projects like [**ARPANET**](https://en.wikipedia.org/wiki/ARPANET) in the 1960s and 1970s, where the goal was to enable different networks to communicate with each other.

### 2. What is the idea of the OSI model?

> 💡 The **OSI (Open Systems Interconnection) Model** provides a conceptual framework to standardize and describe how different networking protocols and hardware interact to enable communication between devices.

#### Key Ideas

- Divide communication processes into **seven layers**, each handling a specific function.
- Promote **interoperability** between different systems and technologies.
- Allow troubleshooting and development by focusing on individual layers.

### 3. How many layers does the OSI Model define? What is the role of the network layer aka Internet Protocol (IP) in the OSI Model?

The OSI Model defines **7 layers**:

1. **Physical Layer**: Deals with raw data transmission (bits) over physical mediums (cables, signals, etc.). Hardware-focused.

    *Example*: Ethernet cables, Wi-Fi signals.

2. **Data Link Layer**: Ensures error-free data transfer between adjacent devices. Uses MAC addresses for local addressing.

    *Example*: Switches, ARP protocol.

3. **Network Layer**: Handles routing and forwarding of data across networks. Uses IP addresses for global addressing.

    *Example*: Routers, IP protocol.

4. **Transport Layer**: Ensures reliable data delivery (error checking, retransmission) and manages end-to-end communication.

    *Example*: TCP, UDP.

5. **Session Layer**: Manages sessions (connections) between applications, including setup, maintenance, and termination.

    *Example*: Remote login (SSH, SQL session).

6. **Presentation Layer**: Translates, encrypts, or compresses data for application usage.

    *Example*: JPEG images, SSL encryption.

7. **Application Layer**: Provides network services directly to end-user applications.

    *Example*: HTTP (web browsing), SMTP (email).

#### Role of the Network Layer (IP)

- Handles **routing** of packets from the source to the destination across multiple networks.
- Uses **IP addresses** to identify devices on the network.
- Manages **packet fragmentation** if the payload exceeds the maximum transmission size.

### 4. Which information do we find in an IP Packet?

An IP packet typically contains:

1. **Header:** Contains metadata about the packet. Key fields include:
    - Source IP address.
    - Destination IP address.
    - Total length (size of the packet in bytes).
    - Protocol (specifies the transport layer protocol, e.g., TCP or UDP).
2. **Payload:** The actual data being transmitted (e.g., part of a file, message, or webpage).

### 5. True or False:

1. **IP ensures all packets reach the receiver.**

    **False:** IP is an **unreliable protocol** (best-effort delivery). Packets may be lost, delayed, or dropped during transmission.

2. **IP ensures two subsequently sent packets reach the receiver in the same order they were sent.**

    **False:** IP does not guarantee packet ordering. Packets can arrive out of order due to different routing paths.

3. **IP does not prevent the duplication of packets on the way from sender to receiver.**

    **True:** IP does not prevent duplication, and it’s up to higher-layer protocols (e.g., TCP) to detect and handle duplicates.

### 6. What is an IP address?

> 💡 An **IP address** is a numerical identifier assigned to a device connected to a network. It serves two main purposes:

1. **Identification:** Uniquely identifies a device on a network.
2. **Location Addressing:** Provides information about the device’s location within the network for routing purposes.

### 7. Where does the address 127.0.0.1 point to?

The address **127.0.0.1** points to the **local host** or **loopback interface** of a device.

- It allows a device to send network traffic to itself for testing or debugging purposes.
- It does not require a physical network connection.

Example: You can run a web server locally and access it using `http://127.0.0.1`.

## TCP

### 1. Name four important fields of an IP packet.

An IP packet contains several fields, but four important ones are:

1. **Source IP Address:** The IP address of the sender.
2. **Destination IP Address:** The IP address of the intended recipient.
3. **Payload:** The actual data being transmitted, such as a file, message, or webpage content.
4. **Total Length:** Specifies the entire length of the IP packet, including the header and payload, measured in bytes.

### 2. How much data payload can an IP packet transport at most?

- **IPv4:**

    The total packet size is **65,535 ($2^{16}$) bytes (64 KB)**, including headers. With a typical IPv4 header of **20 bytes**, the maximum payload is **65,515 bytes**.

- **IPv6:**

    IPv6 allows a payload size of **4,294,967,295 ($2^{32}$) bytes (4 GB)** through an optional jumbo payload extension, though practical usage is much smaller.

### 3. Explain briefly how reliable transmission works in TCP.

1. **Sequencing**:

    Every byte of data sent over TCP is numbered. This ensures the receiver can reassemble the data in the correct order, even if packets arrive out of order.

    **Example**:

    - Sender sends packets with sequence numbers 1001, 1002, 1003.
    - If packet 1002 is delayed but 1003 arrives first, the receiver waits and uses the sequence numbers to reorder the data.

2. **Acknowledgments (ACKs)**:

    The receiver acknowledges received data by sending an acknowledgment number (e.g., the next expected sequence number).

    **Example**:

    - Receiver gets packets 1, 2, and 3. It sends back an ACK for 4, indicating it expects the next segment to start at sequence 4.
    - If packet 2 is lost, the receiver will not send an ACK for 3, prompting the sender to retransmit 2.

3. **Error Checking**:

    TCP adds a checksum to every segment. The receiver verifies the checksum to ensure the data wasn’t corrupted during transmission. If the checksum doesn’t match, the segment is discarded, and the sender retransmits.

    **Example**:

    - Sender transmits "Hello," but a network error corrupts it into "He#lo."
    - The receiver detects the mismatch using the checksum and requests retransmission.

4. **Retransmission**:

    If an acknowledgment isn’t received within a specific timeout, TCP assumes the packet was lost and retransmits it.

    **Example**:

    - Sender sends packet 1 and expects an ACK in 2 seconds. If no ACK arrives, it resends packet 1.

5. **Flow Control (Window Size)**:

    TCP uses a sliding window mechanism to control the amount of data a sender can transmit before needing an acknowledgment. This prevents overwhelming the receiver.

    **Example**:

    - If the receiver’s buffer size is 10KB, the sender will pause after sending 10KB of data until the receiver sends an ACK indicating space is freed.

6. **Congestion Control**:

    TCP monitors the network for congestion and reduces the transmission rate if congestion is detected. It uses algorithms like **slow start** to gradually increase the rate until the network can handle it.

    **Example**:

    - If multiple retransmissions occur, TCP reduces the data sent per round-trip (congestion window) and increases it slowly after detecting the network is stable.

**Overall Example in Action**:

Imagine you’re downloading a file. TCP splits the file into segments and numbers them.

- If segment 5 gets lost, the receiver doesn’t acknowledge it.
- The sender notices the missing ACK and retransmits segment 5.
- Meanwhile, the receiver uses sequence numbers to correctly reorder the segments before handing the file to the application.

These mechanisms ensure TCP provides reliable, ordered, and error-free transmission over an unreliable network like the Internet.

### 4. For which types of applications is TCP not the best choice for an OSI Layer 4 protocol (transport), and why?

> 💡 **TCP** is not ideal for applications that prioritize **speed and real-time performance** over reliability. Examples:

1. **Video Streaming:**
    - Dropped packets are tolerable as the content is time-sensitive.
    - Using TCP could introduce latency due to retransmissions.
2. **Online Gaming:**
    - Real-time actions require low latency.
    - Delayed retransmissions from TCP would disrupt the experience.
3. **Voice over IP (VoIP):**
    - Real-time audio needs to be delivered with minimal delay.
    - Dropped packets are better than waiting for retransmissions.

In such cases, **UDP** (User Datagram Protocol) is preferred because it is faster and has lower overhead, even though it doesn’t guarantee reliability.

### 5. How do I recognize an IPv4 address?

- **Format:** IPv4 addresses consist of **four decimal numbers**, each ranging from 0 to 255, separated by periods (e.g., `192.168.1.1`).
- **Length:** IPv4 is a 32-bit address, divided into 4 octets (8 bits each).
- **Example:** `192.168.0.1`, `10.0.0.254`

### 6. How do I recognize an IPv6 address?

- **Format:** IPv6 addresses are written as **eight groups of four hexadecimal digits**, separated by colons (e.g., `2001:0db8:85a3:0000:0000:8a2e:0370:7334`).
- **Length:** IPv6 is a 128-bit address.
- **Shortening Rules:**
    1. Leading zeros in each group can be omitted (e.g., `2001:db8:85a3::8a2e:370:7334`).
    2. Consecutive groups of zero can be replaced by `::` (only once in an address).
- **Example:** `2001:0db8:0000:0000:0000:ff00:0042:8329` can be shortened to `2001:db8::ff00:42:8329`.

## HTTP

### 1. What is HTTP, and what is its primary purpose?

> 💡 **HTTP (Hypertext Transfer Protocol)** is a stateless, application-layer protocol that forms the foundation of data communication on the World Wide Web.

It allows clients (e.g., browsers) to request resources from servers and retrieve them in the form of web pages, images, or other data formats.

#### Key Characteristics:

- **Stateless:** Each request-response pair is independent, meaning no memory is retained between interactions.
- **Extensible:** Supports various methods and headers, making it adaptable for different needs.
- **Layer 5-7 in the OSI model:** Operates in the application layer, relying on TCP/IP for transport and routing.

### 2. What are resources on the web, and how are they represented?

> 💡 **Resources** on the web refer to any identifiable item accessible via HTTP, such as web pages, documents, images, or videos.

#### Representation of Resources:

- When a resource is requested, the server provides a **representation** or snapshot of it (e.g., a JSON object, an HTML page, or an image file).
- This concept underpins the **RESTful architecture**, which uses standard HTTP methods to interact with resources.

#### Example:

- A resource could be a user profile at `/users/123`.
- A GET request retrieves the current representation of the profile, while a PUT request updates it.

### 3. How does HTTP interact with resources? Name the basic HTTP methods.

HTTP interacts with resources using **methods** that define the action to be performed:

- **GET:** Retrieve a resource or its representation.
- **POST:** Submit data to create or modify a resource.
- **PUT:** Replace or update a resource.
- **DELETE:** Remove a resource.

**Additional Methods:**

- **HEAD:** Similar to GET but only retrieves the headers (useful for checking resource status).
- **OPTIONS:** Describes the communication options available for a resource.
- **PATCH:** Applies partial updates to a resource.

#### Example Use Case:

A form submission might use POST to send data to `/submit`, while a DELETE request to `/posts/1` would remove a blog post.

### 4. What is a URL, and what are its components?

> 💡 A **URL (Uniform Resource Locator)** specifies the location of a resource on the web and how to access it.

#### Components:

1. **Scheme:** Protocol (e.g., `http`, `https`, `ftp`).
2. **Host:** Domain name or IP address (e.g., `www.example.com`).
3. **Port:** Optional; defaults are `80` for HTTP and `443` for HTTPS.
4. **Path:** Specifies the resource's location on the server (e.g., `/docs/page`).
5. **Query String:** Parameters for additional information (e.g., `?id=123&sort=asc`).

#### Example:

`https://www.example.com:443/resources?id=42`

| **Part** |     **Value**     |
|:--------:|:-----------------:|
| Protocol |      `https`      |
|   Host   | `www.example.com` |
|   Port   |       `443`       |
|   Path   |    `/resources`   |
|   Query  |      `id=42`      |

### 5. What are the key features of HTTP/2 compared to HTTP/1.1?

HTTP/2 improves performance, security, and efficiency over HTTP/1.1.

#### Key Features:

1. **Request Pipelining:** Multiple requests are sent over a single connection without waiting for responses.
2. **Server Push:** Servers can proactively send resources to the client without explicit requests (e.g., sending CSS for a page).
3. **Binary Protocol:** Data is encoded in binary, which is more efficient than HTTP/1.1’s text-based format.
4. **Header Compression:** Reduces overhead by compressing header data.

#### Benefits:

- Faster page loads.
- Reduced latency for complex applications.
- Improved support for modern web features like real-time data updates.

### 6. Explain the structure of an HTTP message.

An HTTP message consists of:

1. **Request/Status Line:**
    - Request line: Includes the method (e.g., GET), URI, and HTTP version.
    - Status line: Contains the protocol version, status code, and reason phrase (e.g., `HTTP/1.1 200 OK`).
2. **Headers:** Metadata about the message, such as `Content-Type` (e.g., `application/json`) and `Content-Length`.
3. **Body:** The optional data being sent, such as form data or JSON payloads.

**Example (Request):**

```vbnet
GET /index.html HTTP/1.1
Host: www.example.com
Content-Type: text/html
```

**Example (Response):**

```vbnet
HTTP/1.1 200 OK
Content-Type: text/html
Content-Length: 137

<html>...</html>
```

### 7. What do the HTTP status code groups indicate, and what are key examples?

> 💡 HTTP status codes are grouped by their **first digit**, each indicating a specific category of response.

#### 1xx: Informational

These codes indicate that the request has been received, and the server is continuing the process.

**Example:**

- **100 Continue:** The server has received the headers and is ready to process the body of the request.

#### 2xx: Success

These codes mean the request was successfully received, understood, and processed.

**Examples:**

- **200 OK:** The request succeeded, and the server returned the requested resource.
- **201 Created:** The request succeeded, and a new resource was created (e.g., after a **POST**).

#### 3xx: Redirection

These codes inform the client that further action is needed to complete the request.

**Examples:**

- **301 Moved Permanently:** The resource has been permanently moved to a new URL.
- **302 Found:** The resource is temporarily available at a different URL.

#### 4xx: Client Errors

These codes indicate an issue with the client’s request.

**Examples:**

- **400 Bad Request:** The request could not be processed due to syntax errors.
- **404 Not Found:** The requested resource could not be located on the server.

#### 5xx: Server Errors

These codes indicate that the server failed to fulfill a valid request.

**Examples:**

- **500 Internal Server Error:** A generic error indicating an unexpected server problem.
- **503 Service Unavailable:** The server is temporarily unable to handle the request (e.g., due to maintenance or overload).

> 💡 Each group helps clients and developers quickly understand the **outcome of an HTTP request** and diagnose potential issues.

### 8. Why is character encoding important in HTTP?

> 💡 Character encoding ensures text data is correctly interpreted, **especially** for non-ASCII characters or symbols.

#### Examples:

- UTF-8 supports characters from multiple languages (e.g., `ä` is encoded as `%C3%A4`).
- Reserved characters like `&` or `?` are percent-encoded to avoid conflicts.

### 9. What is the role of proxies and gateways in HTTP communication?

- **Proxies:** Act on behalf of clients to improve performance (e.g., caching responses) or provide security (e.g., hiding IP addresses).
- **Gateways:** Intermediaries on the server side that encapsulate services or enforce security measures.

#### Example:

A proxy might cache an image for faster subsequent requests, while a gateway could validate user authentication.

### 10. What is the purpose of headers like `Content-Type` and `Content-Length`?

- **Content-Type:** Informs the receiver about the data format (e.g., `application/json`, `text/html`).
- **Content-Length:** Specifies the size of the message body in bytes, ensuring the receiver knows where the message ends.

#### Example:

A `Content-Type: application/json` header signals the server to interpret the body as JSON data.

### 11. How is HTML structured, and what are its key purposes?

> 💡 **HTML** organizes web content into semantic elements using tags (e.g., `<h1>` for headers, `<p>` for paragraphs).

#### Key Purposes:

- Define document structure.
- Embed multimedia elements like images and videos.
- Provide hyperlinks for navigation.

#### Example:

```html
<!DOCTYPE html>
<html>
  <head><title>Example</title></head>
  <body>
    <h1>Welcome!</h1>
    <p>This is a paragraph.</p>
  </body>
</html>
```

### 12. What are the layers of web content formats?

1. **Content Layer:** HTML defines the structure and text.
2. **Style Layer:** CSS provides the look and feel.
3. **Behavior Layer:** JavaScript adds interactivity and dynamic changes.

#### Example:

- HTML: Displays a button.
- CSS: Makes the button blue with rounded edges.
- JS: Adds a click event to the button.

### 13. What is the difference between GET and POST in HTTP?

- **GET:** Retrieves data; parameters are visible in the URL.
- **POST:** Sends data to the server; parameters are hidden in the message body.

#### Example

GET for search queries; POST for form submissions.

### 14. What is the significance of `127.0.0.1` in HTTP testing?

> 💡 **`127.0.0.1`** is the loopback address that points to the local machine. It is used for testing web servers and applications without requiring an external network.


