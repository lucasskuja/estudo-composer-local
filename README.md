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
