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

## 07/05  
  _O projeto começou com o professor dando ajuda com o passo a passo para preparar o django, o professor usou as etapas passadas na ultima aula, com isso seguimos o resto do dia configurando o Django, porque é uma parte trabalhosa, por isso o apoio do professor é necessário, acreditamos que a parte mais importante da preparação do "ambiente" são os comandos setados para criar de maneira correta o django:    
###  _INICIANDO O AMBIENTE VIRTUAL_ (no terminal) 🔧

_Criar o ambiente virtual pelo terminal_
_Ctrl + Shift + "_
```
python -m venv venv
```
_Entrar no ambiente virtual_
```
.\venv\Scripts\Activate.ps1
```

_INSTALANDO O DJANGO_
_No VSCode, dentro da pasta do projeto com Django, executar o comando_
```
pip install django
```
_Para conferir de todo o procedimento foi feito corretamente, execute:_
```
django-admin
```

- Criando o projeto
```
django-admin startproject "nome do projeto"
cd "nome do projeto"
```
```
python manage.py runserver
```
_Ele te dará um link que poderá ser aberto no navegador. Ao abrir, você irá visualizar o desenho de um foguete azul._

- Aplicativos(APP) dentro do Projeto
_Assim, em todo projeto Django, após criar o projeto, você irá acessar a página do projeto e dentro dela executar_
```
python manage.py startapp "nome da app"
```

___
## Criar e configurar um template
1. Crie a pasta **'templates'** e a **'index'** dentro do **'APP'**
2. Mude as **'settings.py'** na parte de templates
```
import os

TEMPLATES = [
    {
        'BACKEND': 'django.template.backends.django.DjangoTemplates',
        'DIRS': [os.path.join(BASE_DIR, 'templates')], 
        'APP_DIRS': True,
        'OPTIONS': {
            'context_processors': [
                'django.template.context_processors.request',
                'django.contrib.auth.context_processors.auth',
                'django.contrib.messages.context_processors.messages',
            ],
        },
    },
]
```
3. Em **'views'**, dentro do **'projeto_app'**, vamos retornar a página criada, nesse caso, o index:
```
from django.http import HttpResponse
from django.shortcuts import render


def index(request):
    return render(request, "index.html")
```
4. Em **'urls'** dentro de **'projeto'**, adicione a urlpatterns no código. O código completo ficará assim:
```
from django.contrib import admin
from django.urls import include, path
from django.conf import settings
from django.conf.urls.static import static

urlpatterns = [
    path("", include("polls.urls")),
    path("admin/", admin.site.urls),
]

if settings.DEBUG:
    urlpatterns += static(settings.MEDIA_URL, document_root=settings.MEDIA_ROOT)
    urlpatterns += static(settings.STATIC_URL, document_root=settings.STATIC_ROOT)
```

___
## Pastas static e media
1. Na pasta raíz do projeto, nesse caso, **'xxx_projeto'**, criar as pastas **'static'** e **'media'**
```
xxx_projeto/
├── xxx_app
├── xxx_projeto
├── media
├── static
├── db.sqlite3
├── manage.py
└── venv
```
2. No **'settings.py'** configurar ele com as pastas novas. Adicionar isso ao arquivo
```
# começo do codigo
import os

# fim do codigo
# Arquivos estáticos (CSS, JS, imagens)
STATIC_URL = '/static/'
STATICFILES_DIRS = [os.path.join(BASE_DIR, 'static')]
STATIC_ROOT = os.path.join(BASE_DIR, 'staticfiles')  # para produção

# Arquivos de mídia (uploads)
MEDIA_URL = '/media/'
MEDIA_ROOT = os.path.join(BASE_DIR, 'media')
```
3. Modificar a pasta de **'urls.py'** da pasta do projeto **'xxx_projeto'** 
```
# importar
from django.conf import settings
from django.conf.urls.static import static

urlpatterns = [
    # continuar com as urls aqui
]

if settings.DEBUG:
    urlpatterns += static(settings.MEDIA_URL, document_root=settings.MEDIA_ROOT)
    urlpatterns += static(settings.STATIC_URL, document_root=settings.STATIC_ROOT)
```

___
## Configurar um super user
1. Para aplicar as migrações do Django e do app:
```
python manage.py makemigrations

python manage.py migrate
```
2. Para criar um super user, rodar o comando no terminal:
```
python manage.py createsuperuser
```
3. No navegador, adicionar a rota **'/admin/'** do lado na url e fazer login do super user


Vamos revisar a estrutura do nosso projeto. Assim que criarmos nosso projeto, teremos o arquivo **`manage.py`** e a pasta com o mesmo nome do projeto, além dos demais arquivos.
Dentro dessa pasta, teremos o arquivo **`__init__.py`**, que estará vazio. Esse arquivo indica para o Python que essa pasta **`teste01`** faz parte de um módulo Python.
Os arquivos **`asgi.py`** e **`wsgi.py`** são os arquivos de configuração que, quando colocarmos o site em um servidor, o servidor saberá como lidar com esse projeto. Utilizaremos esses arquivos apenas no momento de fazer o **deploy** do projeto.
No arquivo **`urls.py`**, é onde definiremos os links, os endereços das páginas do nosso site. Já o **`settings.py`** é onde iremos de fato configurar o projeto. É dentro desse arquivo que definiremos as configurações e as informações essenciais para o nosso site funcionar corretamente. 
Em cada aplicativo criado, também teremos alguns arquivos que serão gerados automaticamente. Entre eles, um arquivo **`__init__.py`** que também iniciará vazio e indicará que a pasta **loja** é um aplicativo do nosso projeto.
A pasta **`migrations`** será responsável por gerenciar e registrar as modificações no banco de dados.
O **`admin.py`** será onde você configurará o que será exibido na tela de administração do site, ou seja, o que o usuário que é administrador do site visualizará ao acessá-lo.
No **`apps.py`**, você irá configurar e registrar os aplicativos referentes à aplicação **`nomedoaplicativo`**. Por padrão, o Django já irá criar o app referente à sua aplicação, e costumamos deixar apenas um app por aplicação mesmo.
O arquivo **`tests.py`**, como o próprio nome sugere, serve para que você execute os testes da sua aplicação.
Por fim, temos dois arquivos muito importantes: o **`models.py`** e o **`views.py`**. Esses arquivos são os que você mais utilizará e modificará.
No **`models.py`**, é onde você definirá as informações que serão registradas no seu sistema e no seu banco de dados. O **`views.py`** é onde definirá a lógica por trás do seu site, ou seja, onde você definirá as funções ou classes que serão executadas quando o usuário acessar um link específico do seu site.



## 21/05
_Demos continuidade à parte principal do projeto, ainda com o apoio do professor. Estamos na etapa de configuração do sistema, incluindo a definição de quem será o administrador. Nesta aula, o foco foi configurar e preparar o código responsável por auxiliar os usuários na reserva dos quartos. De forma resumida, conseguimos implementar a seleção do quarto desejado pelo cliente, além de exibir se o quarto está reservado ou disponível. Aproveitamos também para definir o preço de cada quarto disponível no sistema._



  
 
 
