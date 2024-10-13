# Password Cracking and Hardening: Analyzing Security Vulnerabilities

## Project Overview
This project investigates the vulnerabilities associated with weak passwords and implements password-cracking techniques using industry-standard tools. By understanding the effectiveness of these methods, the project underscores the importance of robust password policies in enhancing cybersecurity.

## Objective
To identify and analyze the weaknesses in password security through practical password-cracking techniques. The goal is to demonstrate the risks associated with weak passwords and emphasize the need for strong password practices.

## Environment
- **Operating System**: Kali Linux
- **Virtualization Software**: Oracle VirtualBox
- **RAM**: 2GB

## Tools and Resources
- **John the Ripper**: Open-source password cracking software used to test password strength.
- **Wordlist**: `rockyou.txt`, a well-known list of common weak passwords.
- **OpenSSL**: Used for generating password hashes.

## Methodology

### Step 1: Generate Password Hashes
Generated various password hashes (MD5, SHA-1, SHA-256) for testing:
```bash
echo -n "password" | openssl dgst -md5 >> md5hash.txt
echo -n "password" | openssl dgst -sha1 >> sha1hash.txt
echo -n "password" | openssl dgst -sha256 >> sha256hash.txt
```
### Step 2: Prepare the Wordlist
Downloaded and prepared the rockyou.txt wordlist for testing:
```
wget https://github.com/graphicore/rockyou.txt/releases/download/2020-12-21/rockyou.txt.gz
gunzip rockyou.txt.gz
```

### Step 3: Crack Passwords Using John the Ripper
Used John the Ripper to crack the hashes:

```
john --wordlist=~/rockyou.txt md5hash.txt
john --wordlist=~/rockyou.txt sha1hash.txt
john --wordlist=~/rockyou.txt sha256hash.txt
```

After cracking, displayed the results:
```
john --show md5hash.txt
john --show sha1hash.txt
john --show sha256hash.txt
```
### Conclusion
This project has provided valuable insights into the vulnerabilities of weak passwords and the effectiveness of password-cracking tools like John the Ripper. Understanding these vulnerabilities reinforces the need for stronger password practices and contributes to enhanced cybersecurity measures.
