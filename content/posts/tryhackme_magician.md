---
weight: 4
title: "My First CTF writeup"
date: 2021-03-03T21:57:40+08:00
lastmod: 2021-03-03T16:45:40+08:00
description: "This is my first TryHackMe writeup"

title: My first CTF writeup
featuredImage: tryhackmebanner.jpg
hiddenfeaturedImage: true

tags: ["TryHackMe", "CTF"]
categories: ["Writeups"]

lightgallery: false
summary: Joining this room on the TryHackMe platform, it tells us that this box is apparently a webserver that hosts a vulnerable website which lets you convert image file formats.
---

### Summary

1. Recon with nmap & Enumerate the services. FTP on port 21, HTTP-Proxy on port 8080 and HTTP on port 8081.

2. The HTTP service on port 8081 allows image upload and exploiting the “ImageTragick” vulnerability . 

3. Initial foothold by exploiting ImageTragick Remote Code Execution (CVE-2016-3714).

4. Upload the payload, spawn a shell and get our first user flag.

5. Linux enumeration reveals that port 6666 (Magic Cat Listener) is listening on target localhost.

6. We create a tunnel with ssh, and proxy our traffic through port 6666 on our Kali machine which lets us talk to the localhost service on the victim machine.

7. The local service allows for LFI, which lets us read root.txt and get our last flag.

   






