---
title: "💻 Create Your Own LeetCode with Judge🔥"
seoTitle: "build your own leetocode , judge0 setup"
seoDescription: "setting up judge0 for windows and mac users"
datePublished: Fri Apr 25 2025 11:19:06 GMT+0000 (Coordinated Universal Time)
cuid: cm9wp8avm000t09l7bju72a37
slug: create-your-own-leetcode-with-judge
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1745582657835/810949ac-2ad3-4763-9277-d14656025769.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1745582636190/88962e46-6bfe-48bd-bc4c-560f1739e969.png
tags: web-development, leetcode, judge0, chaicode, chaicohort, codeengine, judge0setup, chaicodecohort

---

## **What is Judge0 ?**

Judge0 is an open-source online code execution engine that supports over 60 programming languages. It allows you to compile and run code remotely via a REST API, making it perfect for building coding platforms, online judges, or interview preparation tools like LeetCode, HackerRank, or Codeforces. Whether you're running C++, Python, JavaScript, or Go — Judge0 handles it all in a secure, sandboxed environment.

### How to Setup Judge0 ?

I recommend using Linux especially Ubuntu-20.04, But you can also setup this on mac

### For Windows Users Special Steps

Install Wsl in your windows, run this command in your powershell terminal

### Installing wsl

```bash
wsl --install
```

Then Setup your Unix username and password, After this restart your pc then run this command to install Ubuntu-20.04

```bash
wsl --insall -d Ubuntu-20.04
```

then login to Ubuntu with this command

```bash
wsl -d Ubuntu-20.04
```

your terminal will change like this

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1745570927902/9c1bc714-de74-47b0-a5cc-2c5b088bf935.png align="center")

then run command

```bash
sudo apt update
// enter the passowrd which you set in the unix login
```

after this

```bash
sudo apt upgrade
sudo reboot
```

after rebooting the Ubuntu it will be closed so then restart with

```bash
wsl -d Ubuntu-20.04
```

then again it wll be like this

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1745572923198/c5345128-4789-48ab-b97f-dcb9b835abd8.png align="center")

then run again

```bash
sudo apt update 
//enter the password
```

then open the grub file in nano with command

### ✅ Fixing GRUB Syntax Error in Ubuntu

#### 🔧 Step 1: Open the GRUB config file

```bash
sudo nano /etc/default/grub
```

> It’ll ask for your password — type it and press `Enter`.

---

#### 🧾 Step 2: Paste the following into the file

Note:- (if you have empty grub file then do this if not paste only last line):

```bash
bashCopyEditGRUB_DEFAULT=0
GRUB_TIMEOUT=10
GRUB_DISTRIBUTOR=`lsb_release -i -s 2> /dev/null || echo Debian`
GRUB_CMDLINE_LINUX_DEFAULT="quiet splash"
GRUB_CMDLINE_LINUX=systemd.unified_cgroup_hierarchy=0
```

* Use `Ctrl + Shift + V` to paste (if you're on a standard terminal).
    
* Make sure there are **no extra characters or spaces** after any line.
    

---

#### 💾 Step 3: Save and Exit

* Press `Ctrl + O` (to write/save the file)
    
* Press `Enter` (to confirm)
    
* Press `Ctrl + X` (to exit the editor)
    

---

#### 🔄 Step 4: Update GRUB

```bash
sudo update-grub
```

> 📋 If a popup appears, **select the 2nd option** (usually your system disk), then press **OK**.  
> If no popup, it will just update silently — that’s fine too.

---

#### ✅ Step 5: Reconfigure and clean up

Run this to finish up:

```bash
bashCopyEditsudo dpkg --configure -a
sudo apt install -f
```

This should fix the broken `grub-pc` and `grub-gfxpayload-lists` issues.

after this everything is on judge0 github documentation link: [https://github.com/judge0/judge0/blob/master/CHANGELOG.md](https://github.com/judge0/judge0/blob/master/CHANGELOG.md)

but here’s simple steps to do it:-

Download docker and docke-compose with this command

```bash
sudo apt install docker
// this will install docker
sudo apt install docker-compose
// this will install docker-compose
```

### Geting Judge0 file

### Note: Mac users can follow this from here

```bash
wget https://github.com/judge0/judge0/releases/download/v1.13.1/judge0-v1.13.1.zip
```

### Installing Unzip

```bash
sudo apt install unzip
// this is install unzip
```

### Unzip the judge0 file

```bash
unzip judge0-v1.13.1.zip
```

### Setting Up password

then go to judge0 file with cd command

```bash
cd judge0-v1.13.1/
ls 
// ls will show you these files docker-compose.yml  judge0.conf
```

then set the `REDIS_PASSWORD`and `POSTGRES_PASSWORD` and `judge0.conf` of your choice

i recommend using [this website](https://www.random.org/passwords/?num=1&len=32&format=plain&rnd=new) to generate passwords

```bash
sudo nano judge0.conf
// then set the password
```

* Press `Ctrl + O` (to write/save the file)
    
* Press `Enter` (to confirm)
    
* Press `Ctrl + X` (to exit the editor)
    

### Running db and docker

After lets run db and redis this will take time

```bash
sudo docker-compose up -d db redis
sleep 10s
sudo docker-compose up -d
sleep 5s
```

then check if container are running or not with command

```bash
sudo docker-compose ps
// it will show the four status are up
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1745578836480/4185f3ff-50ec-4058-9091-533774887f4a.png align="center")

Then go to `http://localhost:2358/docs` if it’s open your setup done and you can go to `http://localhost:2358/dummy-client.html` to run the code

### For restarting the program

if you want to start the setup just run these command in windows terminal

```bash
//mac and linux users skip wsl command
wsl -d Ubuntu-20.04
sudo docker-compose up -d 
// it will run everything thing again
```

Note: For mac users if it’s not workging for mac users simply setup a virtual box machine with linux or purchase a machine online for more information follow instructions from hitesh sir video [https://youtu.be/6nkNUDNhSYI?si=OvVQuFpqN13PQ5kV](https://youtu.be/6nkNUDNhSYI?si=OvVQuFpqN13PQ5kV)