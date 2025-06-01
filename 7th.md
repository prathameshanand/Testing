First Command are(ubuntu) 
  sudo apt update

2. sudo apt install ansible -y
3. ansible --version
4. mkdir ~/ansible-lab
5. cd ~/ansible-lab
6. nano hosts (alternative  "mousepad hosts")
   paste following code on the hosts file
     localhost ansible_connection = local
   on the  nano
   press CTRL + O
   and after press CTRL + X 
8. after the creating the above file now execute this comments
9.     '' ansible  -i hosts local -m ping ''
10. after the above excutive see the green line
11. now create one more file , name
12.    ``nano install_nginx.yml``

13. paste following content
14. ""
15. -name: Install and start NGINX on localhost
16. hosts: local
17. become: yes

18. tasks:
19.   -name: Install NGINX
20.   apt:
21.   
22.   name:nginx
23.   state: present
24.   update_cache:yes

25. -name: Ensure NGINX is running
26.   service :
27.   name: nginx
28.   state: started
29.   enabled: yes

30.   ""
31. save the file and execute following command
32.  `` ansible-playbook -i hosts install_nginx.yml ``
33.  after the this command run the following command;-
34.   `` curl http://localhost ``
