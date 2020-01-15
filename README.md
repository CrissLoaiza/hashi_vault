fix ansible-awx hashi_vault error

ASK [Gathering Facts] *************************************************************************************************************************************************************************************
fatal: [serverIP]: FAILED! => {
    "failed": true,
    "msg": "An unhandled exception occurred while running the lookup plugin 'hashi_vault'. Error was a <class 'ansible.errors.AnsibleError'>, original message: Please pip install hvac to use this module"
}
