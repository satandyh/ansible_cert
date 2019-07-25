# ansible role for mTLS certificate creation

This repo create signed certificates for service that You specify.

also it can create root CA certificate and sign by it all your service  
certificates. if you need root cert just change `need_CA` variable to true  
and insert necessary values into `ca_csr` object.

# What is needed for usage _(minimum)_

## files

If you have root CA cert. Put absolute path to your CA credentials at  
localhost. If you have no any root cert - let them default

- **ca_path.key** root private key
- **ca_path.pub** root public cert
- **ca_path.csr** (Optional) root csr record

## vars

- **need_CA** true/false trigger
- **service_name** name for your service at remote host
- **service_owner** files owner at remote host
- **service_group** files group at remote host

- **service_path.key** path to private key at remote host
- **service_path.pub** path to certificate at remote host
- **service_path.csr** (Optional) path to csr file at remote host
- **service_path.chain** path to chain bundle at remote host

- **service_csr.cn** common name
- **service_csr.c** country
- **service_csr.e** email
- **service_csr.o** щrganization name
- **service_csr.ou** organization unit

> ## Note
>
> All credential files will have name like **service_name**.key/csr/crt.  
> All created certificates will work only at remote host with the same  
> fqdn/ip names. Because we play in mTLS.  
> All created certificates will have only client/server authentification  
> possibilities.
