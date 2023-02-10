# Implantação de API web usando Ansible e Dockerfile

Neste projeto, uma API web é implantada usando um Dockerfile que descreve uma imagem personalizada do servidor web NGINX.

A máquina virtual Vagrant é provisionada duas vezes.

O primeiro provisionamento é feito pelo shell, em que um script é executado para atualizar os repositórios do Ubuntu, adicionar o repositório do Ansible e, por fim, instalar o Ansible.

O segundo provisionamento é feito pelo Ansible, que por sua vez executa todos os passos relacionados ao Docker.

## Executando o provisionamento

Após a criação da máquina virtual e o provisionamento do shell, o Ansible realizará as seguintes instruções:

1. Adicionar o repositório do Docker

2. Instalar o Docker

3. Fazer build da imagem da API web

4. Criar um container a partir desta imagem personalizada

O arquivo **playbook.yml** contém as roles, as etapas do provisionamento, que por sua vez, possuem as instruções a serem executadas.

As duas roles executadas nesse projeto são:

- docker: Instalação do Docker

- api: Implantação da API web através de um container

## Resultados

O resultado final será um container da API web do site [VIACEP](https://viacep.com.br)

## Como usar este projeto

Para criar a máquina virtual Vagrant, execute o comando:

`vagrant up`

Para acessar a API web, digite na barra de pesquisa de um navegador web:

`192.168.56.11:8080`
