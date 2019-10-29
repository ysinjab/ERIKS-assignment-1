# ERIKS-assignment-1
ERIKS-assignment-1

Firstly, make sure you have virtualbox and vagrant are both installed in order to test this playbook. 

```
vagrant up
```

To get the VM IP execute this command and inspect the ip:
```
vagrant ssh-config
```

Next step is to create a virtual environment to install ansible:

```
virtualenv -p /usr/local/bin/python3 venv
. venv/bin/activate
pip install -r requirements.txt
```

Now ansible is installed you can go ahead and run the playbook:

```
ansible-playbook deploy_db.yaml -i hosts --ask-vault-pass
```

If you checked Vagrantfile you are going to find that port 33066 is mapped with the port 3306 in the virtual machine, so to test the db connect by using this command:

```
mysql -h 127.0.0.1 -P 33066 -u zamro -psupersecretpassword
```
