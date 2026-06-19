# project
# Password Hashing + Strength Demo (Java)

## Project Overview
This project is a simple console application designed to show secure credential handling
principles. It validates a password against length and complexity rules, securely hashes it
and outlines defensive engineering best practices for storing passwords.



## How to run

Ensure that you have the JDK installed on your system. 

1. **Compile the program:**
   ```bash
   javac PasswordSecurityDemo.java

2. **Run the program:**
   ```bash
   java PasswordSecurityDemo


### Real-World Cryptographic Implementation warning
[!IMPORTANT]
Security Rule: Even though this demo showcases standard one way hashing using native SHA-256,
SHA-256 is fundamentally a fast cryptographic hashing algorithm. In actual production systems,
modern password storage demands adaptive slow-hashing algorithms like BCrypt, Argon2 or PBKDF2.
These include built-in automatic salting mechanisms and custom work factors to slow down
hardware accelerated dictionary and rainbow table brute-force attacks.
