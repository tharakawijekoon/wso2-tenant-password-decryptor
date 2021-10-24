# wso2-tenant-password-decryptor

## Build Project
Clone the repository, change directory into it and execute the following command to build the project

```mvn clean install```

## Decrypt password
change directory in target folder and issue the following command.

```
java -cp org.wso2.custom.password.decrypt-1.0.0.jar:lib/\* org.wso2.custom.password.decrypt.AsymmetricKeyDecryptImpl
```
You will be prompted to enter the following details: Encrypted Text, Server KeyStore file path, KeyStore alias, KeyStore password

example:

```
java -cp org.wso2.custom.password.decrypt-1.0.0.jar:lib/\* org.wso2.custom.password.decrypt.AsymmetricKeyDecryptImpl 
Encrypted Text : eyJjIjoiT0hXOUtRajI3K0JqKzJjRjFTRkdMRXMxUjdSMUE3alZVZ2F1djhRd24yU3JXWXNOWjdBaG9zYllGMHYxSmtEOHNabE5wd1FFZm8vNis1dWVlUGU0aWs4UTNON2huV09FRHVGS3dpejgrWk80VnlkMmx6QWtlRWJPV2p2R1ZYamJyZVY4czVIb2JYUnd0T1lUcmt1MVF2WHg3bXJWZkpSbUZCSk9VT0g1TW9YbUdIZ1kvZVlncU9yVmVKbTlpcHl3Ylo4eUV4andEVi9KazJSaXNMckhkSWMxSHF6Tng0Z0wzTEZDcGZvODBCeEdab05KS1h2UVdIYW5OWUQ0Z2d6SDJzaEJpVzdDLzdLQ1hUYkZkaUxpNkhWb0JsVVZlWXBoTElEcCtQN2VXMTIwU0N5QVVESEIya2dybFBITGFtZERsN0VjR0JtNnFVOFNPOG03VVcwYzZnXHUwMDNkXHUwMDNkIiwidCI6IlJTQS9FQ0IvT0FFUHdpdGhTSEExYW5kTUdGMVBhZGRpbmciLCJ0cCI6IjU3RkYzOEQ5NzY2NEM3OTJGRjg4MDExNzFGMDQxOTFERUQ4ODc3OEQiLCJ0cGQiOiJTSEEtMSJ9
KeyStore file path : /Users/tharaka/Documents/wso2is-5.10.0/repository/resources/security/wso2carbon.jks
KeyStore alias : wso2carbon
KeyStore password : wso2carbon
```
The above values can be passed as args as well. 
```
java -cp org.wso2.custom.password.decrypt-1.0.0.jar:lib/\* org.wso2.custom.password.decrypt.AsymmetricKeyDecryptImpl $CipherText $SuperTenantKeystorePath $SuperTenantKeystoreAlias $SuperTenantKeystorePassword 
```
## Output 
The ouput would be in the following format. The decrypted plain text would be displayed under "*** Plain Text ***"
```
Cipher transformation for decryption : RSA/ECB/OAEPwithSHA1andMGF1Padding
*** Plain Text ***
1b01a18564
```
