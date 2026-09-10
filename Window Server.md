នេះគឺជាខ្លឹមសារលម្អិតយ៉ាងពេញលេញនៃមេរៀននីមួយៗដែលដកស្រង់ចេញពីរវារៈសៀវភៅ **Windows Server 2016 (Part I)** ដែលបានរៀបចំឡើងជាភាសាខ្មែរ រួមមានទាំងការកំណត់ ប៉ារ៉ាម៉ែត្រ ជំហានអនុវត្ត និងកូដបញ្ជាជាក់ស្តែង៖

---

# មេរៀនទី ១៖ ការដំឡើង Windows Server 2016 (Install Windows Server 2016)

### I. ការទាញយកឯកសារ Windows Server 2016
* **ការទិញ និងការសាកល្បង៖** ប្រព័ន្ធប្រតិបត្តិការ Windows Server តម្រូវឱ្យទិញអាជ្ញាប័ណ្ណប្រើប្រាស់ ប៉ុន្តែ Microsoft អនុញ្ញាតឱ្យទាញយក **Evaluation Version** មកប្រើប្រាស់សាកល្បងបានរយៈពេល **១៨០ ថ្ងៃ** តាមរយៈការចុះឈ្មោះលើគេហទំព័រផ្លូវការ។
* **តំណភ្ជាប់ទាញយក៖** អាចទាញយកឯកសារ ISO នៃ Evaluation Version ចេញពីគេហទំព័រ Microsoft Eval Center។

### II. ជំហានដំឡើង Windows Server 2016
1. **ចាប់ផ្តើមដំឡើង (Boot Media)៖** ដាក់ថាស ឬប្រភពដំឡើង Windows Server ចូលទៅក្នុងកុំព្យូទ័រ ហើយចាប់ផ្តើមដំណើរការ (Boot) រួចចុចប៊ូតុង **[Next]** លើអេក្រង់កំណត់ភាសា និងកំណត់តំបន់។
2. **ចុច Install Now៖** ចុចលើប៊ូតុង **[Install Now]** ដើម្បីចាប់ផ្តើមការដំឡើង។
3. **ជ្រើសរើស Edition៖** ជ្រើសរើសប្រភេទជម្រើស Edition ដែលចង់ដំឡើង ឧទាហរណ៍៖ **Datacenter with Graphical Management Tools (Desktop Experience)** ដើម្បីទទួលបានផ្ទាំងប្រកៀកប្រកិត (GUI)។
4. **យល់ព្រមលើអាជ្ញាប័ណ្ណ (License Terms)៖** អានលក្ខខណ្ឌអាជ្ញាប័ណ្ណ រួចធីកប្រអប់ **[I accept the license terms]** ដើម្បីបន្តទៅមុខ។
5. **ជ្រើសរើសប្រភេទដំឡើង (Installation Type)៖** សម្រាប់ការដំឡើងប្រព័ន្ធប្រតិបត្តិការថ្មីស្រឡាង (Clean Installation) ត្រូវជ្រើសយក **[Custom: Install Windows only (advanced)]**។
6. **ជ្រើសរើស Partition៖** ជ្រើសរើស Partition ឬ Hard Disk ដែលត្រូវដំឡើង Windows Server រួចចុច [Next]។
7. **ដំណើរការដំឡើង៖** ប្រព័ន្ធនឹងចាប់ផ្តើមចម្លង និងដំឡើងឯកសារ ដោយក្នុងអំឡុងពេលនេះ ម៉ាស៊ីននឹង Reboot ចំនួនពីរ-បីដង។
8. **កំណត់ Administrator Password៖** បន្ទាប់ពី Reboot រួចរាល់ ប្រព័ន្ធនឹងតម្រូវឱ្យកំណត់ពាក្យសម្ងាត់សម្រាប់ Account **Administrator**។
9. **Sign-in ចូលប្រព័ន្ធ៖** ចុចបន្សំគ្រាប់ចុច **Ctrl + Alt + Del** រួចវាយបញ្ចូល Administrator Password ដើម្បីចូលទៅកាន់ផ្ទាំង Desktop នៃ Windows Server 2016។

---

# មេរៀនទី ២៖ ការកំណត់ដំបូង (Initial Settings)

### ១. ការបន្ថែម USER ក្នុងស្រុក (Add Local User)
1. បើក **Server Manager** -> ចូលទៅកាន់ **[Tools]** -> **[Computer Management]**។
2. នៅផ្ទាំងខាងឆ្វេង ចុចស្តាំលើ **[Users]** ក្រោមថត **[Local Users and Groups]** រួចជ្រើសយក **[New User]**។
3. វាយបញ្ចូល **UserName** និង **Password** សម្រាប់ User ថ្មី រួចចុចប៊ូតុង **[Create]**។
4. **ការផ្ដល់សិទ្ធិជា Administrator៖** ចុចស្តាំលើ User ដែលបានបង្កើត រួចជ្រើសយក **[Properties]** -> ចូលទៅកាន់ Tab **[Member of]** -> ចុច **[Add]** -> វាយបញ្ចូល **Administrators** រួចចុច [OK]។

### ២. ការប្តូរឈ្មោះ Administrator Account (Change Admin User Name)
1. បើក **Server Manager** -> **[Tools]** -> **[Computer Management]**។
2. ចូលទៅកាន់ **[Local Users and Groups]** -> **[Users]** -> ចុចស្តាំលើ **[Administrator]** រួចជ្រើសយក **[Rename]** ហើយប្តូរទៅជាឈ្មោះថ្មីណាមួយដើម្បីពង្រឹងសុវត្ថិភាព។

### ៣. ការប្តូរឈ្មោះកុំព្យូទ័រ (Change Computer Name & Primary DNS Suffix)
1. នៅក្នុង **Server Manager** ជ្រើសយក **[Local Server]** ផ្ទាំងខាងឆ្វេង រួចចុចលើផ្នែក **[Computer Name]** ផ្ទាំងខាងស្តាំ។
2. នៅក្នុង Tab **[Computer Name]** ចុចប៊ូតុង **[Change...]**។
3. វាយបញ្ចូលឈ្មោះកុំព្យូទ័រថ្មីក្នុងប្រអប់ **Computer name** រួចចុចប៊ូតុង **[More...]**។
4. វាយបញ្ចូលឈ្មោះ Domain Primary DNS Suffix ឧទាហរណ៍៖ `srv.world` រួចចុច [OK]។
5. ធ្វើការ **Restart កុំព្យូទ័រ** ដើម្បីអនុវត្តការផ្លាស់ប្តូរ។

### ៤. ការកំណត់អាសយដ្ឋាន IP បែប STATIC (Set Static IP Address)
1. នៅក្នុង **Server Manager** ជ្រើសយក **[Local Server]** -> ចុចលើផ្នែក **[Ethernet]**។
2. ចុចស្តាំលើ Icon **[Ethernet]** រួចជ្រើសយក **[Properties]**។
3. ជ្រើសយក **[Internet Protocol Version 4 (TCP/IPv4)]** រួចចុច **[Properties]**។
4. កំណត់ជ្រើសយក **"Use the following IP address"** រួចបញ្ចូល Static IP address, Subnet mask, និង Default Gateway សម្រាប់បណ្តាញ Local រួចចុច [OK]۔

### ៥. ការកំណត់រចនាសម្ព័ន្ធ Windows Update
1. បើកប្រអប់ **Run** (Win + R) រួចវាយបញ្ជា `gpedit.msc`។
2. ចូលទៅកាន់ផ្លូវ៖ **[Administrative Templates]** -> **[Windows Components]** -> **[Windows Update]**។
3. ចុចបើក **[Configure Automatic Updates]** ផ្ទាំងខាងស្តាំ រួចកំណត់រចនាសម្ព័ន្ធជ្រើសរើសជម្រើស Update តាមតម្រូវការ។

### ៦. ការអនុញ្ញាត ICMP Echo Reply (Allow ICMP / Ping Inbound Rule)
តាមលំនាំដើម Windows Firewall នឹង Block កញ្ចប់ទិន្នន័យ ICMP (ធ្វើឱ្យមិនអាច Ping ជួប Server បានឡើយ)៖
1. បើក **Server Manager** -> **[Tools]** -> **[Windows Firewall with Advanced Security]**។
2. ចុចលើ **[Inbound Rules]** ផ្ទាំងខាងឆ្វេង រួចចុច **[New Rule...]** ផ្ទាំងខាងស្តាំ។
3. ជ្រើសយកប្រភេទ **[Custom]** -> ចុច Next។
4. ជ្រើសយក **[All programs]** -> ចុច Next។
5. ត្រង់ **Protocol type** ជ្រើសយក **[ICMPv4]** -> ចុច Next។
6. កំណត់ជួរ Network IP ដែលអនុញ្ញាត (ឬទុក Any IP address) -> ចុច Next។
7. ជ្រើសយក **[Allow the connection]** -> ចុច Next។
8. ជ្រើសរើស Network Profiles (Domain, Private, Public) ដែលត្រូវអនុញ្ញាត -> ចុច Next។
9. វាយបញ្ចូលឈ្មោះ Rule ឧទាហរណ៍៖ `ICMPv4` រួចចុច [Finish]។

---

# មេរៀនទី ៣៖ ការកំណត់ NTP Server (Configure NTP Server)

ប្រសិនបើ Server ជា Active Directory Domain Controller (DC) សេវាកម្ម NTP ត្រូវបានបើកដំណើរការដោយស្វ័យប្រវត្តិ។ ខាងក្រោមជាការកំណត់សម្រាប់បរិស្ថាន **Workgroup**៖

### ១. ការកំណត់ NTP Server លើម៉ាស៊ីន Workgroup (PowerShell)
បើក **Windows PowerShell** ដោយសិទ្ធិ Admin រួចរ៉ាន់បញ្ជា៖
```powershell
# ពិនិត្យមើលការកំណត់ NtpServer បច្ចុប្បន្ន
Get-ItemProperty -Path "HKLM:\SYSTEM\CurrentControlSet\Services\w32time\TimeProviders\NtpServer"

# បើកដំណើរការសេវាកម្ម NTP Server (Enabled = 1)
Set-ItemProperty -Path "HKLM:\SYSTEM\CurrentControlSet\Services\w32time\TimeProviders\NtpServer" -Name "Enabled" -Value 1

# កំណត់ AnnounceFlags ទៅជា 5 (0x04 Always reliable + 0x01 Always time server)
Set-ItemProperty -Path "HKLM:\SYSTEM\CurrentControlSet\services\W32Time\Config" -Name "AnnounceFlags" -Value 5

# Restart សេវាកម្ម Windows Time
Restart-Service w32Time

# បើក Firewall សម្រាប់ NTP Port UDP 123
New-NetFirewallRule -Name "NTP Server Port" -DisplayName "NTP Server Port" -Description 'Allow NTP Server Port' -Profile Any -Direction Inbound -Action Allow -Protocol UDP -LocalPort 123
```

### ២. ការកំណត់ NTP Client
1. **ពិនិត្យប្រភព Time Sync បច្ចុប្បន្ន៖**
   ```powershell
   w32tm /query /source
   ```
2. **ផ្លាស់ប្តូរម៉ាស៊ីនគោល NTP Server ថ្មី (ឧទាហរណ៍៖ `ntp.nict.jp,0x8`)៖**
   ```powershell
   Set-ItemProperty -Path "HKLM:\SYSTEM\CurrentControlSet\Services\w32time\Parameters" -Name "NtpServer" -Value "ntp.nict.jp,0x8"
   Restart-Service w32Time
   w32tm /resync
   w32tm /query /status
   ```
3. **សម្រាប់ Active Directory Forest Root (ប្តូរពី Local CMOS Clock ទៅកាន់ Network NTP)៖**
   ```powershell
   # ប្តូរប្រភេទ Type ពី NT5DS ទៅជា NTP ជាមុនសិន
   Set-ItemProperty -Path "HKLM:\SYSTEM\CurrentControlSet\Services\w32time\Parameters" -Name "Type" -Value "NTP"
   ```

---

# មេរៀនទី ៤៖ សេវាកម្ម OpenSSH (OpenSSH Services)

### ១. ការដំឡើង OpenSSH Server និង Client
1. ទាញយកកញ្ចប់ Zip `OpenSSH-Win64.zip` ពី GitHub ផ្លូវការ។
2. ពន្លាត (Extract) ឯកសារ រួចដាក់ថតនោះនៅផ្លូវ `C:\Windows\OpenSSH-Win64`។
3. **បន្ថែម PATH ទៅ System Variables៖** បើក **System Properties** -> **[Environment Variables]** -> ត្រង់ **System variables** ជ្រើសយក **Path** -> ចុច [Edit...] -> ចុច [New] រួចបន្ថែមផ្លូវ `C:\Windows\OpenSSH-Win64`។
4. **ដំឡើងសេវាកម្ម sshd តាម PowerShell៖**
   ```powershell
   cd C:\Windows\OpenSSH-Win64
   .\install-sshd.ps1
   ```
5. **បើកដំណើរការ Service៖** ចូលទៅកាន់ `services.msc` -> ចុចស្តាំលើ **OpenSSH SSH Server** -> ប្តូរ **Startup Type** ទៅជា **Automatic** រួចចុច **Start**។
6. **កំណត់សិទ្ធិ Host File និងបើក Firewall Port 22/TCP៖**
   ```powershell
   cd C:\Windows\OpenSSH-Win64
   .\FixHostFilePermissions.ps1
   New-NetFirewallRule -Name "OpenSSH-Server-In-TCP" -DisplayName "OpenSSH Server (Inbound)" -Protocol TCP -LocalPort 22 -Action Allow
   ```

### ២. ការប្រើប្រាស់ SSH Client
អាចប្រើប្រាស់បញ្ជា `ssh`, `scp`, និង `sftp` លើ PowerShell ឬ Command Prompt៖
```powershell
# ការតភ្ជាប់ទៅកាន់ SSH Server
ssh username@hostname_or_IP

# ការផ្ទេរឯកសារតាម SCP / SFTP
scp test.txt Serverworld@10.0.0.100:'C:\Users\Serverworld\'
sftp username@hostname_or_IP
```

### ៣. ការផ្ទៀងផ្ទាត់ភាពត្រឹមត្រូវដោយប្រើសោគូ (Key-Pair Authentication)
1. បង្កើត Key-Pair លើ Server ដោយវាយបញ្ជា `ssh-keygen`។
2. ចូលទៅកាន់ថត `.ssh` រួចប្តូរឈ្មោះសោ Public ទៅជា `authorized_keys`៖
   ```powershell
   cd .ssh
   mv id_rsa.pub authorized_keys
   ```
3. **ដកសិទ្ធិ Everyone ចេញពីឯកសារ (ជាលក្ខខណ្ឌចាំបាច់សម្រាប់ SSH Security)៖**
   ```powershell
   icacls authorized_keys /remove Everyone
   ```
4. **ទាញយកសោសម្ងាត់ (Private Key `id_rsa`) ទៅកាន់ម៉ាស៊ីន Client៖**
   នៅម៉ាស៊ីន Client បង្កើតថត `.ssh` ក្រោម Home Directory រួចប្រើប្រាស់ `sftp` ទាញយកឯកសារ `id_rsa` មកដាក់ក្នុងថត `.ssh` នោះ។ បន្ទាប់មក អាចធ្វើការ Log in ដោយមិនបាច់វាយ Password ឡើយ។

### ៤. ការប្តូរ Default Shell ទៅជា PowerShell
តាមលំនាំដើម OpenSSH ប្រើ `cmd.exe` ប៉ុន្តែអាចប្តូរទៅប្រើ **PowerShell** វិញបាន៖
```powershell
New-ItemProperty -Path "HKLM:\SOFTWARE\OpenSSH" -Name DefaultShell -Value "C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe" -PropertyType String -Force
```

---

# មេរៀនទី ៥៖ Remote Desktop Server (RDS)

### ១. ការកំណត់លើ Server សម្រាប់ Single Session
1. បើក **Server Manager** -> **[Local Server]** -> ចុចលើ **[Disabled]** ត្រង់ផ្នែក **Remote Desktop**។
2. ធីកប្រអប់ **[Allow remote connections to this computer]** -> ប្រព័ន្ធនឹងបង្ហាញសារអនុញ្ញាត Firewall Exception ចុច [OK] រួចចុច [Apply]។

### ២. ការតភ្ជាប់ពីម៉ាស៊ីន Client (Client Settings)
1. នៅលើម៉ាស៊ីន Client (ឧទាហរណ៍ Windows 10) បើកប្រអប់ Run រួចវាយបញ្ជា `mstsc`។
2. បញ្ចូលអាសយដ្ឋាន IP ឬ Hostname របស់ Server រួចចុច **[Connect]**។
3. វាយបញ្ចូល Username និង Password របស់ Server -> ពេលផ្ទាំង Certificates បង្ហាញឡើង ចុច **[Yes]** ដើម្បីតភ្ជាប់។

### ៣. ការដំឡើង Remote Desktop Services (RDS - Multi-Session Environment)
*លក្ខខណ្ឌ៖* ម៉ាស៊ីន Server ត្រូវតែជាសមាជិក Domain (Domain Member)។
1. បើក **Server Manager** -> ចុច **[Add roles and features]**។
2. ត្រង់ Installation Type ជ្រើសយក **[Remote Desktop Services installation]** -> ចុច [Next]។
3. ជ្រើសយក **[Standard deployment]** -> **[Session-based desktop deployment]**។
4. **កំណត់ Role Services៖**
   * ជ្រើសរើសម៉ាស៊ីនសម្រាប់ **RD Connection Broker**។
   * ជ្រើសរើសម៉ាស៊ីនសម្រាប់ **RD Web Access**។
   * ជ្រើសរើសម៉ាស៊ីនសម្រាប់ **RD Session Host**។
5. ធីកប្រអប់ **[Restart the destination server automatically if required]** រួចចុច **[Deploy]**។

### ៤. ការបង្កើត Session Collections
1. នៅក្នុង **Server Manager** ជ្រើសយក **[Remote Desktop Services]** ផ្ទាំងខាងឆ្វេង -> ចុច **[Create session collections]** ផ្ទាំងខាងស្តាំ។
2. កំណត់ឈ្មោះ Collection Name។
3. ជ្រើសរើសម៉ាស៊ីន RD Session Host។
4. បញ្ជាក់ Users ឬ Groups ដែលអនុញ្ញាតឱ្យចូលប្រើប្រាស់ (ឧទាហរណ៍ `Domain Users`)។
5. កំណត់ User Profile Disks (ប្រសិនបើត្រូវការ) រួចចុច **[Create]**។

### ៥. ការប្រកាសផ្សាយ RemoteApp (Publish RemoteApp)
1. នៅក្នុង **Server Manager** ចុចលើ Session Collection ដែលបានបង្កើត។
2. ត្រង់ផ្នែក REMOTEAPP PROGRAMS ចុច **[Publish RemoteApp programs]**។
3. ធីកជ្រើសរើសកម្មវិធីដែលចង់ផ្សាយ (ឧទាហរណ៍ `Server Manager`) រួចចុច **[Publish]** -> [Close]។

### ៦. ការតភ្ជាប់ទៅកាន់ RemoteApp ពី Client
1. បើក Web Browser លើ Client ចូលទៅកាន់ផ្លូវ៖ `https://(Server_IP_or_FQDN)/RdWeb/`។
2. វាយបញ្ចូល Domain User Credentials ដើម្បី Sign-in។
3. ចុចលើ Icon កម្មវិធី RemoteApp ដែលបានផ្សាយ ដើម្បីដំណើរការកម្មវិធីនោះពីចម្ងាយ (បង្ហាញតែបង្អួចកម្មវិធី មិនបង្ហាញផ្ទាំង Desktop ទាំងមូលឡើយ)។

---

# មេរៀនទី ៦៖ DNS Server (Domain Name System)

### ១. ការដំឡើងសេវាកម្ម DNS Server
1. បើក **Server Manager** -> ចុច **[Add roles and features]**۔
2. ជ្រើសយក **Role-based or feature-based installation**។
3. ធីកប្រអប់ **[DNS Server]** -> ចុច **[Add Features]** -> ចុច [Next] រហូតដល់ប៊ូតុង **[Install]**។

### ២. ការបន្ថែម Forward Lookup Zone
1. បើក **Server Manager** -> **[Tools]** -> **[DNS]**។
2. ចុចស្តាំលើ Hostname របស់ Server -> ជ្រើសយក **[New Zone...]**។
3. ជ្រើសយក **[Primary zone]** -> **[Forward lookup zone]**។
4. វាយបញ្ចូល **Zone name** (ឧទាហរណ៍ Domain Name: `srv.world`)។
5. រក្សាឈ្មោះឯកសារ Zone File លំនាំដើម (`srv.world.dns`) រួចចុច [Finish]។

### ៣. ការបន្ថែម Reverse Lookup Zone
1. នៅក្នុង DNS Manager ចុចស្តាំលើ **[Reverse Lookup Zones]** -> ជ្រើសយក **[New Zone...]**۔
2. ជ្រើសយក **[Primary zone]** -> **[IPv4 Reverse Lookup Zone]**។
3. វាយបញ្ចូល **Network ID** (ឧទាហរណ៍៖ `10.0.0` សម្រាប់បណ្តាញ 10.0.0.0/24)។
4. រក្សាឈ្មោះឯកសារ Zone File លំនាំដើម (`0.0.10.in-addr.arpa.dns`) រួចចុច [Finish]។

### ៤. ការបន្ថែម A និង PTR Record
1. ចុចស្តាំលើ Domain Name ក្រោម Forward Lookup Zone -> ជ្រើសយក **[New Host (A or AAAA)...]**។
2. វាយបញ្ចូល **Name** (ឧទាហរណ៍ `rx-7`) និង **IP address** (ឧទាហរណ៍ `10.0.0.30`)។
3. **ធីកប្រអប់ [Create associated pointer (PTR) record]** ដើម្បីបង្កើត PTR Record ក្នុង Reverse Lookup Zone ដោយស្វ័យប្រវត្តិ។
4. **ផ្ទៀងផ្ទាត់ដោយប្រើ `nslookup`៖**
   ```cmd
   nslookup rx-7.srv.world
   nslookup 10.0.0.30
   ```

### ៥. ការបន្ថែម MX Record (Mail Exchanger)
1. ចុចស្តាំលើ Domain Name -> ជ្រើសយក **[New Mail Exchanger (MX)...]**។
2. វាយបញ្ចូល Hostname/FQDN របស់ Mail Server និងកំណត់អាទិភាព **Mail server priority** (ឧទាហរណ៍ `10`) រួចចុច [OK]។

### ៦. ការបន្ថែម CNAME Record (Canonical Name / Alias)
1. ចុចស្តាំលើ Domain Name -> ជ្រើសយក **[New Alias (CNAME)...]**។
2. វាយបញ្ចូល **Alias name** (ឧទាហរណ៍ `www`) និង FQDN របស់ Target Host (ឧទាហរណ៍ `fd3s.srv.world`)។
3. ផ្ទៀងផ្ទាត់ការបកប្រែឈ្មោះ Alias ដោយបញ្ជា `nslookup www.srv.world`។

---

# មេរៀនទី ៧៖ DHCP Server (Dynamic Host Configuration Protocol)

### ១. ការដំឡើងសេវាកម្ម DHCP Server
1. *លក្ខខណ្ឌតម្រូវ៖* ម៉ាស៊ីន Server ត្រូវតែដំឡើង AD DS ឬ Join ចូល Domain រួចរាល់។
2. បើក **Server Manager** -> **[Add roles and features]** -> ធីកជ្រើសយក **[DHCP Server]** -> **[Add Features]** -> ចុច [Install]។

### ២. ការកំណត់រចនាសម្ព័ន្ធ DHCP Server និង Scope
1. នៅក្នុង Server Manager ចុចលើ **[DHCP]** -> ចុចតំណ **[Complete DHCP configuration]**។
2. បញ្ជាក់សិទ្ធិរដ្ឋបាល (Credentials) ដើម្បីធ្វើការ **Authorize** ម៉ាស៊ីន DHCP Server ក្នុង Active Directory DS រួចចុច **[Commit]**។
3. **បង្កើត IP Scope ថ្មី៖**
   * បើក **Server Manager** -> **[Tools]** -> **[DHCP]**។
   * ចុចស្តាំលើ **[IPv4]** -> ជ្រើសយក **[New Scope...]**។
   * វាយបញ្ចូល Name និង Description សម្រាប់ Scope។
   * **កំណត់ជួរ IP (IP Address Range)៖** បញ្ចូល Start IP address (ឧទាហរណ៍ `10.0.0.200`) និង End IP address (ឧទាហរណ៍ `10.0.0.254`), Subnet Mask (`255.255.255.0`), និង Length (`24`)។
   * កំណត់ **Exclusions** (ដក IP ដែលមិនចង់ឱ្យចែក) និង **Lease duration** (រយៈពេលជួល IP)។
   * កំណត់ **Default Gateway** (ឧទាហរណ៍ `10.0.0.1`)។
   * កំណត់ **Parent Domain** (`srv.world`) និង **DNS Server IP** (`10.0.0.100`)។
   * ជ្រើសយក **[Yes, I want to activate this scope now]** ដើម្បីបើកដំណើរការ Scope។

### ៣. ការកំណត់រចនាសម្ព័ន្ធលើ Client (Configure DHCP Client)
នៅម៉ាស៊ីន Client (ឧទាហរណ៍ Windows 10) ចូលទៅកាន់ Network Connections -> IPv4 Properties -> កំណត់ជ្រើសយក **"Obtain an IP address automatically"** និង **"Obtain DNS server address automatically"**។

---

# មេរៀនទី ៨៖ Active Directory Domain Services (AD DS)

### ១. ការដំឡើងសេវាកម្ម Active Directory Domain Services
1. បើក **Server Manager** -> **[Add roles and features]** -> ធីកជ្រើសយក **[Active Directory Domain Services]** -> **[Add Features]** -> ចុច [Install]។

### ២. ការកំណត់ប្រកាស Domain Controller ថ្មី (Configure New DC / Forest)
1. បន្ទាប់ពីដំឡើងរួច នៅក្នុង Server Manager ចុចលើ Icon សញ្ញាព្រមាន -> ចុចតំណ **[Promote this server to a domain controller]**។
2. ជ្រើសយកជម្រើស **[Add a new forest]** រួចវាយបញ្ចូលឈ្មោះ Domain ក្នុងប្រអប់ **Root domain name** (ឧទាហរណ៍ `srv.world`)។
3. ជ្រើសរើសកម្រិត **Forest functional level** និង **Domain functional level** (ឧទាហរណ៍ `Windows Server 2016`) រួចកំណត់ពាក្យសម្ងាត់ **Directory Services Restore Mode (DSRM)**។
4. កំណត់ NetBIOS domain name (ឧទាហរណ៍ `FD3S01`)។
5. រក្សាទុកផ្លូវថត Database, Log files, និង SYSVOL (លំនាំដើម `C:\Windows\NTDS` និង `C:\Windows\SYSVOL`)។
6. ចុច **[Install]** -> បន្ទាប់ពីដំឡើងរួចរាល់ ប្រព័ន្ធនឹងធ្វើការ Restart ដោយស្វ័យប្រវត្តិ។
7. ពេល Logon ឡើងវិញ ឈ្មោះ Sign-in នឹងប្តូរទៅជាទម្រង់ `[Domain]\[User]` (ឧទាហរណ៍ `FD3S01\Administrator`)។

### ៣. ការបន្ថែម Domain User Accounts
1. បើក **Server Manager** -> **[Tools]** -> **[Active Directory Users and Computers]**។
2. ចុចស្តាំលើថត **[Users]** -> **[New]** -> **[User]**។
3. វាយបញ្ចូល Full Name និង User logon name (ឧទាហរណ៍ `Serverworld`@srv.world)។
4. កំណត់ ពាក្យសម្ងាត់ដំបូង (Initial Password) និងកំណត់ជម្រើស Password ផ្សេងៗ រួចចុច [Finish]។

### ៤. ការបន្ថែម Domain Group Accounts
1. នៅក្នុង ADUC ចុចស្តាំលើថត **[Users]** -> **[New]** -> **[Group]**។
2. វាយបញ្ចូលឈ្មោះ Group Name (ឧទាហរណ៍ `WebAdmin`), កំណត់ Group scope (Global), និង Group type (Security) រួចចុច [OK]។

### ៥. ការបន្ថែម Organizational Unit (OU) តាមឋានានុក្រម
1. នៅក្នុង ADUC ចុចស្តាំលើឈ្មោះ Domain (`srv.world`) -> **[New]** -> **[Organizational Unit]**។
2. វាយបញ្ចូលឈ្មោះ OU (ឧទាហរណ៍ `Hiroshima`)។
3. **ការបង្កើត OU ថ្នាក់កូន (Nested OU)៖** ចុចស្តាំលើ OU `Hiroshima` -> **[New]** -> **[Organizational Unit]** -> វាយបញ្ចូលឈ្មោះ `Development01`។

### ៦. ការបន្ថែម Computer Accounts
1. នៅក្នុង ADUC ចុចស្តាំលើថត **[Computers]** -> **[New]** -> **[Computer]**។
2. វាយបញ្ចូលឈ្មោះ Computer Name (ឧទាហរណ៍ `RX-7`) រួចចុច [OK]។

### ៧. ការបន្ថែម Users ច្រើនក្នុងពេលតែមួយតាម Batch Script (Add Users with a Batch)
១. **បង្កើតឯកសារអត្ថបទ `users.txt` បញ្ជីឈ្មោះ Users៖**
```text
Redhat Linux
Fedora Linux
Ubuntu Xenial
Debian Stretch
```

២. **បង្កើតឯកសារ Batch Script ឈ្មោះ `adduser.bat`៖**
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

៣. **បិទគោលការណ៍ភាពស្មុគស្មាញនៃ Password បណ្តោះអាសន្ន (Password Complexity Policy)៖**
* បើក **Server Manager** -> **[Tools]** -> **[Group Policy Management]**។
* ចុចស្តាំលើ **[Default Domain Policy]** -> ជ្រើសយក **[Edit...]**។
* ចូលទៅកាន់ផ្លូវ៖ **Computer Configuration** -> **Policies** -> **Windows Settings** -> **Security Settings** -> **Account Policies** -> **Password Policy**។
* បើក **[Password must meet complexity requirements]** រួចជ្រើសយក **[Disabled]** បណ្តោះអាសន្ន។
* រ៉ាន់ឯកសារ `adduser.bat` ដើម្បីបង្កើត Users ទាំងអស់ចូលក្នុង AD ដោយស្វ័យប្រវត្តិ រួចត្រឡប់មកបើក **[Enabled]** គោលការណ៍ Complexity វិញជាការស្រេច។

### ៨. ការចូលជាសមាជិក Domain ពីម៉ាស៊ីន Client (Join Domain from Clients)
1. **កំណត់ DNS លើ Client៖** នៅលើម៉ាស៊ីន Client (ឧទាហរណ៍ Windows 10) ចូលទៅកាន់ Network Properties នៃ IPv4 រួចកំណត់ **Preferred DNS server** ឱ្យចង្អុលមក IP របស់ AD DS Server (ឧទាហរណ៍ `10.0.0.100`)។
2. បើក **System Properties** -> ចូលទៅកាន់ Tab **[Computer Name]** -> ចុចប៊ូតុង **[Change...]**។
3. ត្រង់ផ្នែក **Member of** ធីកជ្រើសយក **[Domain]** រួចវាយបញ្ចូល Domain Name (ឧទាហរណ៍ `srv.world`)។
4. ប្រព័ន្ធនឹងទាមទារការផ្ទៀងផ្ទាត់ -> វាយបញ្ចូល Username និង Password របស់ Domain Administrator។
5. បន្ទាប់ពីបង្ហាញសារ **"Welcome to the srv.world domain"** ចុច [OK] រួចធ្វើការ **Restart កុំព្យូទ័រ**។
6. ពេល Logon ឡើងវិញ ជ្រើសយក **"Other user"** រួចវាយបញ្ចូល Domain User Account ដែលបានបង្កើតក្នុង AD ដើម្បី Sign-in ចូលប្រើប្រាស់។
