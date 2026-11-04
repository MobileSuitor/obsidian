<u>Objectives</u>
1. Define digital certificates
2. Describe the components of Public Key Infrastructure (PKI)
3. Describe the different cryptographic protocols
4. Explain how to implement cryptography

------------
- **Defining Digital Certificates**
	- Asymmetric cryptography uses a pair of related keys, public and private, and has two uses: encrypting/decrypting a set of data, and being used as a proof to verify a "signature" of the sender
	- Digital signatures - hash digest that is generated on a document and then encrypted with the sender's private key. The encrypted document and signature is sent to the recipient, and able to be decrypted using the public key of the sender. If the signature cannot be decrypted, then it did not come from the sender originally, as only the sender's public key can decrypt the digest generated with their private key
	- ==🟣Digital Certificate== - technology used to associate a user's identity to a public key and that has been digitally signed by a trusted third party, which verifies the owner and that the public key belongs to that owner
		- can be used to identify objects other than users, such as servers and applications 
- **Managing Digital Certificates**
	- *Certificate Authorities* - entities that are responsible for digital certificates
		- applicants for digital certificates must submit a Certificate Signing Request (CSR) to a registration authority. Once verified, the CSR is sent to an intermediate CA to be processed on behalf of the CA
	- *Certificate Repository* - publicly accessible centralized directory of digital certificates that can be used to view the status of a digital certificate
- **Types of Digital Certificates**
	- *Root Digital Certificates* - grouping and verifying digital certificates relies on ==🟣certificate chaining==, in which digital certificates issued by root CAs and intermediate CAs are signed by the entity that is identified by the next-higher certified entity in the chain. The ==🟣root digital  certificate== refers to the top-most certificate in this chain, the root CA
	- *Domain Digital Certificates* - 