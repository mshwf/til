To create a self-signed certificate:

```
New-SelfSignedCertificate -DnsName "RootAuthority" -CertStoreLocation "cert:\LocalMachine\My" -NotAfter (Get-Date).AddYears(10) -FriendlyName "Root CA" -KeyUsageProperty All -KeyUsage CertSign, CRLSign, DigitalSignature
```

_Copy the Thumbprint from the output._

Create a password:
```
$mypwd = ConvertTo-SecureString -String "1234" -Force -AsPlainText
```

Export the certificate as PFX with the password:
```
Get-ChildItem -Path cert:\localMachine\my\<thumbprint you copied> | Export-PfxCertificate -FilePath "D:\Certs\RootCA.pfx" -Password $mypwd
```

To sign another certificate, get a reference of the RootCa:
```
$rootcert = (Get-ChildItem -Path cert:\LocalMachine\My\<thumbprint of the root CA>)
```

Sign the client certificate:
```
New-SelfSignedCertificate -certstorelocation cert:\localmachine\my -dnsname "MyCertificate" -Signer $rootcert -NotAfter (Get-Date).AddYears(10) -FriendlyName "My Certificate"
```
