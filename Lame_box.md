# Lame box Release Date - 14 Mar, 2017
Lame is an easy Linux machine, requiring only one exploit to obtain root access. It was the first machine published on Hack The Box and was often the first machine for new users prior to its retirement. 

## Quick write up 
After running scan `nmap -sV `on the target box 10.10.10.3, the following ports have been found open 21,22,139,44 and multiple versions were able to be enumerated from the scan, the samba version was originaly not able to be viewed, the following scans where able to enumerate the versions from this service `nmap --scripts defualt `, `smbmap -H `. Using the exploit database and CVE search was able to give more information about potential exploits. 

After enumeration, the box is able to be expolited via CVE-2007-2447. using the Metasploit framework and  loading up the exploit I was able to get a reverse shell with root access to the box. No further explotaion was done. 

## Issues that have caused this box to be able to be exploited. 
- Read and write access on the TMP directory, making reverse shell payload able to be uploaded via metasploit to the SMB service. 
- the FTP sever is able to be logged into via anonomyous credentials, this could have opened up further explotation but we find no files that we can use. 

## what can be done to secure this box 
-  update the SAMBA service to a current version like 4.21 https://www.samba.org/samba/history/
-  Remove access to the TMP Directory
-  Remove the Ability to log in to the FTP server with  anonomyous credentials

### tools used 
- `nmap`
- `smbmap`
- `smbclient`
- `ftp`
- `msfconsole`

 
![image](https://github.com/user-attachments/assets/7d6f082b-d8a6-4311-bd54-81f1a3b9a38d)
![image](https://github.com/user-attachments/assets/e175b2e2-8016-4e0e-9f6c-3fa23314db30)

![image](https://github.com/user-attachments/assets/7d465a99-82d9-4fb9-983c-57f8e990ce3e)


![image](https://github.com/user-attachments/assets/cf3a06b1-ce8b-41f3-b4b2-152b1baba355)

### Exploit ran and reverse shell has been created 
![image](https://github.com/user-attachments/assets/9a6750a3-198a-4df0-bf80-1dfaa554b2b6)

![image](https://github.com/user-attachments/assets/6b4dbdfc-c093-4117-976a-98f80fbbccd6)


