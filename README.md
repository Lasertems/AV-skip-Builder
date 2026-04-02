# Anti-Detection Trojan Generator

**This project represents my personal research into anti-detection trojan techniques, which may stem from my own ideas and online sources!**

**Important Notice: The techniques, concepts, and tools discussed herein are intended solely for educational purposes related to security. No one may use them for illegal activities or profit-making purposes. Violators will bear full responsibility for any consequences!**

The loader project corresponding to this project: [https://github.com/SurrealSky/shellcode_launcher](https://github.com/SurrealSky/shellcode_launcher)** 

---
The anti-detection techniques employed in this project primarily involve PE file modification, decoupled execution, and inline hooking.

- **Software Description**
    + Universal Program Bundler
        - Adds a new section to any program, bundles the CS-generated stage Trojan into the new section, and modifies the program's OPE pointer.
    + Loader Bundling
        - Stage Bundling: When paired with the SCByPE loader, adds a new section to the loader program, encrypts the stage Trojan, and bundles it into the new section. The loader decrypts and executes the Trojan program.
        - URL Bundling: Paired with the SCByPE loader, adds a new section to the loader program, encrypts the stageless URL, and bundles it into the new section. The loader parses the URL link to download the trojan program and executes it.
    + Separate Encryption Methods
        - Encrypted RAW: Paired with the SCByFile loader, encrypts the stage trojan program into a new file. The loader runs using this file as a parameter, parses the trojan code, and executes the stage trojan.
        - Encrypted URL: Paired with the SCByFile loader, loads the stageless trojan URL into a new file. The loader runs using this file as a parameter, downloads the stageless trojan, and executes it.
    
- **Note**
    + Currently, techniques such as flower commands, compiler obfuscation, and API hooking have not been implemented.

---
# Anti-Detection Capability Explanation

+ **1. Arbitrary Program Bundler**
    - Current Status: Least effective anti-detection performance.
    - Improvements: Can incorporate obfuscation instructions, insert the Trojan program into idle program regions, set OEP to point to the original program, and trigger execution via hard-coded jumps or API hooking.

+ **2. Loader Bundling**
    - Stage Bundling
        + Current Status: Poor anti-detection effectiveness.
        + Improvements: None.
    - URL Bundling
        + Current Status: Moderate anti-detection effectiveness.
        + Improvements: None.
+ **3. Separate Encryption Methods**
    - Encrypted RAW
        + Current Status: Evades detection by mainstream antivirus software.
        + Improvements: Incorporate Hellgate and similar techniques.
    - Encrypted URL
        + Current Status: Evades detection by mainstream antivirus software.
        + Improvements: Incorporate Hellgate and similar techniques.

**good luck！~**

