# ansible role for certificate creation

it create signed certificates for service
in additional this role can create root certificate and sign by it all service

# What need for usage _(minimum)_

## files

- (optional) root private key
- (optional) root public cert
- (optional) root csr record

## vars

- need_CA _this is true/false trigger, if no need self signed certificate, please change next vars to your cert_
  - ca_path.key _absolute path to root private key file at localhost_
  - ca_path.csr _absolute path to root csr file at localhost_
  - ca_path.pub _absolute path to root public certificate at localhost_




