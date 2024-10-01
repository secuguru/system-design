## Problem
Design a Secure Login System for a Web Application

## Requirements:
1. Users should be able to log in using their email and password.
2. Passwords must be stored securely using hashing techniques.
3. There should be a limit on failed login attempts.
4. Consider implementing multi-factor authentication (MFA).
5. Suspicious activities should be monitored via logging and anomaly detection.

## Answer
### Situation
  - Type of Application, Security Sensitive? Exposure to public access?
  - Hash algorithm (e.g. PBKDF2, bcrypt, Argon2)
  - how to set a limit on failed login attempts. times? anomaly(geologically) detection?
  - What kinds of MFA are support? (SMS, Auth App, Email)
  - What kind of logs are collected? (Login attempts, IP Address, Login Result-Success/Fail)
### Task
  - Design a secure login system for a web application that required robust authentication and protection against brute force attacks and credential stuffing attacks.
  - Ensure that user passwords were securely stored and that we had mechanisms in place to prevent unauthorized access, as well as detecting suspicious activity.
### Actions
  - Authentication API: Design an API that allows users to log in using their email and password. email and password are transmitted via TLS/SSL from the client to server and are securely hashed on the server before being stored in the database.
  -	Password Hashing: Use strong password hashing algorithms, such as bcrypt, to hash passwords before storing them, with a unique salt added to each password for enhanced security.
  - Login Attempt Limiting: Implemented a mechanism that limits the number of failed login attempts. For example, after 5 failed attempts, the account would be temporarily locked for 15 minutes to prevent brute-force attacks.
  - MFA (Multi-Factor Authentication): After successful login with the correct password, integrate multi-factor authentication (MFA) using an authenticator app or SMS to add an extra layer of security. If the application is a mission critical application, hardware OTP (such as FIDO U2F Key) is more usefull.
  -	Logging & Monitoring: Ensure that all login attempts, including failed ones, were logged along with details like IP address and timestamps. These logs were sent to a centralized logging system, where we could monitor for suspicious activities like repeated failed attempts or logins from unfamiliar locations.
### Result
  - As a result, the system was able to securely authenticate users while preventing unauthorized access through brute force or credential stuffing attacks. The implementation of MFA and real-time monitoring helped to further strengthen the system’s defenses, ensuring only legitimate users could access their accounts.
