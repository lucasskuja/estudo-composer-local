# Estudo Composer Local

Esse projeto tem como intuito o estudo da ferramenta disponibilizada pela **Google Composer Local Development CLI tool**

De uma forma resumida, o Google desenvolveu um código que ao ser executado cria no Docker local da máquina um Composer com as mesmas características do Composer que é disponibilizado como serviço na cloud.

No deploy não serão criados discos no ambiente docker, sendo assim, todos os fontes (dags, configurações, sql`s), estarão armazenados no disco local da máquina que irá executar o Docker + Composer

> Para maiores informações entre [acesse esse link](https://cloud.google.com/composer/docs/composer-2/run-local-airflow-environments).

## Pré Requisitos

- Python >= 3.8
- [gcloud CLI](https://cloud.google.com/sdk/docs/install?hl=pt-br)
- [Docker](https://www.docker.com/)
- Mínimo memória Notebook ou CPU - 8G, ideal 16G
- Mínimo memória docker - 4G, ideal 8G

## Antes de configurar

1. clonar esse projeto na sua máquina local: `git clone https://github.com/lucasskuja/estudo-composer-local.git`
1. Após o clone acessar o diretório onde a pasta `composer-local-dev` está. Ex: `cd composer-local-dev`
1. É recomendável que para evitar problemas e isolarmos a versão do python, trabalhar com uma virtualenv. 
~~~Shell
# Linux
virtualenv venv
virtualenv --python=$(which python$VERSAO) venv # EXEMPLO: virtualenv --python=$(which python$3.9)
source venv/bin/activate
~~~
~~~PowerShell
# Windows
python -m venv venv
python -m venv --python=pythonVERSAO venv
.\venv\Scripts\Activate.ps1
~~~
> _Lembrando que este passo não é obrigatório._
4. Após isso é só seguir o passo a passo de configuração do composer-local descrito no repositório `composer-local-dev` [nesse link](https://github.com/GoogleCloudPlatform/composer-local-dev/blob/eacc17c2c934b7873b7302f4d6b2dd9bdaf6d9d8/README.md#configure-credentials)