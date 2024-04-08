# Vagrant com Ansible


PASSO A PASSO

Podemos usar o ansible instalado no host para automatizar as vms criadas pelo vagrant
para isso basta usar o recurso do inventario automativo do vagrant, é arquivo sem extensão ou com a extensão .yaml chamado vagrant_ansible_inventory,
sua localização deve ser na mesma pasta onde está localizado o vagrantfile

Para gerar esse arquivo use:

  vagrant provision --provision-with=ansible

OBS:
  NESSE ARQUIVO É SÓ ADICIONAR AS CONFIGURAÇÕES DO USUARIO DO VAGRANT É DA CHAVE PARA QUE O ANSIBLE FAÃ A CONEXÃO COM AS VMS

Depois execute o vagrantfile de uma ou mais vms, pode ser varias vms em um unico vagrantfile ou varias vms em vagrantfile separados,
e as vms pode estar com a configuração definida com private network ou mesmo com a configuração padrão do vagrant

Depois que as vms estiveram ativas para usar o ansible para automatizar as configurações das vms(conforme a preferencia) execute o comando
padrão do ansible para playbooks: 
 
  ansible-playbook -i vagrant_ansible_inventory.yml playbook.yml

OBS: 
  O detalhe é que deve ser passado o arquivo de inventario reconhecido pelo vagrant, nesse exemplo o arquivo está no formato yml

Essa é mais uma forma de fazer o uso do ansible para automatizar tarefas em maquinas virtuas, podendo automatizar tarefas do proprio host que tem o vagrant e o ansible
instalados

a forma já conhecida seria instalar o ansible em uma vm do vagrant e dessa vm configurar as chaves ssh e compartilhar para as outras vms
e executas os comandos de playbooks ou roles do ansible para automatizar as tarefas nas outras vms existentes
