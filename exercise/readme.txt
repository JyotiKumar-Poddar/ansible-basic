

Inventory features
-Behaviorls parameters
-Groups
-Group of Groups
-


# To disable host key cheking
# to enable host key cheking  use
# ssh vagrant@192.168.56.20
# ssh vagrant@192.168.56.30
# to fix the login issue sudo passwd ubuntu to new password vagrant
#ansible all -i inventory -u vagrant -m ping -k
#ansible 192.168.56.20 -i inventory -u vagrant -m ping -k

#ansible webservers -i inventory_prod.yml -m user -a "name={{username}} password=123456" --become

#ansible webservers -i inventory_prod.yml -m apt -a "name=httpd state=present"

ansible webservers -i inventory_prod.yml -a "/bin/echo hello sammy"


to install apache web server
ansible webservers -i inventory_prod.yml -m apt -a "name=apache2 state=present update_cache=true" --become

installing mysql
ansible dbbservers -i inventory_prod.yml -m apt -a "name=mysql-server state=present update_cache=true" --become

starting mysql service

ansible dbservers -i inventory_prod.yml -m service -a "name=mysql state=started" --become




