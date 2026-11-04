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
	- *Domain Digital Certificates* - most digital certificates are those that are issued from a web server to an endpoint. Web servers and clients perform a ==🟣key exchange== when setting up secure communications (see [[Figure 7-6]]). Several types of domain digital certificates are described below:
		- **Domain Validation**- verifies the identity of the entity that has control over the domain name
		- **Extended Validation (EV)** - requires more extensive verification of the legitimacy of a business
		- **Wildcard** - used to validate a main domain along with all subdomains
		- **Subject Alternative Name (SAN)** - AKA Unified Communications Certificate, primarily used for Microsoft Exchange servers or unified communications
	- *Hardware and Software Digital Certificates* - includes machine/computer digital certificates, code signing digital certificates, and email digital certificates
- **Public Key Infrastructure (PKI)**
	- the underlying infrastructure for the management of public keys used in digital certificates
	- *Trust Models* - refers to the type of trust relationship that can exist between individuals and entities. Three PKI trust models use a CA:
		- **Hierarchical Trust Model** - one master CA called the root signs all digital certificate authorities with a single key
		- **Distributed Trust Model** - multiple CAs that sign digital certificates
		- **Bridge Trust Model** - one CA acts as a facilitator to interconnect all other CAs. The facilitator does not issue digital certificates, but instead acts as the hub between hierarchical and distributed trust models
- **Managing PKI**
	- *Certificate Policy* - published set of rules that govern the operation of a PKI
	- *Certificate Practice Statement (CPS)* - more technical document that describes in detail how a CA uses and manages certificates
	- *Key Management* - includes key storage, usage, and handling procedures
		- **Key storage** - storing in software can leave vulnerabilities that expose keys to attacks. Storing in hardware is an alternative. Public keys can be stored using special CA root and intermediate CA hardware devices. Private keys can eb stored on smart cards or in tokens. 
		- **Key handling procedures** - Key escrow refers to a process in which keys are managed by a third party, such as a trusted CA
- **Cryptographic Protocols**
	- *Secure Sockets Layer (SSL)* - early and widespread cryptographic transport algorithm that is now considered obsolete. Attackers can intercept the unsecured requests and establish an HTTPS connection between themselves and the server, while establishing a HTTP connection with the user
		1. browser sends unsecured HTTP request to web server
		2. server responds via HTTP and redirects the browser to a secure page instructing it to use HTTPS
		3. browser sends secure HTTPS request and the secure session begins
	- *Transport Layer Security (TLS)* - replacement for SSL
	- *Secure Shell (SSH)* - encrypted alternative to Telnet protocol used to access remote computers. Both client and server ends of connection are authenticated using a digital certificate, and passwords are protected by being encrypted
	- *Hypertext Transport Protocol Secure (HTTPS)* - HTTP sent over TLS or SSL
	- *Secure/Multipurpose Internet Mail Extensions (S/MIME)* - protocol for securing email messages
	- *Secure Real-time Transport Protocol (SRTP)* - protocol for providing protection for voice over IP (VoIP) communications
	- *IP Security (IPsec)* - protocol suite for securing Internet Protocol communications. Encrypts and authenticates each IP packet of a session between hosts or networks
- **Implementing Cryptography**
	- *Key strength* - cryptographic keys are values that serve as inputs to algorithms. Strength is determined by its randomness, its cryptoperiod (length of time for which a key is authorized for use), and its length
	- *Block Cipher Modes of Operation* - some algorithms work on one character at a time (stream cipher), while others manipulate an entire block of plaintext at once (block cipher). Block cipher modes of operation describe how blocks should be handled
		- **Electronic Code Book (ECB)** - plaintext is divided into blocks, and each block is encrypted separately
		- **Cipher Block Chaining (CBC)** - after being encrypted, each ciphertext block gets fed back into the encryption process to encrypt the next plaintext block
		- **Counter (CTR)** - requires that both the message sender and receiver access a counter, which computes a new value each time a ciphertext block is exchanged
		- **Galois/Counter (GCM)** - both encrypts plaintext and computes a message authentication code (MAC) to ensure that the message was created by the sender and that it was not tampered with during transmission