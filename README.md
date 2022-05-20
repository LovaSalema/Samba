<div id="top"></div>

<br />
<div align="center">

  <h3 align="center">SAMBA</h3>


</div>

 ![Samba](https://adrianmejia.com/images/samba-filesharing-with-windows-ubuntu-mac-large.jpg)

<!-- TABLE OF CONTENTS -->
<details>
  <summary>Table of Contents</summary>
  <ul>
    <li>
        <a href="#Description">description</a>
    </li>
    <li>
      <a href="#Setting-up-the-Samba-File-Server-on-Ubuntu/Linux">Setting up the Samba File Server on Ubuntu/Linux</a>
    </li>
  </ul>
</details>



<!-- ABOUT THE PROJECT 


[![Product Name Screen Shot][product-screenshot]](https://example.com)-->
## Description

Samba allows to share files and printers with other computers remotely, regardless their operating system (linux, windows, Mac, ...). This guide show how to intall and configure the Samba service in a Ubuntu machine and access it through windows and mac.

## Setting up the Samba File Server on Ubuntu/Linux:

* Open the terminal
* Install samba with the following command: 
```sh
 sudo apt-get install samba smbfs
```
* Configure samba typing: 
```sh
 vi /etc/samba/smb.conf
```

* Set your workgroup (if necesary). Go down in the file, until you see :

` # Change this to the workgroup/NT-domain name your Samba server will part of workgroup = WORKGROUP`
   


* Set your share folders. Do something like this (change your path and comments)

 `# Adrian's share`
 ```sh
[MyShare]
  comment = YOUR COMMENTS
  path = /your-share-folder
  read only = no
  guest ok = yes
```


* Restart samba. type: `/etc/init.d/smbd restart`
Create the share folder: `sudo mkdir /your-share-folder`
Set the permissions: `sudo chmod 0777 /your-share-folder`

If you need to enable the samba ports in your firewall these are the ports:
```sh
port type    port no
udp        137
udp        138
tcp        139
tcp        445
```


<!-- MARKDOWN LINKS & IMAGES -->
<!-- https://www.markdownguide.org/basic-syntax/#reference-style-links -->
[contributors-shield]: https://img.shields.io/github/contributors/othneildrew/Best-README-Template.svg?style=for-the-badge
[contributors-url]: https://github.com/othneildrew/Best-README-Template/graphs/contributors
[forks-shield]: https://img.shields.io/github/forks/othneildrew/Best-README-Template.svg?style=for-the-badge
[forks-url]: https://github.com/othneildrew/Best-README-Template/network/members
[stars-shield]: https://img.shields.io/github/stars/othneildrew/Best-README-Template.svg?style=for-the-badge
[stars-url]: https://github.com/othneildrew/Best-README-Template/stargazers
[issues-shield]: https://img.shields.io/github/issues/othneildrew/Best-README-Template.svg?style=for-the-badge
[issues-url]: https://github.com/othneildrew/Best-README-Template/issues
[license-shield]: https://img.shields.io/github/license/othneildrew/Best-README-Template.svg?style=for-the-badge
[license-url]: https://github.com/othneildrew/Best-README-Template/blob/master/LICENSE.txt
[linkedin-shield]: https://img.shields.io/badge/-LinkedIn-black.svg?style=for-the-badge&logo=linkedin&colorB=555
[linkedin-url]: https://linkedin.com/in/othneildrew
[product-screenshot]: images/screenshot.png
