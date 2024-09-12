# Sea

Tis box was fun used alot of tools, dont want to give a write upo untill the HTB gives the go ahead. 

## Tools used 
- nmap
- wfuzz
- hashcat
- burp
- CVE database
- python

I was stuck on this box for a good while due to a simple mistake. I was unzipping the exploit to change the IP and port, and then when I was using the zip command, I was not zipping the directory and the file recursively. As a result, the .php file was getting dropped. When the machine sent GET requests to me for the files, it was grabbing the XSS file and the zip file, but when it opened the zip file, there was nothing in it,no rs script this was because it was being dropped when I was zipping the directory.
I discovered this by using zipinfo on the zip folder and then not seeing the php file. I resolved this by using the zip command properly and was able to get a callback instantly. I was then able to get through the machine pretty quickly after that. I thought the machine was harder than it was, and it turned out I was just messing up a simple command.![image](https://github.com/user-attachments/assets/84c109e1-9978-456c-abda-ee6add3b57a8)





![image](https://github.com/user-attachments/assets/fa0475f4-4553-427c-990e-b0b815ee8240)

