# Revision History

# **KW47_A2_1_SDKFW2.0**

## FW version
* 0x2000000 0xf62d24e

## FW updates
* Extended ASYMMETRIC_SPAKE2_DERIVE_KEY service to support CCC specification (Digital Key Technical Specification v4.0.0 CCC-TS-101).
* Extended KEY_STORE_GET_KEY service with request to get public key called on private key only key object, which will newly calculate and return public key for NIST-P and Brainpool elliptic curves.

# **KW47_A2_1_SDKFW1_0**

## Release description

This is the release note for loadable EdgeLock Enclave (ELE) Firmware. This ELE FW is authenticated and installed by ELE ROM. It provides new features, fixes, and exposes cryptographic services.


## FW version
* 0x1000000 0xa4959964

## FW updates
* Fixed problem with tunnel request handling.

# **KW47_A2_1_SDKFW1_0_EAR3**

## Release description

This is the release note for loadable EdgeLock Enclave (ELE) Firmware. This ELE FW is authenticated and installed by ELE ROM. It provides new features, fixes, and exposes cryptographic services.


## FW version
* 0x1000000 0x56b64c75

## FW updates
* Fixed problem with stack sharing between ROM and FW.

# **KW47_A2_1_SDKFW1.0_EAR2**

## FW version
* 0x1000000 0x96A49DED

## FW updates
* Support of EL2GO blob import features.
* Support for Elgamal blob import according Geely specification.

# **KW47_A2_SDKFW1.0_EAR1**

## FW updates:
* Adding support for Elgamal blob import according Geely specification.

## Supported revision
* KW47 A2.1
* MCXW72x A2.1

## Backward compatibility
Software that runs on KW47 ELE ROM should run also on KW47 ELE ROM with loaded FW with documented exceptions.

## Build instructions
The FW cannot be rebuilt and is available in binary form only.

# **KW45_K32W1xx_MCXW71_SDKFW2.1_RFP**

## Release description

This is the release note for loadable EdgeLock Enclave (ELE) Firmware. This ELE FW is authenticated and installed by ELE ROM. It provides new features, fixes, and exposes cryptographic services.

Services exposed by this firmware:
* Fix problem with EdgeLock2Go blob import with P521 public key.

## Supported revision
* KW45
* K32W1xx
* MCXW71

# **KW45_K32W1xx_MCXW71_SDKFW2.0_RC1.1**

## Release description

This is the release note for loadable EdgeLock Enclave (ELE) Firmware. This ELE FW is authenticated and installed by ELE ROM. It provides new features, fixes, and exposes cryptographic services.

Services exposed by this firmware:
* Updates in EdgeLock2Go PSA key atributes combinations.
* Updated maximal size of EdgeLock2Go blob.

## Supported revision
* KW45
* K32W1xx
* MCXW71

# **KW45_K32W1xx_MCXW71_SDKFW2.0_RC1**

## Release description

This is the release note for loadable EdgeLock Enclave (ELE) Firmware. This ELE FW is authenticated and installed by ELE ROM. It provides new features, fixes, and exposes cryptographic services.

Services exposed by this firmware:
* Updates in EdgeLock2Go PSA key atributes combinations.

## Supported revision
* KW45
* K32W1xx
* MCXW71

# **SDK_FW_KW45_K32W1xx_MCXW71_1_2_0_1_RC1**

## Release description

This is the release note for loadable EdgeLock Enclave (ELE) Firmware. This ELE FW is authenticated and installed by ELE ROM. It provides new features, fixes, and exposes cryptographic services.

Services exposed by this firmware:
* Added support for EdgeLock2Go blobs import/decryption:
  * Extended KEY_STORE_IMPORT_KEY to import EdgeLock2Go key object to ELE keystore.
  * Extended TUNNEL_REQUEST for authentication and decryption of X.509 and binary data key objects to user defined buffer.
* HMAC functionality extended to enable SHA1, SHA224, SHA384, and SHA512.

## Supported revision
* KW45
* K32W1xx
* MCXW71

## Backward compatibility
Software that runs on KW45 ELE ROM should run also on KW45 ELE ROM with loaded FW with documented exceptions.

## Build instructions
The FW cannot be rebuilt and is available in binary form only.

# **KW45_A1_A2_SDK_FW_1_1_0_0**

## Release description

This is the release note for loadable EdgeLock Enclave (ELE) Firmware. This ELE FW is authenticated and installed by ELE ROM. It provides new features, fixes, and exposes cryptographic services.

## FW updates:
* Update of HMAC one go service to support message bigger than 64kB
API remain same as in ROM service, only maximal supported message length updated from 65536 bytes to 4294967295 bytes for HMAC algorithm.

* DRBG initialized according NIST SP 800-90b (1024bit validated against 512bit validated in ROM)
API remain same as in ROM service, if the high quality random number is requested for the first time, the DRBG is initialized by entropy from TRNG with validated 1024bits by statistical checks, ROM implementation validates only 512bits. This is done to be compliant with NIST SP 800-90b. DRBG is instantiated only once till S200 reset. If was previously used ROM service to initialize DRBG, the firmware load removes the global flag and once is high quality random number again requested, DRBG will be initialized newly in a way compliant with NIST SP 800-90b.

## Supported revsion
* KW45

## Backward compatibility
Software that runs on KW45 ELE ROM should run also on KW45 ELE ROM with loaded FW with documented exceptions.

## Build instructions
The FW cannot be rebuilt and is available in binary form only.