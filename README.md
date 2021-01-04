##solved(ANTHEM vm)

      _______________________________________________      
      ||THE          ____   ____  ____ ____         ||     
      ||   || || || ||._|| ||__||  ||   ||  ||__||  ||     
      ||   ||_||_|| || \_  ||  || _||_  ||  ||  ||  ||     
      ||____________________________________________||   



#TRY HACK ME - EASY

# part1 questions:-

1. Let's run nmap and check what ports are open.
A. Done 

#nmap
```
PORT     STATE SERVICE       VERSION
80/tcp   open  http          Microsoft HTTPAPI httpd 2.0 (SSDP/UPnP)
|_http-title: Anthem.com - Welcome to our blog
135/tcp  open  msrpc         Microsoft Windows RPC
139/tcp  open  netbios-ssn   Microsoft Windows netbios-ssn
445/tcp  open  microsoft-ds?
3389/tcp open  ms-wbt-server Microsoft Terminal Services
| rdp-ntlm-info: 
|   Target_Name: WIN-LU09299160F
|   NetBIOS_Domain_Name: WIN-LU09299160F
|   NetBIOS_Computer_Name: WIN-LU09299160F
|   DNS_Domain_Name: WIN-LU09299160F
|   DNS_Computer_Name: WIN-LU09299160F
|   Product_Version: 10.0.17763
|_  System_Time: 2021-01-03T12:50:26+00:00
| ssl-cert: Subject: commonName=WIN-LU09299160F
| Not valid before: 2021-01-02T12:46:52
|_Not valid after:  2021-07-04T12:46:52
|_ssl-date: 2021-01-03T12:51:05+00:00; -5h29m57s from scanner time.
Service Info: OS: Windows; CPE: cpe:/o:microsoft:windows

Host script results:
|_clock-skew: mean: -5h29m57s, deviation: 0s, median: -5h29m57s
| smb2-security-mode: 
|   2.02: 
|_    Message signing enabled but not required
| smb2-time: 
|   date: 2021-01-03T12:50:30
|_  start_date: N/A

```
#dirsearch
```

```

2. What port is for the web server?
A. 80

3. What port is for remote desktop service?
A. 3389

4. What is a possible password in one of the pages web crawlers check for?
A. UmbracoIsTheBest!

In robots.txt

5. What CMS is the website using?
A. umbraco

In robots.txt

6. What is the domain of the website?
A. anthem.com

7. What's the name of the Administrator
A. Solomon Grundy

After googling the poem

8. Can we find find the email address of the administrato
A.  SG@anthem.com
```
Image result for Born on a Monday,Christened on Tuesday,Married on Wednesday,Took ill on Thursday,Grew worse on Friday,Died on Saturday,Buried on Sunday.That was the end… writer
Solomon Grundy
Grew worse on a bright and breezy Friday, Died on a grey and glorious Saturday, Buried on a baking, blistering Sunday. That was the end of Solomon Grundy.
```
according to the previous one (JD@anthem.com)SG

#part2

1. What is flag 1?
A. THM{L0L_WH0_US3S_M3T4}
```
http://10.10.85.100/archive/we-are-hiring/
In its page source 
search THM
```

2. What is flag 2?
A. THM{G!T_G00D}

```
http://10.10.85.100/archive/we-are-hiring/
In its page source 
search THM
```

3. What is flag 3?
A.THM{AN0TH3R_M3TA}
```
http://10.10.85.100/archive/a-cheers-to-our-it-department/
In its page source 
search THM
```

4. What is flag 4?
A. THM{L0L_WH0_D15}
```
in profile
```

#part3

//It is really interesting 

1. Let's figure out the username and password to log in to the box.(The box is not on a domain)
	COMPLETED
2. Gain initial access to the machine, what is the contents of user.txt?
A.THM{N00T_NO0T}

first, you must use the command rdesktop
```
rdesktop YOURIP
```
then login with 
```
username => SG and password => UmbracoIsTheBest!
```
on desktop user.txt file open it, it is flag1

3. Can we spot the admin password?
A. ChangeMeBaby1MoreTime  //XD

Go to ThisPC -> localdisk(c)
on view option allow show hidden file
go in ->backup->restore

go in restore properties->security->add user(add a user)-> in permission accept fullcontrol-> open file and see the password


4. Escalate your privileges to root, what is the contents of root.txt?
A. THM{Y0U_4R3_1337}

open cmd with adminstrator -> use the previous password -> then go to c/user/administrator/desktop -> write command in terminal
```
type root.txt
```
