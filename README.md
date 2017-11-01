# custom-ansible-facts
Example Ansible playbook showing how to use custom facts

### Example output below
    [root@host]/home/ssebs/custom-ansible-facts# ansible-playbook playbooks/custom_fact.yml --limit node01
    
    PLAY [all] ******************************************************************************************************************************************
    
    TASK [Gathering Facts] ******************************************************************************************************************************
    ok: [node01]
    
    TASK [Create ansible fact directory] ****************************************************************************************************************
    ok: [node01]
    
    TASK [Copy custom fact JSON] ************************************************************************************************************************
    ok: [node01]
    
    TASK [Get Ansible facts] ****************************************************************************************************************************
    ok: [node01]
    
    TASK [Print new facts] ******************************************************************************************************************************
    ok: [node01] => (item={u'sample': {u'SomeKey': u'SomeVal', u'Foo': u'Bar', u'Animal': {u'Gender': u'Female', u'Type': u'Cat'}}}) => {
        "item": {
            "sample": {
                "Animal": {
                    "Gender": "Female",
                    "Type": "Cat"
                },
                "Foo": "Bar",
                "SomeKey": "SomeVal"
            }
        },
        "msg": [
            [
                "Female",
                "Cat"
            ]
        ]
    }
    
    PLAY RECAP ******************************************************************************************************************************************
    node01                 : ok=5    changed=0    unreachable=0    failed=0
    
    [root@host]/home/ssebs/custom-ansible-facts#
