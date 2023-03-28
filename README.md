# Ansible Hands-on


Preparar ambiente para o experimento:

Iniciar 4 máquinas virtuais (VMs), uma das máquinas será a master e as demais serão servidores que iremos gerenciar.
- Configurar as VMs para permitir conexão via SSH sem senha a partir da master. Caso as VMs tenham sido criadas na AWS para serem acessadas através de uma chave .pem, basta configurar a máquina master para conter 


Instalar ansible na máquina do sysadmin:

    sudo apt-add-repository ppa:ansible/ansible
    sudo apt-get update
    sudo apt-get install ansible

Criar um grupo de máquinas no arquivo /etc/ansible/hosts:

    [servers]
    server1 ansible_host=172.31.81.157
    server2 ansible_host=172.31.89.74
    server3 ansible_host=172.31.86.235

Testar execução de comando em todos os nodos:

    ansible servers -a hostname
    ansible servers -a uptime

Usar módulo ping para verificar a conectivadade com os servidores:

    ansible all -m ping

Referências:
- https://www.digitalocean.com/community/tutorials/how-to-install-and-configure-ansible-on-ubuntu-20-04
