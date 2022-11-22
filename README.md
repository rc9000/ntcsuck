# "ntcsuck"

Ansible playbook proof-of-concept to fetch mac address tables, parse them with ntc-templates/textfsm, and store in Netdisco using the new API from PR https://github.com/netdisco/netdisco/pull/942


## How to install & run, "requirements.txt"

    python3 -m venv venv
    . venv/bin/activate
    python3 -m pip install ansible textfsm ansible-pylibssh 
    ansible-galaxy collection install ansible.netcommon cisco.ios cisco.nxos
    ansible-galaxy role install ansible-network.network-engine
    netdisco-do getapikey -e admin > api_key.txt
    
    ansible-playbook  -k -i inventory-lab2.yml  -l "192.168.*"  pb.yml
