# Java Security  
* Java security technology includes a large set of APIs, tools, and implementations of commonly used security algorithms, mechanisms, and protocols. The Java security APIs span a wide range of areas, including cryptography, public key infrastructure, secure communication, authentication, and access control.  
* The Java security model is based on a customizable "sandbox" in which Java software programs can run safely, without potential risk to systems or users.  
**Overview**: [Oracle](https://www.oracle.com/technetwork/java/javase/jaas/index.html)  
## High-level features
* Platform Security
	* String Data Typing
	* Automatic Memory Management
	* Bytecode verification
	* Secure class loading
* Cryptography
	* Comprehensive API with support for a wide range of cryptographic services 
	* Support for a wide range of standard algorithms including RSA, DSA, AES, Triple DES, SHA, PKCS#5, RC2, and RC4.
* Authentication and Access Control
	* JAAS framework
* Secure Communications
	* APIs and implementations for the following standards-based secure communications protocols: Transport Layer Security (TLS), Secure Sockets Layer (SSL) etc.
* Public Key Infrastructure (PKI)
	* Tools for managing keys and certificates
## Misc
* Java JCA == Java Cryptographic Architecture
* Java JCE == Java Cryptographic Extension
* Java JAAS == Java Authentification and Authorization Service
* Java JSSE == Java Secure Socket Extension
* Read more: https://docs.oracle.com/javase/7/docs/technotes/guides/security/overview/jsoverview.html