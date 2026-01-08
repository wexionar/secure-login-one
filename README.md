# Secure Login One

A secure login where the user's private key is never hosted on servers or the user's online devices ( this project can also be used as a form of two-factor authentication ( 2FA ) where the user's private key is never hosted on servers )

---

## 📜 Security Philosophy: The "Zero-Exposure" Protocol

To ensure absolute cryptographic integrity and protect the user from modern digital threats, this project adheres to the following strict principles:

* **Absolute Private Key Isolation:** No private key (or any fragment of it) should ever be **stored, copied, typed, or dragged** onto any device with an active internet connection. This eliminates risks from keyloggers, clipboard sniffers, and remote access trojans.
* **Air-Gapped Interaction:** We strongly discourage the use of physical connections (USB, cables, or data ports) which can carry hardware-level malware. Communication must be strictly visual through **QR code scanning**.
* **Dedicated Offline Hardware:** We recommend repurposing older mobile devices as **"Cold Vaults."** These devices must remain permanently disconnected (WiFi, Bluetooth, GPS, and Cellular disabled or hardware-removed), running only specialized security software.
* **The Server's Responsibility:** Infrastructure providers must evolve to support these sovereign tools. Users are often the "weakest link" only because the industry has failed to provide systems that do not rely on human memory or exposure to dangerous online environments.

### 🌐 Universal Applications
This model serves as a foundational blueprint for:
* **Secure User Login** & Passwordless Authentication.
* **True Two-Factor Authentication (2FA)** without server-side secrets.
* **Account Recovery** & Identity Confirmation.
* **Secure Transaction Signing** for Banking, Fintech, and Cryptocurrencies.

---

## Requirements

![table](docs/table.png)

## Description

**1&nbsp;)&nbsp;** Using an online device (&nbsp;D1&nbsp;) the user goes to the server's login page (&nbsp;S1&nbsp;)

![login1](docs/login1.png)

**2&nbsp;)&nbsp;** The user simply enters his username in the form, and this data is submitted to the server (&nbsp;login.php&nbsp;)

![login2](docs/login2.png)

**3&nbsp;)&nbsp;** If the user's username exists in the server's database (&nbsp;code.php&nbsp;) then the server creates a 12-digit random code, this random code is encrypted with the user's public key, and a QR code containing the encrypted random code is sent to the user (&nbsp;code.php&nbsp;)

![code1](docs/code1.png)

**4&nbsp;)&nbsp;** Using an offline device (&nbsp;D2&nbsp;) the user scans the QR code, the QR code data is decrypted with the user's private key, and this decrypted data is submitted to the server (&nbsp;code.php&nbsp;)

![code2](docs/code2.png)

**5&nbsp;)&nbsp;** If the 12-digit code submitted by the user is correct (&nbsp;test.php&nbsp;) then the user will be able to access the user's home page (&nbsp;home.php&nbsp;)

![home](docs/home.png)

**6&nbsp;)&nbsp;** And the user will also be able to access the user's profile page (&nbsp;profile.php&nbsp;)

![profile](docs/profile.png)

## Types of Philosophy

**&raquo; &nbsp;** Philosophy : **Never-Never**

* Private Keys : (&nbsp;**Never** on servers&nbsp;) and (&nbsp;**Never** on online devices&nbsp;)

* Therefore, public keys only on (&nbsp;online or offline&nbsp;) servers and private keys only on offline devices.

* This philosophy only applies when using asymmetric encryption algorithms (&nbsp;RSA, ECDSA, EdDSA, etc.&nbsp;)

**&raquo; &nbsp;** Philosophy : **Only-Only**

* Private Keys : (&nbsp;**Only** on offline servers&nbsp;) and (&nbsp;**Only** on offline devices&nbsp;)

* Therefore, private keys : never on online servers and never on online devices.

* This philosophy only applies when using symmetric encryption algorithms (&nbsp;AES, 3DES, etc.&nbsp;)

## License

[MIT](https://opensource.org/license/mit)
