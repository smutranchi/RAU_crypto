# RAU_crypto
[![Language](https://img.shields.io/badge/Lang-Python-blue.svg)](https://www.python.org)

Hard-coded encryption key remote file upload exploit for CVE-2017-11317, CVE-2017-11357 (Telerik UI for ASP.NET AJAX). Allows for straightforward decryption and encryption of the rauPostData used with Telerik.Web.UI.WebResource.axd?type=rau and resulting in arbitrary file uploads. The exploit will automatically upload the file.

## Requirements
- python >= 3.6 with pycryptodome (https://blog.sqreen.io/stop-using-pycrypto-use-pycryptodome/)

## Published on exploit-db
- https://www.exploit-db.com/exploits/43874/

## See also

My other Telerik UI exploit (for CVE-2017-9248) will probably also be of interest. It is available here:
- https://github.com/bao7uo/dp_crypto

## To do
- [x] Missing HMAC functionality for later versions.
- [ ] Brute force versions.

## Vulnerabilities
The CVE-2017-11317 vulnerability was discovered by others. Shortly after it was announced, I encountered the Telerik library during the course of my work, so I researched it and the vulnerability and wrote this exploit in July 2017. I also reported CVE-2017-11357 for the related insecure direct object reference.

https://www.telerik.com/support/kb/aspnet-ajax/upload-%28async%29/details/insecure-direct-object-reference

## Usage
```
$ ./RAU_crypto_py3.py 

RAU_crypto by Paul Taylor / Foregenix Ltd.
CVE-2017-11317 - Telerik RadAsyncUpload hardcoded keys / arbitrary file upload

Usage:

Decrypt a plaintext:      -d ciphertext
Decrypt rauPostData:      -D rauPostData
Encrypt a plaintext:      -e plaintext
Gen rauPostData:          -E TempTargetFolder Version
Gen rauPostData (quiet):  -Q TempTargetFolder Version
Version in HTTP response: -v url
Generate a POST payload:  -p TempTargetFolder Version filename
Upload a payload:         -P TempTargetFolder Version filename url

$

```

## Example - decryption
![Decrypt screenshot](images/decrypt_screenshot.png)

## Example - arbitrary file uplaod
![Upload screenshot](images/upload_screenshot.png)

