# ផ្នែកទី ១៖ ខ្លឹមសារមេរៀន និងនិយមន័យសំខាន់ៗ (Lesson Contents & Key Definitions)

### ១. មេរៀនទី ១៖ ការដំឡើង Windows Server 2016 (Install Windows Server 2016)
* **Evaluation Version:** គឺជាជំនាន់សាកល្បងប្រើប្រាស់របស់ Windows Server 2016 ដែលអនុញ្ញាតឱ្យប្រើប្រាស់បានរយៈពេល **១៨០ ថ្ងៃ**។
* **Datacenter with Graphical Management Tools (Desktop Experience):** គឺជាជម្រើសនៃការដំឡើងប្រព័ន្ធប្រតិបត្តិការ Windows Server ដែលមានបង្ហាញផ្ទាំងរូបភាព Graphic (Desktop GUI) សម្រាប់សម្រួលដល់ការគ្រប់គ្រង។
* **Custom: Install Windows only (advanced):** គឺជាជម្រើសនៃការដំឡើងប្រព័ន្ធប្រតិបត្តិការថ្មីស្រឡាង (Clean Installation) ទៅលើ Partition ឬ Disk នៃម៉ាស៊ីន Server។
* **Administrator Password:** ត្រូវបានកំណត់ភ្លាមៗបន្ទាប់ពីការដំឡើងប្រព័ន្ធប្រតិបត្តិការ និងការ Restart ម៉ាស៊ីនរួចរាល់ ដើម្បីប្រើសម្រាប់ Sign-in ចូលប្រព័ន្ធ។

### ២. មេរៀនទី ២៖ ការកំណត់ដំបូង (Initial Settings)
* **Add Local User:** ការបន្ថែមអ្នកប្រើប្រាស់ក្នុងស្រុក (Local User) ធ្វើឡើងតាមរយៈ **Server Manager** -> **Tools** -> **Computer Management** -> **Local Users and Groups** -> **Users**។ ប្រសិនបើចង់ផ្ដល់សិទ្ធិជាអ្នកគ្រប់គ្រង ត្រូវបន្ថែម User នោះចូលទៅក្នុង Group **Administrators**។
* **Change Admin User Name:** ការប្តូរឈ្មោះ Account "Administrator" ទៅជាឈ្មោះផ្សេងទៀត ធ្វើឡើងដើម្បីពង្រឹងសុវត្ថិភាពម៉ាស៊ីន Server។
* **Computer Name & Domain Suffix:** ឈ្មោះកុំព្យូទ័រត្រូវតែផ្លាស់ប្តូរចេញពីឈ្មោះលំនាំដើមរបស់ប្រព័ន្ធ ហើយអាចកំណត់ Primary DNS Suffix (ដូចជា `srv.world`) រួចតម្រូវឱ្យ Restart កុំព្យូទ័រដើម្បីអនុវត្តការផ្លាស់ប្តូរ។
* **Static IP Address:** ការកំណត់អាសយដ្ឋាន IP បែបអចិន្ត្រៃយ៍ (Static IPv4) លើកាតបណ្តាញ (Ethernet) ជំនួសឱ្យការទទួល IP ពី DHCP ដើម្បីធានាថាអាសយដ្ឋាន Server មិនប្រែប្រួល។
* **Windows Update Policy:** អាចកំណត់រចនាសម្ព័ន្ធបច្ចុប្បន្នភាព Windows តាមរយៈ Local Group Policy Editor (`gpedit.msc`) ក្រោមផ្លូវ `Administrative Templates` -> `Windows Components` -> `Windows Update`۔
* **Allow ICMP Echo Reply (Ping):** តាមលំនាំដើម Windows Firewall នឹង Block កញ្ចប់ទិន្នន័យ ICMP។ ដើម្បីអនុញ្ញាតឱ្យគេអាច Ping មកកាន់ Server បាន ត្រូវបង្កើត **Inbound Rule** ថ្មីប្រភេទ **Custom Rule** សម្រាប់ Protocol **ICMPv4** នៅក្នុង Windows Firewall with Advanced Security។

### ៣. មេរៀនទី ៣៖ ការកំណត់ NTP Server (Configure NTP Server)
* **NTP (Network Time Protocol) Server:** គឺជាសេវាកម្មសម្រាប់ធ្វើស៊ីសង្វាក់ពេលវេលា (Time Synchronization) រវាងម៉ាស៊ីន Server និង Clients នៅក្នុងបណ្តាញ។
* **Workgroup vs Active Directory Environment:** ប្រសិនបើ Server ជា Active Directory Domain Controller (DC) នោះសេវាកម្ម NTP ត្រូវបានបើកដំណើរការដោយស្វ័យប្រវត្តិ។ ប៉ុន្តែនៅក្នុងបរិស្ថាន Workgroup ត្រូវកំណត់បើក `Enabled = 1` ក្នុង Registry និងកំណត់ `AnnounceFlags = 5` តាមរយៈ PowerShell។
* **NTP Port:** សេវាកម្ម NTP ប្រើប្រាស់ Protocol **UDP Port 123** ដែលត្រូវអនុញ្ញាតនៅក្នុង Windows Firewall។
* **w32tm Tool:** គឺជា Command-line tool សម្រាប់ពិនិត្យ និងបញ្ជាការធ្វើ Time Synchronization លើ NTP Client/Server (ដូចជា `w32tm /query /source`, `w32tm /resync`, `w32tm /query /status`)។

### ៤. មេរៀនទី ៤៖ សេវាកម្ម OpenSSH (OpenSSH Services)
* **OpenSSH:** គឺជាសេវាកម្មដែលអនុញ្ញាតឱ្យធ្វើការបញ្ជា និងគ្រប់គ្រង Server ពីចម្ងាយតាមរយៈបណ្តាញដោយមានសុវត្ថិភាព (Encrypted Remote Management) តាម **Port 22/TCP**។
* **OpenSSH Installation:** ធ្វើឡើងដោយ Extract កញ្ចប់ Zip ទៅកាន់ផ្លូវ (ឧទាហរណ៍ `C:\Windows\OpenSSH-Win64`), បន្ថែម PATH ទៅកាន់ Environment Variables និងរ៉ាន់ Script `.\install-sshd.ps1` តាម PowerShell។
* **Key-Pair Authentication:** យន្តការផ្ទៀងផ្ទាត់ភាពត្រឹមត្រូវដោយប្រើប្រាស់សោគូ (Public/Private Key)។ សោ Public ត្រូវផ្លាស់ប្តូរឈ្មោះទៅជា `authorized_keys` នៅក្នុងថត `.ssh`។ សិទ្ធិ `Everyone:(RX)` លើឯកសារនេះត្រូវតែដកចេញតាមបញ្ជា `icacls authorized_keys /remove Everyone` ដើម្បីឱ្យការ Authenticate ដំណើរការ។
* **Default Shell:** តាមលំនាំដើម OpenSSH ប្រើប្រាស់ Command Prompt (`cmd.exe`) ប៉ុន្តែអាចប្តូរទៅប្រើ **PowerShell** ជា Default Shell បានតាមរយៈការប្រកាសក្នុង Registry Entry។

### ៥. មេរៀនទី ៥៖ Remote Desktop Server (RDS)
* **Remote Desktop (Single Session):** អនុញ្ញាតឱ្យតភ្ជាប់អេក្រង់បញ្ជាពីចម្ងាយមកកាន់ Server បានមួយ Session ក្នុងពេលតែមួយ តាមរយៈកម្មវិធី Client `mstsc`។
* **Remote Desktop Services (RDS):** ផ្ដល់សមត្ថភាពឱ្យ Clients ច្រើនអាចតភ្ជាប់មកកាន់ Server ក្នុងពេលតែមួយបាន (Multi-session Environment)។
* **RDS Role Services:**
  * **RD Connection Broker:** ធ្វើការតភ្ជាប់ ឬតភ្ជាប់ឡើងវិញនូវ Client Devices ទៅកាន់ RemoteApp ឬ Desktops។
  * **RD Web Access:** អនុញ្ញាតឱ្យ Users ចូលប្រើប្រាស់ RemoteApp និង Desktops តាមរយៈ Web Browser (ផ្លូវ `https://(Server_IP)/RdWeb/`)។
  * **RD Session Host:** ធ្វើជា Host សម្រាប់ផ្ទុក និងដំណើរការ RemoteApp programs ឬ Session-based desktops។
* **Session Collection:** បណ្តុំនៃការគ្រប់គ្រង និងបែងចែកសិទ្ធិអំណាចប្រើប្រាស់ Remote Desktop ទៅឱ្យ Users ឬ Groups។
* **RemoteApp:** ការប្រកាសផ្សាយ (Publish) កម្មវិធីឯកត្តជន (ដូចជា Server Manager) ឱ្យ Users ដំណើរការតាមចម្ងាយដោយបង្ហាញតែបង្អួចកម្មវិធី មិនបង្ហាញផ្ទាំង Desktop ទាំងមូលឡើយ។

### ៦. មេរៀនទី ៦៖ DNS Server (Domain Name System)
* **DNS Server:** គឺជាសេវាកម្មសម្រាប់បកប្រែឈ្មោះ Hostname ទៅជាអាសយដ្ឋាន IP Address ឬបកប្រែ IP Address មកជា Hostname វិញ។
* **Forward Lookup Zone:** គឺជា Zone សម្រាប់បកប្រែពី **DNS Name (Hostname) ទៅជា IP Address**។
* **Reverse Lookup Zone:** គឺជា Zone សម្រាប់បកប្រែពី **IP Address ទៅជា DNS Name (Hostname)**។
* **ប្រភេទព័ត៌មានត្រា DNS (Resource Records):**
  * **A Record (Host):** ត្រាសម្រាប់ភ្ជាប់ Hostname ទៅកាន់អាសយដ្ឋាន IPv4។
  * **PTR Record (Pointer):** ត្រាសម្រាប់ភ្ជាប់ IP Address ទៅកាន់ Hostname នៅក្នុង Reverse Lookup Zone។
  * **MX Record (Mail Exchanger):** ត្រាកំណត់ម៉ាស៊ីន Mail Server សម្រាប់ប្រើប្រាស់ក្នុង Domain។
  * **CNAME Record (Canonical Name):** ត្រាកំណត់ឈ្មោះជំនួស (Alias Name) ទៅឱ្យ A-Record ដែលមានស្រាប់។
* **nslookup:** គឺជាឧបករណ៍ Command-line សម្រាប់ធ្វើតេស្ត និងផ្ទៀងផ្ទាត់ការបកប្រែឈ្មោះ ឬ IP របស់ DNS Server។

### ៧. មេរៀនទី ៧៖ DHCP Server (Dynamic Host Configuration Protocol)
* **DHCP Server:** គឺជាសេវាកម្មសម្រាប់ចែករំលែក ឬជួលអាសយដ្ឋាន IP Address, Subnet Mask, Default Gateway, និង DNS Server ទៅឱ្យកុំព្យូទ័រ Client នៅក្នុងបណ្តាញដោយស្វ័យប្រវត្តិ។
* **AD DS Authorization:** ម៉ាស៊ីន DHCP Server នៅក្នុងបរិស្ថាន Active Directory ត្រូវតែទទួលបានការប្រគល់សិទ្ធិ (Authorize) នៅក្នុង AD DS ជាមុនសិន ទើបអាចដំណើរការបាន។
* **DHCP Scope:** ការកំណត់ជួរអាសយដ្ឋាន IP (IP Address Range), ការដកចេញនូវ IP មិនឱ្យចែក (Exclusions), រយៈពេលជួល (Lease Duration), Default Gateway, និង DNS Server សម្រាប់បណ្តាញ Local។

### ៨. មេរៀនទី ៨៖ Active Directory Domain Services (AD DS)
* **AD DS (Active Directory Domain Services):** គឺជាសេវាកម្មបញ្ជីឈ្មោះកណ្តាលសម្រាប់រក្សាទុក និងគ្រប់គ្រងព័ត៌មាន Objects ទាំងអស់ក្នុងបណ្តាញ ដូចជា Users, Groups, Computers, និង Organizational Units (OU)។
* **Domain Controller (DC):** គឺជា Server ដែលដំណើរការតួនាទី AD DS និងគ្រប់គ្រងដែនសមត្ថកិច្ច (Domain)។
* **Forest & Domain Functional Level:** កម្រិតមុខងាររបស់ Forest និង Domain ដែលកំណត់ពីភាពត្រូវគ្នានៃប្រព័ន្ធប្រតិបត្តិការ (ឧទាហរណ៍៖ Windows Server 2016)។
* **Directory Services Restore Mode (DSRM) Password:** ពាក្យសម្ងាត់ពិសេសសម្រាប់ប្រើប្រាស់នៅពេលស្ដារទិន្នន័យ Active Directory۔
* **Organizational Unit (OU):** គឺជាថតរៀបចំឋានានុក្រមនៅក្នុង Active Directory សម្រាប់ផ្ទុក Users, Groups, និង Computers ដើម្បីងាយស្រួលគ្រប់គ្រង និងដាក់ Group Policy។
* **Batch User Creation:** ការបន្ថែម User Accounts ច្រើនក្នុងពេលតែមួយដោយប្រើប្រាស់ Batch file (`.bat`) រួមជាមួយបញ្ជា `dsadd user`។
* **Password Complexity Policy:** គោលការណ៍ពង្រឹងភាពស្មុគស្មាញនៃពាក្យសម្ងាត់ ដែលអាចបិទបណ្តោះអាសន្នតាមរយៈ **Group Policy Management** (`gpedit.msc` ឬ `Default Domain Policy`) ពេលបង្កើត Users ជា Batch។
* **Join Domain from Client:** ការបញ្ជូលម៉ាស៊ីន Client ឱ្យចូលជាសមាជិក Domain ដោយត្រូវកំណត់ DNS របស់ Client ឱ្យចង្អុលមក IP របស់ AD DS Server ជាមុនសិន។

---

# ផ្នែកទី ២៖ កូដ និងពាក្យបញ្ជាសំខាន់ៗ (Key Commands & Scripts)

### ១. ការកំណត់ NTP Server (PowerShell)
```powershell
# ១. ពិនិត្យការកំណត់ NTP Server បច្ចុប្បន្ន
Get-ItemProperty -Path "HKLM:\SYSTEM\CurrentControlSet\Services\w32time\TimeProviders\NtpServer"

# ២. បើកដំណើរការ NTP Server
Set-ItemProperty -Path "HKLM:\SYSTEM\CurrentControlSet\Services\w32time\TimeProviders\NtpServer" -Name "Enabled" -Value 1

# ៣. កំណត់ AnnounceFlags ទៅជា 5 (Reliable Time Server)
Set-ItemProperty -Path "HKLM:\SYSTEM\CurrentControlSet\services\W32Time\Config" -Name "AnnounceFlags" -Value 5

# ៤. Restart សេវាកម្ម Windows Time
Restart-Service w32Time

# ៥. បើក Firewall Port 123/UDP សម្រាប់ NTP
New-NetFirewallRule -Name "NTP Server Port" -DisplayName "NTP Server Port" -Description 'Allow NTP Server Port' -Profile Any -Direction Inbound -Action Allow -Protocol UDP -LocalPort 123

# ៦. ពិនិត្យប្រភព Time Sync និងធ្វើ Sync ឡើងវិញ
w32tm /query /source
w32tm /resync
w32tm /query /status
```

### ២. ការដំឡើង និងកំណត់ OpenSSH (PowerShell)
```powershell
# ១. ដំឡើងសេវាកម្ម sshd
cd C:\Windows\OpenSSH-Win64
.\install-sshd.ps1

# ២. កំណត់សិទ្ធិឯកសារ Host
.\FixHostFilePermissions.ps1

# ៣. បើក Firewall Port 22/TCP សម្រាប់ SSH
New-NetFirewallRule -Name "OpenSSH-Server-In-TCP" -DisplayName "OpenSSH Server (Inbound)" -EventCmd -Protocol TCP -LocalPort 22 -Action Allow

# ៤. បង្កើត SSH Key-Pair និងកំណត់សិទ្ធិ
ssh-keygen
cd .ssh
mv id_rsa.pub authorized_keys
icacls authorized_keys /remove Everyone

# ៥. កំណត់ PowerShell ជា Default Shell របស់ OpenSSH ក្នុង Registry
New-ItemProperty -Path "HKLM:\SOFTWARE\OpenSSH" -Name DefaultShell -Value "C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe" -PropertyType String -Force
```

### ៣. កូដ Batch Script សម្រាប់បង្កើត Users ច្រើនក្នុង Active Directory (`adduser.bat`)
* **ឯកសារអត្ថបទ `users.txt`:**
  ```text
  Redhat Linux
  Fedora Linux
  Ubuntu Xenial
  Debian Stretch
  ```
* **ឯកសារ `adduser.bat`:**
  ```batch
  @echo off
  set USERLIST=users.txt
  set OU=OU=Development01,OU=Hiroshima
  set DC=DC=srv,DC=world
  for /f "tokens=1,2" %%i in (%USERLIST%) do (
  dsadd user CN=%%i,%OU%,%DC% -pwd %%i%%j -mustchpwd yes ^
  -ln %%i -fn %%j -email %%i@srv.world -display "%%i %%j"
  )
  PAUSE
  ```

---

# ផ្នែកទី ៣៖ កម្រងសំណួរ និងលំហាត់សម្រាប់ប្រឡង (Exam Questions)

## ប្រភេទទី ១៖ សំណួរជ្រើសរើសចម្លើយ (Multiple Choice Questions)

**សំណួរ ១៖ តើកែប្រែកំណត់រចនាសម្ព័ន្ធ Windows Update តាម Group Policy ត្រូវរ៉ាន់បញ្ជាអ្វីនៅក្នុងប្រអប់ Run?**
A. `sysdm.cpl`  
B. `gpedit.msc`  
C. `services.msc`  
D. `secpol.msc`  
* **ចម្លើយត្រឹមត្រូវ៖ B**

**សំណួរ ២៖ តើសេវាកម្ម NTP Server ប្រើប្រាស់ Protocol និង Port មួយណាសម្រាប់ការប្រស្រ័យទាក់ទងតាមបណ្តាញ?**
A. TCP Port 80  
B. TCP Port 22  
C. UDP Port 123  
D. UDP Port 53  
* **ចម្លើយត្រឹមត្រូវ៖ C**

**សំណួរ ៣៖ តើស្តង់ដារ Port លំនាំដើមរបស់សេវាកម្ម OpenSSH គឺ Port ប៉ុន្មាន?**
A. Port 21/TCP  
B. Port 22/TCP  
C. Port 3389/TCP  
D. Port 80/TCP  
* **ចម្លើយត្រឹមត្រូវ៖ B**

**សំណួរ ៤៖ បន្ទាប់ពី உருவாக்கឯកសារ `authorized_keys` សម្រាប់ SSH Key-Pair Authenticate តើត្រូវប្រើប្រាស់បញ្ជា `icacls` អ្វីដើម្បីដកសិទ្ធិ Everyone ចេញ?**
A. `icacls authorized_keys /grant Everyone`  
B. `icacls authorized_keys /remove Everyone`  
C. `icacls authorized_keys /deny Everyone`  
D. `icacls authorized_keys /delete`  
* **ចម្លើយត្រឹមត្រូវ៖ B**

**សំណួរ ៥៖ តើកម្មវិធី Client ស្ដង់ដាររបស់ Windows សម្រាប់តភ្ជាប់ Remote Desktop គឺអ្វី?**
A. `ssh`  
B. `sftp`  
C. `mstsc`  
D. `nslookup`  
* **ចម្លើយត្រឹមត្រូវ៖ C**

**សំណួរ ៦៖ តើផ្លូវ URL ស្ដង់ដារសម្រាប់ចូលប្រើប្រាស់ RemoteApp តាមរយៈ RD Web Access គឺមួយណា?**
A. `http://(Server_IP)/RemoteApp`  
B. `https://(Server_IP)/RdWeb/`  
C. `https://(Server_IP)/RemoteDesktop`  
D. `ftp://(Server_IP)/RdWeb`  
* **ចម្លើយត្រឹមត្រូវ៖ B**

**សំណួរ ៧៖ តើប្រភេទ DNS Resource Record មួយណាដែលប្រើសម្រាប់បកប្រែពី IP Address ទៅជា Hostname នៅក្នុង Reverse Lookup Zone?**
A. A Record  
B. MX Record  
C. CNAME Record  
D. PTR Record  
* **ចម្លើយត្រឹមត្រូវ៖ D**

**សំណួរ ៨៖ តើ Command-line tool មួយណាដែលប្រើប្រាស់សម្រាប់ធ្វើតេស្ត និងផ្ទៀងផ្ទាត់ការបកប្រែឈ្មោះ ឬ IP Address របស់ DNS Server?**
A. `ping`  
B. `ipconfig`  
C. `nslookup`  
D. `tracert`  
* **ចម្លើយត្រឹមត្រូវ៖ C**

**សំណួរ ៩៖ ដើម្បីឱ្យ DHCP Server អាចដំណើរការ និងចែក IP នៅក្នុង Active Directory Domain បាន តើត្រូវធ្វើអ្វីជាចាំបាច់ជាមុនសិន?**
A. ត្រូវបិទ Windows Firewall  
B. ត្រូវធ្វើការ Authorize ម៉ាស៊ីន DHCP នៅក្នុង AD DS  
C. ត្រូវកំណត់ IP ទៅជា Dynamic  
D. ត្រូវលុប Scope ចាស់ចោល  
* **ចម្លើយត្រឹមត្រូវ៖ B**

**សំណួរ ១០៖ តើពាក្យបញ្ជា Command-line មួយណាដែលត្រូវប្រើប្រាស់នៅក្នុង Batch file សម្រាប់បង្កើត User Account ចូលទៅក្នុង Active Directory?**
A. `net user add`  
B. `dsadd user`  
C. `adadd user`  
D. `useradd`  
* **ចម្លើយត្រឹមត្រូវ៖ B**

---

## ប្រភេទទី ២៖ សំណួរសរសេរ និងដោះស្រាយកូដ (Structured & Command Questions)

**សំណួរ ១៖** ចូររៀបរាប់ពីជំហាននៃការអនុាតឱ្យកញ្ចប់ទិន្នន័យ Ping (ICMP Echo Reply) ឆ្លងកាត់ Windows Firewall តាមរយៈ Windows Firewall with Advanced Security។
* **ចម្លើយ៖**
  1. បើក **Server Manager** -> **Tools** -> **Windows Firewall with Advanced Security**។
  2. ចុចលើ **Inbound Rules** ហើយជ្រើសរើស **New Rule...**។
  3. ជ្រើសរើសប្រភេទ Rule ជា **Custom** រួចចុច Next។
  4. ជ្រើសរើស **All programs**។
  5. ត្រង់ Protocol type ជ្រើសយក **ICMPv4**។
  6. កំណត់ជួរ Network Range ដែលអនុញ្ញាត។
  7. ជ្រើសយក **Allow the connection** និងជ្រើសរើស Profile រួចដាក់ឈ្មោះ Rule (ឧទាហរណ៍ `ICMPv4`) ជាការស្រេច។

**សំណួរ ២៖** ចូរសរសេរពាក្យបញ្ជា PowerShell សម្រាប់៖
1. កំណត់តម្លៃ `AnnounceFlags` ទៅជា `5` សម្រាប់ NTP Server។
2. បង្កើត Firewall Rule ថ្មីសម្រាប់អនុញ្ញាត NTP Port (UDP 123)។
* **ចម្លើយ៖**
  1. `Set-ItemProperty -Path "HKLM:\SYSTEM\CurrentControlSet\services\W32Time\Config" -Name "AnnounceFlags" -Value 5`
  2. `New-NetFirewallRule -Name "NTP Server Port" -DisplayName "NTP Server Port" -Description 'Allow NTP Server Port' -Profile Any -Direction Inbound -Action Allow -Protocol UDP -LocalPort 123`

**សំណួរ ៣៖** ចូរពន្យល់ពីតួនាទីរបស់ RDS Role Services ទាំង ៣៖ **RD Connection Broker**, **RD Web Access**, និង **RD Session Host**។
* **ចម្លើយ៖**
  * **RD Connection Broker:** ធ្វើការតភ្ជាប់ ឬតភ្ជាប់ឡើងវិញនូវ Client Devices ទៅកាន់ RemoteApp ឬ Desktops។
  * **RD Web Access:** ផ្តល់ការចូលប្រើប្រាស់ RemoteApp/Desktops តាមរយៈ Web Browser។
  * **RD Session Host:** ធ្វើជា Host ផ្ទុក និងដំណើរការកម្មវិធី RemoteApp ឬ Session-based Desktops ជាក់ស្តែង។

**សំណួរ ៤៖** ចូរបកស្រាយពីភាពខុសគ្នារវាង **Forward Lookup Zone** និង **Reverse Lookup Zone** នៅក្នុង DNS Server។
* **ចម្លើយ៖**
  * **Forward Lookup Zone:** ប្រើប្រាស់សម្រាប់បកប្រែពី **DNS Name (Hostname) ទៅជា IP Address**។
  * **Reverse Lookup Zone:** ប្រើប្រាស់សម្រាប់បកប្រែពី **IP Address ទៅជា DNS Name (Hostname)**។

**សំណួរ ៥៖** ចូរសរសេរកូដ Batch Script (`.bat`) សម្រាប់ទាញយកឈ្មោះ User ចេញពី `users.txt` រួចបង្កើត User នោះចូលទៅក្នុង OU ឈ្មោះ `Development01` ដែលស្ថិតក្រោម OU `Hiroshima` នៃ Domain `srv.world` ដោយកំណត់ Password ភ្លាមៗស្មើនឹងឈ្មោះដើម និងតម្រូវឱ្យប្តូរ Password ពេល Logon លើកដំបូង។
* **ចម្លើយ៖**
  ```batch
  @echo off
  set USERLIST=users.txt
  set OU=OU=Development01,OU=Hiroshima
  set DC=DC=srv,DC=world
  for /f "tokens=1,2" %%i in (%USERLIST%) do (
  dsadd user CN=%%i,%OU%,%DC% -pwd %%i%%j -mustchpwd yes ^
  -ln %%i -fn %%j -email %%i@srv.world -display "%%i %%j"
  )
  PAUSE
  ```

---
💡 **តើលោកគ្រូ/អ្នកគ្រូ ចង់ឱ្យខ្ញុំរៀបចំកម្រងមេរៀន និងសំណួរប្រឡង Windows Server 2016 នេះបន្ថែមជាទម្រង់ណាទៀតដែរឬទេ?**
