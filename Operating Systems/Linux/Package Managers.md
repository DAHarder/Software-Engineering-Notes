# Installing Software on Linux

## Centos/RedHat/Fedora
### RPM
Requires you to point to the location of the package.  
Does install dependencies

```bash
rpm -i telnet.rpm
#Intall package

rpm -e telnet.rpm
#Uninstall Package

rpm -q telnet.rpm
Query package
```

---

### YUM
High level package manager that uses RPM underneath installs all dependencies

```bash
yum install ansible
#installs package and all dependencies
	yum install ansible-<version>
	#to install a specific version of a package

yum install <URL>.rpm
#you can install a new repo from a url

yum list <package>
#lists available or installed packages
	--showduplicates
	#list all versions you can install

yum remove <package>
#remove installed package

yum repolist
#lists available repos

ls /etc/yum.repos.d/
#lists the repo files for the repolist

cat /etc/yum.repos.d/<file>
#shows the URL for all the packages within the repo (Visit the url to see packages)
```