# ansible

## Comando basicos ansible
## Esse comando ela ajuda a indenticar se as maquinas estão ok de acordo com host
** $ansible -i hosts all -m ping
## Comando que ajuda auxialiar nas configuração na hora de criação do ansible
** ansible -i hosts oracle -m setup -k -K 
** ansible -i hosts debian12 -m setup -k -K 

## Verificar erros de sintaxe
`ansible-playbook playbooks/PLAYBOOK_NAME.yml --syntax-check`

## Executar o ansible no modo *dry-run*
`ansible-playbook playbooks/PLAYBOOK_NAME.yml --check`

## Caso os módulos não funcionem, usar o modo `raw`:
`ansible -m raw -s -a "yum install libselinux-python -y" new-atmo-images`

## Limitar a execução do playbook por hosts:
* `ansible-playbook playbooks/PLAYBOOK_NAME.yml --limit "host1"`
* `ansible-playbook playbooks/PLAYBOOK_NAME.yml --limit "host1,host2"`

## Limitar tasks por tags:
`ansible-playbook playbooks/PLAYBOOK_NAME.yml --tags 'install'`

## Pular tasks por tags:
`ansible-playbook playbooks/PLAYBOOK_NAME.yml --skip-tags 'sudoers'`

## Nomear os hosts no inventário:
```
[web]
host1 ansible_host=127.0.0.1
host2 ansible_host=192.1678.0.1
```
