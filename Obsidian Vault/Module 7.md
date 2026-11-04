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
		- **Key storage** - storing in software can leave vulnerabilities 