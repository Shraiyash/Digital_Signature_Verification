# Digital_Signature_Verification

Step 1: Generate a private key 
openssl genpkey -algorithm RSA -out private_key.pem

Step 2: Generate a private key
openssl pkey -in private_key.pem -pubout -out public_key.pem

Step 3: Sign the confidential file with a SHA256 signature
openssl dgst -sha256 -sign private_key.pem -out signature contract.txt

Step 4: Verify the file
openssl dgst -sha256 -verify public_key.pem -signature signature contract.txt
