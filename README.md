
# Will Robertson
Thank you for taking the time to view my projects!

The function of this readme is to give a quick idea of what I've worked on and in what language/with which frameworks.

Please note that all of these repositories are private due to Michigan's rules surrounding intellectual property and our honor code.

If you're interested in access, please email me at _wjrob@umich.edu_ and I'll arrange it!









## EECS 370 - Introduction to Computer Organization
### Project 1 - LC-2K ISA Assembler, Simulator, and Multiplier
- The assembler was written exclusively in C. It takes raw LC-2K assembly and translates it into machine language. The output was a series of 32-bit instructions that account for the LC-2K ISA, an academic and instructional RISC that supports 8 simple operations, with opcodes ranging from 0b000 to 0b111.
- The behavioral simulator was similarly written exclusively in C. It simulates any legal LC-2K machine code, and outputs 7 register states as long as the state of a memory array.
- The third part of this project was to write an LC-2K program to multiply two large numbers. We were guaranteed that the two input numbers are, at most, 15 bits. My solution relies on a loop and shift algorithm to find the least significant bit in each loop.

## EECS 388 - Introduction to Computer Security
### Project 1 - Cryptography
-  **(1.1) - Length Extension**
    - Python
    - Exploited SHA-256 hashing (could have also used MD5/SHA-1) to conduct a simulated attack against a bank API. Utilized string concatenation to append a malicious API command to a hashed URL, while accounting for SHA's integrated padding.
- **(1.2) - Hash Collision**
    - Python, Command Line
    - Utilized Marc Steven's fastcoll tool to generate two files with identical MD5 hashes. One file is harmless, and the other executes a malicious payload in Python. The purpose of this was to demonstrate how MD5 hashing should not be relied on. Please note that SHA-1 has similar vulnerabilites, but SHA-1 collisions are more extensive to compute. The first SHA-1 collision was published in 2017 and took 110 GPU-years to compute while another attack, published on Jan. 7, 2020, computed a SHA-1 collision with arbitrary prefixes on a GPU cluster at a cost of about $75,000.
- **(2.1) - Padding Oracle Attack**
    - Python
    - Implemented a Padding Oracle exploit against a simulated CBC (Cipher-Block Chaining) encryption scheme to decrypt messages _without_ any sort of encryption key. This project involved crafting tailored requests to a web server, utilizing its error responses to gradually reveal the plaintext of an encrypted message. The exploit uses the server's responses to iteratively decrypt and recover the original message content, while being aware of and excluding the MAC and padding. 
    - Refined original script from taking ~60 minutes to run to ~20 seconds by making API calls in batch rather than singular.
- **(2.2) - RSA Signature Forgery**
    - Python
    - Wrote a demonstration of Bleichenbacher's RSA signature forgery attack, exploiting vulnerabilites in the signature validation process of a simulated bank API. The Python script generates base64-encoded signatures for arbitrary messages, highlighting the potential for significant security breaches in systems relying on improperly validated PKCS #1 v1.5 padding.
### Project 2 - Web Security
- **Part 1 - SQL Injection**
    - SQL, Python
    - Demonstrated successful SQL injection attacks across multiple defense scenarios on a simulated website. Exploited lack of and simple input sanitization to execute SQL queries. Additionally, developed a more sophisticated approach to bypass enhanced security measures that included input escaping and password hashing (using SHA-256 again!). Wrote a script in Python to find a password to enter into the website that, when hashed, included a sequence that would escape the SQL sanitization and automatically log me in as any user. This script ran for ~20 minutes and gave me 10 possible passwords, 8 of which were successful. 
- **Part 2 - Cross-Site Scripting (XSS)**
    - JavaScript, HTML
    - Built payloads that could be executed by contructing a URL that, when loaded in the victim's browser, sent stolen data to my machine (a simulated attacker's server) via a GET request. Stolen data included username and most recent search. Needed to write different styles of payloads to bypass defense mechanisms of various levels - no defense, removed "script" tag strings, removal of several HTML tags (such as <img>, <body>, etc), and finally the removal of characters such as ; ' and ".
- **Part 3 - Cross-Site Request Forgery (CSRF)**
    - JQuery, Javascript, HTML
    - Developed two HTML files that, when opened by a victim, logs their browser into our simulated website under an account named 'attacker'. The first file exploited the lack of CSRF defenses implemented in the target website, however, the second file needed to circumvent a 16-byte cookie associated with the user's session that was required to login. I cannot go into specifics as the solution relies on one HTML trick, but my solution leveraged both XSS and CSRF.

## EECS 281 - Data Structures and Algorithms
### Project 1 - Maze Solver
- C++
- Employed Breadth-First Search (BFS) and Depth-First Search (DFS) algorithms to navigate through maze configurations (sometimes 100,000s of characters long/wide) to find an optimal solution path, if one exists. Additionally, accounts for up to 26 styles of different doors that the algorithm is not allowed to pass through unless it visits an associated button first. Allows for flexibility between approaches, offering both BFS and DFS options in the command line, as well as different output modes, defaulting to a map representation of the solution.
### Last update 2/21/24 - need to include more 281 projects.

