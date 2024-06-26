This repository contains a proof of concept for determining the public RSA key from a pair of email messages which are signed with the same private key.

## Setup

Start by cloning this repository and navigating to the repository root directory.

```bash
cd sigs2rsa
```

### Install Python dependencies

```bash
pip3 install pycryptodome
pip3 install gmpy2
```

## Find public RSA keys from en email archive

These commands extract signed data (canonicalized headers) and signatures from each message in an email archive,
and searches for public RSA keys for pairs of messages with the same DKIM domain and selector.

Load mbox files and extract signed data and signatures to corresponding .datasig files:

```bash
python3 extract_signed_data.py --mbox-files inbox1.mbox inbox2.mbox
```

Find public RSA keys from the .datasig files

```bash
python3 find_public_keys.py --datasig-files inbox1.mbox.datasig inbox2.mbox.datasig
```

Run `python3 extract_signed_data.py --help` and `python3 find_public_keys.py --help` for more information.
