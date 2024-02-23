# Como instalar o Docker no Ubuntu

O Docker é uma plataforma de software que permite automatizar a implantação e o gerenciamento de aplicativos em contêineres. Contêineres permitem empacotar um aplicativo com todas as partes necessárias, como bibliotecas e outras dependências, e implantá-lo como uma única unidade.

Neste artigo, vamos abordar os passos para instalar o Docker no Ubuntu, uma das distribuições Linux mais populares.

## Pré-requisitos

Antes de começarmos, certifique-se de ter acesso a um terminal de linha de comando em um sistema Ubuntu. Além disso, é recomendado ter privilégios administrativos para executar os comandos com `sudo`.

## Passo 1: Atualizar o sistema

O primeiro passo é garantir que o sistema esteja atualizado. Abra um terminal e execute os seguintes comandos:

```bash
sudo apt update
sudo apt upgrade
```

Isso garantirá que todos os pacotes existentes estejam atualizados para as versões mais recentes.

## Passo 2: Instalar as dependências necessárias

Para garantir que o sistema tenha as dependências necessárias, instale o `curl` e os `ca-certificates` com o seguinte comando:

```bash
sudo apt-get install ca-certificates curl
```

## Passo 3: Adicionar a chave GPG do Docker

O Docker distribui seus pacotes assinados digitalmente. Adicione a chave GPG oficial do Docker ao sistema:

```bash
sudo install -m 0755 -d /etc/apt/keyrings
sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
sudo chmod a+r /etc/apt/keyrings/docker.asc
```

## Passo 4: Adicionar o repositório do Docker ao sistema

Agora, precisamos adicionar o repositório do Docker aos repositórios APT do Ubuntu. Execute o seguinte comando para adicionar o repositório:

```bash
echo "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu \
$(. /etc/os-release && echo "$VERSION_CODENAME") stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```

## Passo 5: Atualizar os repositórios e instalar o Docker

Após adicionar o repositório, atualize a lista de pacotes disponíveis e instale o Docker:

```bash
sudo apt-get update
sudo apt-get install docker-ce docker-ce-cli containerd.io
```

## Passo 6: Verificar a instalação do Docker

Após a instalação, verifique se o Docker foi instalado corretamente executando o seguinte comando:

```bash
docker --version
```

Você deve ver a versão do Docker instalada no seu sistema.

## Conclusão

Parabéns! Você instalou o Docker com sucesso no seu sistema Ubuntu. Agora você pode começar a usar o Docker para empacotar, distribuir e executar seus aplicativos em contêineres. Se você estiver interessado em aprender mais sobre como usar o Docker, confira a documentação oficial em [https://docs.docker.com](https://docs.docker.com).

Este artigo forneceu um guia passo a passo para instalar o Docker no Ubuntu. Se você encontrar algum problema durante a instalação, consulte a documentação oficial do Docker ou procure ajuda na comunidade.