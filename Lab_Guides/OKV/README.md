# Database Security Workshop: Oracle Key Vault

## Introduction

This is one of several labs which are part of **Oracle Database Security Workshop.** This workshop will walk you through the process configuring, validating and using all of Oracle's Database Securtity products

Oracle Key Vault enables you to quickly deploy encryption and other security solutions by centrally managing encryption keys, Oracle wallets, Java keystores (JKS), Java Cryptography Extension keystores (JCEKS), and credential files. Oracle Key Vault is optimized for managing Oracle Advanced Security Option/Transparent Data Encryption (TDE) master keys. 

The full-stack, security-hardened Oracle Key Vault software appliance uses Oracle Linux and Oracle Database technology for security, availability, and scalability. This centralized approach addresses challenges that are caused by the increased use of keys, wallets, and keystores, and prevents their accidental loss, while enabling long-term retention and restoration of encrypted data. In addition to supporting Oracle database and application servers, Oracle Key Vault follows the industry standard OASIS Key Management Interoperability Protocol (KMIP) for compatibility with KMIP-based clients.

***To log issues***, click here to go to the [github oracle](https://github.com/oracle/learning-library/issues/new) repository issue submission form.


## Required Artifacts

- The following lab requires:
  - Laptop (Windows, Mac or Linux)
  - VNC client


### LAB CONFIGURATION & DETAILS

- For these lab exercises, the following infrastructure components will be used.
  - Database: Database (pdb1) 
  - Key Vault 18c Server 

- Here is a summary of the users used in these labs.
    - KVAUDITOR / Oracle123+
    - KVSUPER / Oracle123+
    - KVADMIN / Oracle123+
    - oracle / Oracle123
    - root / Oracle123

- If accessing via VNC
  - :2 (5902) - oracle / Oracle123


## Labs

[LAB EXERCISE 100: TDE KEY ESCROW](100/README.md)

[LAB EXERCISE 200: TDE ONLINE MASTER KEY](200/README.md)



