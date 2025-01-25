# Digital_Signature_Verification

Overview

The Digital Signature Verification project demonstrates the process of securing a confidential file by signing it with a digital signature using the SHA256 algorithm. It also verifies the integrity of the file to detect any unauthorized changes or corruption.

This project utilizes OpenSSL, a robust toolset for implementing cryptographic functions like key generation, signing, and verification.

---

Prerequisites

Before starting, ensure the following:
	•	OpenSSL is installed on your system.
	•	You have a file to sign (e.g., contract.txt).

---

Steps

Step 1: Generate a private key 

openssl genpkey -algorithm RSA -out private_key.pem

Step 2: Generate a private key

openssl pkey -in private_key.pem -pubout -out public_key.pem

Step 3: Sign the confidential file with a SHA256 signature

openssl dgst -sha256 -sign private_key.pem -out signature contract.txt

Step 4: Verify the file

openssl dgst -sha256 -verify public_key.pem -signature signature contract.txt

---

Expected Output
	•	If the file is authentic and unaltered, OpenSSL will confirm the verification.
	•	If the file has been tampered with or the signature does not match, verification will fail.

---

Project Structure

 Digital_Signature_Verification/
├── private_key.pem         # Generated private key
├── public_key.pem          # Derived public key
├── contract.txt            # File to be signed (example)
├── signature               # Generated signature

---

Notes
	•	The SHA256 algorithm is used for hashing to ensure strong security.
	•	Always keep your private key secure and do not share it with anyone.
	•	The public key can be distributed to those who need to verify the signature.

---

License

This project is open-source and distributed under the MIT License.
