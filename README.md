# Post-Quantume Cryptography Zenroom scripts
Multiplatofrm Post-Quantum cryptography Zenroom scripts for microservices or as a library.

Includes: 
- ML-DSA-44 sign: signs a string and returns **string**, **signature** and **public key** of the signer. Uses a private key included in the [repo](https://github.com/ForkbombEu/tf-pqcrypto-scripts/blob/main/contracts/ml-dsa44-sign.keys.json). If you want to create a new sk, use the example [Apiroom](https://apiroom.net) or use [Zenrooom CLI](https://dev.zenroom.org/#/pages/zencode-scenarios-post-quantum-cryptography)
- ML-DSA-44 verify: verifies the output from above

# As a microservice

The scripts can be used in Zenroom, or as a microservice. 

When used as standalone, requires [NCR](https://github.com/forkbombEu/ncr) to run

# Quickstart 

Downlod NCR:

```bash
wget https://github.com/forkbombeu/ncr/releases/latest/download/ncr -O ~/.local/bin/ncr && chmod +x ~/.local/bin/ncr
```

Run NCR no port 8080:

```bash
ncr -p 8080 -z ../tf-pqcrypto-scripts/contracts &
```

# Swagger

Open the browser at http://localhost:8080/docs 

You should see something like: 

![Swagger](/images/NCR-PQ.png)



# Applets

In Swagger, navigate the *Generated Applets* section, press *execute* and open the resulting URL in the browser, or access the applets directly from:

* Signature applet: http://localhost:8080/ml-dsa44-sign/app
* Verification applet:http://localhost:8080/ml-dsa44-verify/app

The applets look like: 

![Applet](/images/NCR-PQ-applet.png)

 
