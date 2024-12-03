# Descritpion

This role deploys certificates from Vault to `/certs` directory.

# Configuration

```yaml
deploy_certs_domains: ['example.org']
```

This would search for the following attachments in `certs/example.org`:
```
cert.ca-bundle
cert.crt
cert.key
```
And would deploy those under `/certs/example.org`:
```
 > find /certs/example.org
/certs/example.org
/certs/example.org/bundle.crt
/certs/example.org/cert.ca-bundle
/certs/example.org/cert.crt
/certs/example.org/cert.key
```
The `bundle.crt` is created by combining `cert.crt` and `cert.ca-bundle`.
