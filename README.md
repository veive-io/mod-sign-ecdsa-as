# **Mod Sign Ecdsa**

## **Overview**

`ModSignEcdsa` is a module in the Veive protocol designed to validate signatures using the ECDSA (Elliptic Curve Digital Signature Algorithm) secp256k1 standard. ECDSA is widely used in blockchain systems for securing transactions and verifying the authenticity of messages. This module focuses specifically on validating ECDSA signatures, ensuring that transactions are signed by the rightful account owners.

![image](https://github.com/user-attachments/assets/b7af2978-2e56-4c4e-8277-2259cb42af21)

## **Purpose**

ECDSA is a cryptographic algorithm that generates a digital signature from a private key and a message. In blockchain applications, this signature proves ownership and authorizes transactions. The algorithm provides a high level of security, making it a popular choice for blockchain systems, including Bitcoin and Ethereum.

**Key Components in ECDSA Signature Validation:**

1. **Signature**: A 65-byte string that consists of the actual signature and a recovery byte, which is used to derive the public key from the signature.
2. **Public Key**: The public portion of the key pair, which can be derived from the signature and used to verify the signature.
3. **Transaction ID**: A unique identifier for the transaction, used along with the signature to recover the public key.

### **How `ModSignEcdsa` Works**

The `ModSignEcdsa` module is responsible for validating that a transaction is signed by the account it claims to be from. This process involves:

1. **Signature Length Check**:
   - The module first checks if the provided signature is 65 bytes long, which is the standard length for ECDSA signatures.

2. **Public Key Recovery**:
   - Using the signature and the transaction ID, the module recovers the public key. This recovery process involves complex cryptographic operations that ensure the public key is correctly derived from the signature.

3. **Address Verification**:
   - The recovered public key is then converted into an address. The module checks if this address matches the sender's address provided in the transaction. If they match, the signature is considered valid.

This module's primary role is to provide a robust and efficient method for validating the authenticity of transactions in the Veive protocol, ensuring that only authorized transactions are processed.

## **Usage**

### **Installation**

To install the `ModSignEcdsa` module, first ensure that the Veive protocol is set up on your Koinos blockchain environment. Install the module using yarn:

```bash
yarn add @veive-io/mod-sign-ecdsa-as
```

Deploy the module contract on the Koinos blockchain and install it on the desired account using the `install_module` method provided by the Veive account interface.

### **Scripts**

#### Build

To compile the package, run:

```bash
yarn build
```

#### Dist

To create a distribution, run:

```bash
yarn dist
```

#### Test

To test the package, use:

```bash
yarn jest
```

## **Contributing**

Contributions are welcome! Please open an issue or submit a pull request on the [GitHub repository](https://github.com/veiveprotocol/mod-sign-ecdsa).

## **License**

This project is licensed under the MIT License. See the LICENSE file for details.
