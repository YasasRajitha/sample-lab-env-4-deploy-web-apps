# ansible-labs

## How to use these Labs
1. Install Oracle Virtual Box:  https://www.virtualbox.org/

2. Install Vagrant: https://www.vagrantup.com/downloads.html

3. In a new Directory copy this respository:
``` shell
git clone https://github.com/YasasRajitha/ansible-labs.git
```

4. Start the vagrant instance.
``` shell
vagrant up
```

5. Create an SSH key using ssh-keygen.
``` shell
ssh-keygen
```

6. SSH into the ansible-control virtual machine.
``` shell
vagrant ssh ansible-control
```

7. Copy SSH key to every node (U might need to enter the password for each node ->  Password,Username :- vagrant).
``` shell
ssh-copy-id localhost && ssh-copy-id loadbalancer && ssh-copy-id web01 && ssh-copy-id web02 && ssh-copy-id db01
```

8. Install ansible on ansible-control node.
``` shell
sudo apt install ansible
```

9. Change Directory to vagrant lab directory.
``` shell
cd /vagrant/lab
```

10. Run the playbook command.
``` shell
ansible-playbook -i hosts -K playbook1.yml
```

11. Then load the website on a browser through loadbalancer ip and given port (192.168.56.104:82).
