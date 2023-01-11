**Get the ProcessorArchitecture of a dll assembly:**
```
[System.Reflection.Assemblyname]::GetAssemblyName($pathToDll).ProcessorArchitecture
```

**Delete bin & obj folders:**
```
 Get-ChildItem -Path "path-to-root-folder" .\ -include bin, obj -Recurse | ForEach-Object ($_) { remove-item $_.fullname -Force -Recurse }
```
