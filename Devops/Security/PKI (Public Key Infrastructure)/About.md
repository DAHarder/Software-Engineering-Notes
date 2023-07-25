SSL (Secure Sockets Layer) and TLS (Transport Layer Security) are cryptographic protocols designed to secure communications between two entities, such as a user's web browser and a website, over the internet. These protocols ensure data confidentiality, integrity, and authentication by using strong encryption techniques to prevent eavesdropping and tampering of sensitive information. When you make an online transaction, log into an account or share private information, SSL and TLS create a secure channel to safeguard your data from unauthorized access or exposure to potential threats.

# How it works
SSL and TLS protocols work by establishing a secure connection between two parties, such as your web browser and a web server, through a process known as a "handshake". During the handshake, the following steps occur:

## **ClientHello**:
Your browser sends a message to the web server, requesting to start a secure communication. The message contains information about the SSL/TLS versions and cipher suites (encryption algorithms) supported by your browser.   

## **ServerHello**: 
The server responds by selecting the best SSL/TLS version and cipher suite that both parties support. It also sends its digital certificate, which includes the server's public key and information about the server's identity, verified by a trusted Certificate Authority (CA).

## **Certificate Verification**: 
Your browser checks the server's certificate to ensure it's valid and trustworthy. If the certificate is invalid or expired, you'll receive a warning message.

## **Key Exchange**: 
Your browser uses the server's public key from the certificate to generate a shared secret, called the "premaster secret". This secret is encrypted with the server's public key and sent back to the server.

## **Decryption and Secret Derivation**: 
The server uses its private key to decrypt the premaster secret. Both parties use this secret to create symmetric session keys, which will be used to encrypt and decrypt data exchanged during the secure session.

## **Finished Messages**: 
Both parties send messages to confirm the process is complete, and the secure connection is established using the session keys.

After the handshake, SSL and TLS use the session keys to encrypt and decrypt data exchanged between the browser and server, ensuring confidentiality, integrity, and authenticity of the information being shared.

# How to create public and private keys
See Documentation here: [[SSH]]

# Common key file type endings
![[Pasted image 20230424170935.png]]