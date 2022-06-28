**About OS**
```powershell
Get-WmiObject -Class win32_OperatingSystem | select Version,BuildNumber
systeminfo | find /i "OS Version"
```
---
from kali with rdp
```cmd
xfreerdp /f /u:USERNAME /p:PASSWORD /v:HOST[:PORT]
```
where /f full mode

---
**Show dir and files(aka ls)**
```cmd
dir
```
---
view text file
```cmd
type flag.txt
```
---
NTFS permissions
```powershell
icacls c:\windows
```
---
The resource access level is list after each user in the output. The possible inheritance settings are:

(CI): container inherit
(OI): object inherit
(IO): inherit only
(NP): do not propagate inherit
(I): permission inherited from parent container

---
Basic access permissions are as follows:

F : full access
D :  delete access
N :  no access
M :  modify access
RX :  read and execute access
R :  read-only access
W :  write-only access

---
grant the joe user full control over the directory
```powershell
icacls c:\users /grant joe:f
```
---
revoke permissions
```powershell
icacls c:\users /remove joe
```
---
find file
```powershell
Get-ChildItem C:\ -name -recurse flag.txt
```