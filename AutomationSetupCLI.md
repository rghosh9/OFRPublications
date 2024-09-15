## Automation setup with Command line interface for research (DRAFT - In development)

This page discusses the key items 

Public API key to use 
<pre><code>-----BEGIN PUBLIC KEY-----
MIIBIjANBgkqhkiG9w0BAQEFAAOCAQ8AMIIBCgKCAQEA7I6Rmqlm0I60Ehz1WjbE
GcK8PfqljMZpOxSxXOhFf0NsHcqJMYnCbwhlJSSzhs/mohZkgMkbPr8Xd/iNeJSR
62Pk94TcfRnbLDTW+DCkhSYvTdVgjEQVzKBRgWi6GTdEnq6tYMcN68kIjdq75OSN
fol+JnkF2v3LxE2bdinkzUC21QMd5zhGgaoa4AmTeRWbD32P4oZ3sIF4Pt0T+MIj
AvIQ+VU6i+2C/5VO2dYUurseTH5axd90WKopq3ScXVCZeQJY1XQy8MLsSVVK2k6B
S7mfb62t1+bXkSev04gAT9opHbTspDf+YfDx0xPDU2yrUZ0M2hVm1J9fcS/1jUZS
RQIDAQAB
-----END PUBLIC KEY-----</code></pre>

Once done you should get the following fingerprint 
<pre><code>7e:e1:e0:d3:7d:a5:f7:99:1e:97:16:d1:dc:41:f2:58</code></pre>

1. However, for security purposes, it is recommended to generate a public key pair and create your own API key for security. 
2. The keys should be created in pem format and should be added through the OCI CLI console to 

#### Getting the image 

#### Generating a SSH public / private key pair 
1. Option 1: (Easiest way) Try to spin up a compute instance and download the public and private SSH and cut/paste it to update the file in the pem format.
2. Option 2: Generate your own public / private key pair and use this

#### Getting the key attributes from your tenancy 
Copy the OCID for the following components and keep in your notepad:
1. User: Profile (right top corner) --> User settings --> Copy the User OCID
2. Tenancy: Profile (right top corner) --> Tenancy --> Copy the tenancy OCID
3. API fingerprint: Profile (right top corner) --> User settings --> API Key --> fingerprint

#### OCI CLI configuration
Edit the file ~/.oci/config (use a editor i,e vi or nano of your choice) to edit and fill in the user, fingerprint, tenancy, region
Edit the oci_api_key.pem and oci_api_key_public.pem files to include your private and public keys respectively

#### Passphrase
1. Default passphrase is set to research. You can change it to your passphrase for OCI

#### Testing OCI CLI 
Run the following code and if it outputs a json, you should be all set
<pre><code>$oci os ns get
Private key passphrase:
{
  "data": "ideqbfsd51fu"
}<code></pre> 
