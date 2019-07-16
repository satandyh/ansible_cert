# ansible role for mTLS certificate creation

it create signed certificates for service

also it can create root CA certificate and sign by it all your service certificates. if you need root cert just change `need_CA` variable to true and insert necessary values into `ca_csr` object.

# What need for usage _(minimum)_

## files

_If you have root CA cert. Put absolute path to your CA credentials at localhost. If you have no any root cert - let them default_

- ca_path.key _root private key_
- ca_path.pub _root public cert_
- ca_path.csr _(Optional) root csr record_

## vars

- need_CA _true/false trigger_
- service_name _name for your service at remote host_
- service_owner _files owner at remote host_
- service_group _files group at remote host_

- service_path.key _path to private key at remote host_
- service_path.pub _path to certificate at remote host_
- service_path.csr _(Optional) path to csr file at remote host_
- service_path.chain _path to chain bundle at remote host_

service_csr.cn _common name_
service_csr.c _country_
service_csr.e _email_
service_csr.o _organization name_
service_csr.ou _organization unit_

## Note

All credential files will have name like **service_name**.key/csr/crt.

All created certificates will work only at remote host with the same fqdn/ip names. Because we play in mTLS.

All created certificates will have only client/server authentification possibilities.

