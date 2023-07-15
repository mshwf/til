To find if a specific port is being used:  
`Get-Process -Id (Get-NetTCPConnection -LocalPort 5000).OwningProcess`  
or:  
`netstat -ano | findstr :<PORT>`

To kill a process running on a port:  
`taskkill /PID <PID> /F`  
where `<pid>` is the last number in the netstat command

You can view a list of which ports are excluded from your user by running this command:  
`> netsh interface ipv4 show excludedportrange protocol=tcp`
