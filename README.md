# kafka-poc

## Install Ansible on RHEL server (which doesn't have subscription)

Below steps are used for local installation of ansible if you want to install all packages manually:

* yum localinstall -y 
* python-crypto2.6-2.6.1-2.el6.x86_64.rpm 
* python-httplib2-0.7.41.el6.art.noarch.rpm 
* python-jinja2-26-2.6-3.el6.noarch.rpm 
* python-keyczar-0.71c 1.el6.noarch.rpm 
* sshpass-1.05-5.el6.art.x86_64.rpm

Below steps are required for addng CentOS repositories to make yum work on a RHEL server **without subscription**.

 $ vi /etc/yum.repos.d/centos.repo  
>[root@mylab01 ~]# cat /etc/yum.repos.d/centos.repo   
> [centos]  
> name=CentOS $releasever - $basearch  
> baseurl=http://ftp.heanet.ie/pub/centos/6/os/$basearch/  
> enabled=1  
> gpgcheck=0  

$ sudo yum update

We ned to install epelrepositories for installing ansible.

> wget https://dl.fedoraproject.org/pub/epel/epel-release-latest-6.noarch.rpm  
> rpm -ivh epel-release-latest-6.noarch.rpm --force  
> yum install ansible  
> sudo yum install git  


> [kafka@mylab01 ~]$ ansible --version  
>ansible 2.6.20  
>  config file = /etc/ansible/ansible.cfg  
>  configured module search path = [u'/home/kafka/.ansible/plugins/modules', u'/usr/share/ansible/plugins/modules']  
>  ansible python module location = /usr/lib/python2.6/site-packages/ansible  
>  executable location = /usr/bin/ansible  
>  python version = 2.6.6 (r266:84292, Aug 18 2016, 15:13:37) [GCC 4.4.7 20120313 (Red Hat 4.4.7-17)]  
> [kafka@mylab01 ~]$  

