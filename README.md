# tipCommands

### Find a text and reemplace, recursive:
  ```
   find . -type f -exec sed -i 's/TEXT_TO_FIND/\\TEXT\\TO\\REEMPLACE/g' {} \;
  ```
### Para Error opening terminal: xterm-256color
  ```
# export TERM=xterm
  ```

### Para permitir conexiones externas:
  ```
# service nscd start
  ```

### Para resolver los nombres de domino:
  ```
	# vim /etc/resolv.conf  
		nameserver 8.8.8.8	
  ```
		
		
### Proxy		
  ```
set PROXY_HTTP=http://proxy4.unal.edu.co:8080
  ```
### Para instalar fuse-sshfs se necesita primero fuse
  ```
# yum install fuse
  ```

luego con el archivo rpm  [fuse-sshfs-1.7-2.el5.kb.src.rpm](http://rpm.pbone.net/index.php3/stat/26/dist/55/size/105688/name/fuse-sshfs-1.7-2.el5.kb.src.rpm)
ftp://ftp.pbone.net/mirror/centos.karan.org/el5/extras/testing/SRPMS/fuse-sshfs-1.7-2.el5.kb.src.rpm
  ```
# rpm -ivh fuse-sshfs-1.7-2.el5.kb.src.rpm
# rpmbuild -bb /usr/src/redhat/SPECS/fuse.spec
  ```

Finalmente, installar los rmps que se han compilado:
  ```
cd /usr/src/redhat/RPMS/x86_64 (replace ‘x86_64’ with your arch, if necessary)
rpm -Uvh fuse-sshfs-1.7-2.x86_64.rpm
  ```

## For backups of database using rsync - exporter
  ```
# rsync --help | grep remove-
     --remove-source-files   sender removes synchronized files (non-dirs)
  ```
Si no se encuentra la opción: --remove-source-files es neceserio instalar una versión actualizada de rsync
  ```
  # yum install rsync
  ```

# SET mirros from Fedora in /etc/yum.repos.d/CentOS-Base.repo
 ```sh
[extras]
name=Fedora Core 6 Extras
mirrorlist=http://mirrors.dotsrc.org/fedora-buffet/archive/fedora/linux/extras/6/$basearch
enabled=0
gpgkey=file:///etc/pki/rpm-gpg/RPM-GPG-KEY-fedora-extras
gpgcheck=0

[fc6-updates]
name=Fedora Core 6 Updates
mirrorlist=http://mirrors.dotsrc.org/fedora-buffet/archive/fedora/linux/updates/6/$basearch
enabled=0
gpgkey=file:///etc/pki/rpm-gpg/RPM-GPG-KEY-fedora-extras
gpgcheck=0
 ```
 
 en la consola
  ```
 # yum clean all
  ```
## smtp Connection error
TYPO3 Exception: Connection could not be established with host smtp.gmail.com [Connection timed out #110]

    Check if httpd_can_sendmail is on , run this getsebool httpd_can_sendmail
        When you get: httpd_can_sendmail --> off , run setsebool -P httpd_can_sendmail 1
        When you get: httpd_can_sendmail --> on that's fine move on step 2.

    Check also if httpd_can_network_connect is on, run getsebool httpd_can_network_connect
        When you get httpd_can_network_connect --> off run setsebool -P httpd_can_network_connect 1
        When you get: httpd_can_network_connect --> on that's fine move on step 3.
    Use the following settings for smtp : 'host' => '64.233.166.108' 'port' => '465'
