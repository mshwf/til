### linking a port with ssl cert:


open tool:
PS C:\Windows\system32> netsh
netsh>http
netsh http><commands here>

add:

netsh http> add sslcert ipport=0.0.0.0:3050 certhash=19b2511ec44aeec4d39104746b94460e563554f6 appid={3CC2DB19-1933-486A-9B9F-5A6954ADF111}

delete:
netsh http> delete sslcert ipport=0.0.0.0:3050

Delete dev certs:

dotnet dev-certs https --clean
