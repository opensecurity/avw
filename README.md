# ansible vault web

---

a **secure**, **client-side browser tool** designed for effortless encryption and decryption of ansible vault secrets. this utility supports encrypting and decrypting both individual text values and entire files, including multiple variables with distinct vault ids.

## features

* **client-side encryption/decryption**: all cryptographic operations are performed directly in your browser. **no data, passwords, or secrets are ever sent to a server**, ensuring maximum security.
* **encrypt text**: securely encrypt single secret values or multiple ansible variables within a yaml-like structure.
* **decrypt text**: decrypt ansible vault blocks, whether standalone or embedded within larger yaml content.
* **encrypt files**: upload and encrypt entire files.
* **decrypt files**: upload and decrypt ansible vault-encrypted files.
* **vault id support**: compatible with ansible vault ids for managing multiple secrets with different passwords.
* **user-friendly interface**: intuitive web interface for a smooth user experience.
* **theme switching**: toggle between dark and light themes.

## how it works

`avw` leverages the [cryptojs](https://github.com/brix/crypto-js) library to implement the same aes256 encryption algorithm used by ansible vault. when you provide a password and data, the encryption/decryption happens locally in your web browser. this means your sensitive information never leaves your device, mitigating risks associated with server-side processing.

## usage

you can use `avw` by simply opening the `index.html` file in your web browser.

### encryption

1.  select the **"encrypt"** operation mode.
2.  choose **"text input"** for individual values/variables or **"file upload"** for entire files.
3.  **for text input (multiple variables mode)**:
    * add new variable entries with "variable name" and "secret value".
    * optionally provide a "vault id".
    * enter your "vault password".
    * click "encrypt data".
4.  **for text input (simple text mode)**:
    * enter your "secret text".
    * optionally provide a "vault id".
    * enter your "vault password".
    * click "encrypt data".
5.  **for file upload**:
    * click or drag your file onto the designated area.
    * optionally provide a "vault id".
    * enter your "vault password".
    * click "encrypt file".

the encrypted output will appear in the result area, ready to be copied or downloaded.

### decryption

1.  select the **"decrypt"** operation mode.
2.  choose **"text input"** for pasted content or **"file upload"** for encrypted files.
3.  **for text input**:
    * paste your ansible vault encrypted text (single block or multiple `!vault` entries).
    * enter your "vault password".
    * click "decrypt data".
4.  **for file upload**:
    * click or drag your encrypted `.vault` file onto the designated area.
    * enter your "vault password".
    * click "decrypt file".

the decrypted plaintext will be displayed in the result area, ready to be copied or downloaded.

## security considerations

* **offline first**: this tool is designed to work completely offline, ensuring data privacy.
* **password strength**: the security of your secrets heavily relies on the strength of your vault password. always use strong, unique passwords.
* **browser security**: ensure your browser is up-to-date and your system is free from malware, as client-side operations are only as secure as the environment they run in.

## development

this project is a single-page html application, primarily using vanilla javascript and minimal css.

url: [project](https://github.com/opensecurity/avw)

author: Lucian BLETAN
