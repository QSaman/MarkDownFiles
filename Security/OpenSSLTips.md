# Checking for Expiry Date

Note that private and public keys don't have expiry date; only certificates have. Usually certificates are in X.509.

## Check Certificate Expiry Date

You can open certificate  file (the extension can be `crt`, `pem`, ...)  with a text editor or running the following command to see its expiry date:

```
openssl x509 -enddate -noout -in file.crt
```

For printing both start and  end date:

```
openssl x509  -startdate -enddate -noout -in file.crt
```

For more information run `man openssl-x509` or `openssl x509 -help`.

## CRL Text Format
 
If you want to see a CRL file (certificate revocation list) in text format and see its expiry date you must run the following command:

```
openssl crl -text -in crl.pem 
```
If you don't want to see the actual CRL, use the following command:

```
openssl crl -text -noout -in crl.pem
```

For more information run `man openssl-crl` or `openssl crl -help`.
