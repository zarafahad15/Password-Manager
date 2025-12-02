Password Manager

A secure and lightweight command-line password manager written in Python.
This application allows users to generate strong passwords, store them securely using symmetric encryption, and retrieve them when needed. All stored passwords are encrypted locally using the cryptography library.

⸻

Features
	•	Strong password generation using cryptographically secure randomness
	•	Encrypted storage using Fernet symmetric encryption
	•	Simple command-line interface for saving and retrieving passwords
	•	Local JSON database for service credentials
	•	Automatic encryption key generation and persistence

⸻

Requirements
	•	Python 3.8 or higher
	•	cryptography library

Install dependencies:

pip install cryptography


⸻

Project Structure

password_manager.py
secret.key          # Automatically generated encryption key
passwords.json      # Encrypted password storage (auto created)


⸻

How It Works
	1.	Key Management
	•	On first run, the application generates a secret.key file.
	•	All password entries are encrypted/decrypted using this key.
	2.	Password Storage
	•	Passwords are encrypted with Fernet and stored in a local JSON file.
	•	Each entry includes a service name, username, and encrypted password.
	3.	Password Retrieval
	•	The application decrypts the password associated with a specified service.
	•	No remote storage or cloud dependency.

⸻

Usage

Run the application:

python password_manager.py

Menu options include:
	1.	Generate a strong password
	2.	Save a password (manual or automatically generated)
	3.	Retrieve an existing password
	4.	Exit the application

⸻

Security Notes
	•	The secret.key file is required to decrypt passwords; keep it secure and do not share it.
	•	All stored passwords are encrypted using the Fernet implementation of AES-128 in CBC mode with HMAC verification.
	•	If the key is deleted, existing passwords cannot be recovered.
	•	Consider additional hardening such as:
	•	A master password
	•	Key derivation (PBKDF2, scrypt, or Argon2)
	•	Secure key storage mechanisms

⸻

Extending the Project

Possible enhancements include:
	•	Adding a master password to derive the encryption key
	•	Building a GUI (Tkinter or PyQt)
	•	Implementing a FastAPI or Flask web interface
	•	Integrating secure clipboard handling
	•	Adding password expiration and auditing features

⸻
