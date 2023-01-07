# ansible


### Ansible Manual Command : Using this , we can execute one command at a time.

``` 
    ansible all -i inventory -e ansible_user=centos -e ansible_password=xyz123 -m shell -a "df -h"
```

-i inventory file 
-e extra or environment variables
ansible_user     : speciat variable name for the user-account to use 
ansible_password : speciat variable name for the user-account-password to use 
-m               : name of the module 

Ansible Scripts are referred as Playbooks and playbooks are written using YAML.

YAML : Yet Another Markup Language :

Markup Language : It's a presentation language.

YAML is very simple. Things to be remembered while learning YAML 

``` 
    1) YAML is intendation specific  
    2) YAML is all about Dictionary , List & a Map 
    3) YAML Files should always be ending with either .yml or .yaml 
```

# List 
# A list of tasty fruits
```
    - Apple
    - Orange
    - Strawberry
    - Mango
```

# Dictionary : A Key with a value is referred as Dictionary. 
# An employee record
```
    martin:
        name: Martin D'vloper
        job: Developer
        skill: Elite
```

### Example of list and dictionary 
```
    - martin:
        name: Martin D'vloper
        job: Developer
        skills:
            - python
            - perl
            - pascal
    - tabitha:
        name: Tabitha Bitumen
        job: Developer
        skills:
            - lisp
            - fortran
            - erlang
```
PS : A Key with multiple values is referred as a list 

# Map : A Key with multiple key value pairs is referred as a Object.


### What is a playbook ?
A playbook is a list of plays.

### What is a play ?
A Play is a list of tasks 

### What is a task ? 
A Task is a list of actions that you want to execute.