---
id: 40e488b6-0a6b-453c-a7f3-b0703749d122
title: Powershell
desc: ''
updated: 1611632654259
created: 1610647331652
sources:
  - name: ""
    url: "https://mathieubuisson.github.io/powershell-linux-bash/"
    license: ""
---

## Unix equivalent

### ls
- dir or `ls`

### cat 
- Get-Content

### setting env

```
$Env:<variable-name> = "<new-value>"
```

### tee

```
Tee-Object -FilePath "C:\Test1\testfile2.txt"
```

### rm

```powershell
Remove-Item -Recurse -Force
```

### kill

```powershell
Stop-process -Id 8464
```

# cook

### process running on port

```powershell
Get-Process -Id (Get-NetTCPConnection -LocalPort YourPortNumberHere).OwningProcess
```