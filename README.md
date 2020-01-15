# Fix ansible-awx hashi_vault error

```
ASK [Gathering Facts] *************************************************************************************************************************************************************************************
fatal: [serverIP]: FAILED! => {
    "failed": true,
    "msg": "An unhandled exception occurred while running the lookup plugin 'hashi_vault'. Error was a <class 'ansible.errors.AnsibleError'>, original message: Please pip install hvac to use this module"
}
```

# How to fix

Add this repository to a new proyect and create a template to run the playbook in localhost.

playbook:

```yml
- hosts: localhost
  connection: local
  tasks:
    - name: Install ansible pip dependencies for Ansible
      pip:
        name: "{{ item }}"
        state: latest
      with_items:
        - jmespath
        - hvac
        - "hvac[parser]"
```