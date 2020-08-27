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
