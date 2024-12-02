# Post-Quantum Cryptography Zenroom scripts
Multiplatofrm Post-Quantum cryptography Zenroom scripts for microservices or as a library.

Includes: 
- ML-DSA-44 sign: signs a string and returns **string**, **signature** and **public key** of the signer. Uses a private key included in the [repo](https://github.com/ForkbombEu/tf-pqcrypto-scripts/blob/main/contracts/ml-dsa44-sign.keys.json). If you want to create a new sk, use the example [Apiroom](https://apiroom.net) or use [Zenrooom CLI](https://dev.zenroom.org/#/pages/zencode-scenarios-post-quantum-cryptography)
- ML-DSA-44 verify: verifies the output from above

# As a microservice

The scripts can be used in Zenroom, or as a microservice. 

When used as standalone, requires [NCR](https://github.com/forkbombEu/ncr) to run

# Quickstart 

## Setup and unr NCR

Downlod NCR (currently **runs only on Linux**):

```bash
wget https://github.com/forkbombeu/ncr/releases/latest/download/ncr && chmod +x ncr
```

Run NCR no port 3333:

```bash
./ncr -p 3333 -z ../tf-pqcrypto-scripts/contracts
```

## Create keys, print pubkeys

There are already secret and public keys in the folder ./contracts/keys that you can use for testing. 

You can also create new keys, using the API *create-keys* or the corresponding applet that you can open at http://localhost:3333/create-keys/app, the new keys will be stored into ./contracts/keys/keyring.keys.json and ./contracts/keys/pubkeys.keys.json

You can also print out the pubkeys using the API *print-pubkeys* or the corresponing applet at http://localhost:3333/print-pubkeys/app

## APIs

Once you have created your keys, you can: 
- Sign a string (using the secret key we just created) with ML-DSA-44
- verify a ML-DSA-44 signature 
**Note**: if instead of a string you want to sign an object or data coming from an endpoint, 1 or 2 lines of Zencode are needed (ask us if you need help at info@forkbomb.eu)

- encrypt a string using ML-KEM + AES (coming soon)
- decrypt a string using ML-KEM + AES (coming soon)

# Swagger

Open the browser at http://localhost:3333/docs 

You should see something like: 

![Swagger](/images/NCR-PQ.png)



# Applets

In Swagger, navigate the *Generated Applets* section, press *execute* and open the resulting URL in the browser, or access the applets directly from:

* Signature applet: http://localhost:8080/ml-dsa44-sign/app
* Verification applet:http://localhost:8080/ml-dsa44-verify/app

The applets look like: 

![Applet](/images/NCR-PQ-applet.png)

 
