Create a .rpmmacros 
```bash
-bash-4.2$ cat ~/.rpmmacros 
%_topdir      %(echo $HOME)/build_rooot/rpmbuild
#%_topdir      %(echo $HOME)/rpmbuild
%_smp_mflags  -j3
%__arch_install_post   /usr/lib/rpm/check-rpaths   /usr/lib/rpm/check-buildroot
-bash-4.2$
```
Create rpmbuild directory structure
```bash
mkdir -p ~/build_root/rpmbuild/{BUILD,RPMS,SOURCES,SPECS,SRPMS}
```

```bash
cd
git clone https://github.com/gireeshdeepakr/httpd.spec.git  #Update Version and release info as per the version you're building
cd httpd.spec
cp http.spec ~/build_root/rpmbuild/SPEC/
cd ~/build_root/rpmbuild/SOURCES/
wget --no-check-certificate https://dlcdn.apache.org/httpd/httpd-2.4.58.tar.gz
cd ~/build_root/rpmbuild
rpmbuild -bb SPECS/httpd.spec 
```
