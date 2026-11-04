![[Pasted image 20261104112242.png]]

1. Web browser sends message (ClientHello) to server that contains the list of cryptographic algorithms that the client supports
2. Server responds (ServerHello) by indicating which algorithm will be used and sends server digital certificate to browser
3. Browser verifies the server certificate and extracts the server's public key. It then generates a random value and encrypts it with the server's public key (pre-master secret), then sends it to the server (Client Key Exchange)
4. Server decrypts message and obtains the pre-master secret, allowing both the browser and server to create the same master secret, which is used to create ==🟣session keys==. These are symmetric keys used to encrypt/decrypt information exchanged during the session and to verify its integrity