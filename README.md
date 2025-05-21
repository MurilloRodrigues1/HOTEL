# HOTEL - projeto 🛎️

_Este é um sistema de gerenciamento de hotel desenvolvido com Django. Ele permite cadastrar quartos, clientes e realizar reservas de forma prática e eficiente. Ideal para pequenos e médios estabelecimentos hoteleiros._

> Caio Pietro Fernandes - N° 03
>  
> Daniel Fonseca Monteiro - N° 05
>  
> Daniele Amaral Santos - N° 07
> 
> Matheus Vinicius Gatto - N° 25
> 
> Murillo Henrique de Oliveira Rodrigues - N° 26
> 
___

### LINKS DE APOIO 🔗
> trello ->  https://trello.com/invite/b/681b9cad0a474cf0d867f30c/ATTI2d08f2b9d14cb3e36c715249d4d8fc7f9E196C58/hotelaria   
> notion -> https://lizard-tangerine-a45.notion.site/RASCUNHO-Hotelaria-1ec6cd955f7a80c5a5e2deb5d4149398?pvs=4
___

### 07/05  
  _O projeto começou com o professor dando ajuda com o passo a passo para preparar o django, o professor usou as etapas passadas na ultima aula, com isso seguimos o resto do dia configurando o Django, porque é uma parte trabalhosa, por isso o apoio do professor é necessário, acreditamos que a parte mais importante da preparação do "ambiente" são os comandos setados para criar de maneira correta o django:    
###  _INICIANDO O AMBIENTE VIRTUAL_ 🔧
```
python -m venv venv
```
```
.\venv\Scripts\Activate.ps1
```
_INSTALANDO O DJANGO_
```
pip install django
```
- Criando o projeto
```
django-admin startproject "nome do projeto"
cd "nome do projeto"
```
- Criando a aplicação
```
python manage.py startapp "outro nome para projeto"
```
- Rodando a aplicação
```
python manage.py runserver
```
___
## INICIANDO UM PROJETO DJANGO
1. Executar o comando para iniciar um projeto
```
django-admin startproject teste01
```
2. Abrir a pasta teste01 no terminal do projeto, executando o comando:
```
cd teste01
```
3. Executar o runserver:
```
python manage.py runserver
```
Vamos revisar a estrutura do nosso projeto. Assim que criarmos nosso projeto, teremos o arquivo **`manage.py`** e a pasta com o mesmo nome do projeto, além dos demais arquivos.

Dentro dessa pasta, teremos o arquivo **`__init__.py`**, que estará vazio. Esse arquivo indica para o Python que essa pasta **`teste01`** faz parte de um módulo Python.

Os arquivos **`asgi.py`** e **`wsgi.py`** são os arquivos de configuração que, quando colocarmos o site em um servidor, o servidor saberá como lidar com esse projeto. Utilizaremos esses arquivos apenas no momento de fazer o **deploy** do projeto.

No arquivo **`urls.py`**, é onde definiremos os links, os endereços das páginas do nosso site. Já o **`settings.py`** é onde iremos de fato configurar o projeto. É dentro desse arquivo que definiremos as configurações e as informações essenciais para o nosso site funcionar corretamente. 



### 21/05
_Demos continuidade à parte principal do projeto, ainda com o apoio do professor. Estamos na etapa de configuração do sistema, incluindo a definição de quem será o administrador. Nesta aula, o foco foi configurar e preparar o código responsável por auxiliar os usuários na reserva dos quartos. De forma resumida, conseguimos implementar a seleção do quarto desejado pelo cliente, além de exibir se o quarto está reservado ou disponível. Aproveitamos também para definir o preço de cada quarto disponível no sistema._



  
 
 
