# Projeto de GDrvie usando Laravel + Sail + Vue

Link: https://www.youtube.com/watch?v=Wn3IPX_ax-0&ab_channel=freeCodeCamp.org

## Configurar no Windows11

+ Usaremos Laravel + Sail
+ Link da doc oficial para configurar:
  - https://laravel.com/docs/10.x#sail-on-windows


 ## WSL

+ Habilite o WSL e o HyperV no Windows, além de ter o Docker Destop
+ É necessário instalar o Ubuntu tambpem, ele nâo vem como padrâo, vá na loja do Windows e baixa ele.

## Comandos docker

docker ps
+ Ver o que está rodando no docker

## Comandos sail

Abir bash dentro do container docker

````sh
./vendor/bin/sail bash
````

## COmando do artisan

php artisan --help


## Criar Projeto

+ Abra o terminal Ubuntu (no git brasnh nâo funciona)
+ Execute o comando a seguir:
  - OBS: substitua `example-app` pelo nome da sua aplicação

````sh
curl -s https://laravel.build/example-app | bash
````

+ Execute o sail com o comando a seguir entrando na pasta do projeto:

````sh
./vendor/bin/sail up
````

Vai baixar várias imagens docker e também vai pedir a senha do seu usuário ubuntu no final e por fim executar.

Se tudo der certo a aplicaçâo vai está na porta 80, entâo baxas entrar em [localhost](localhost)

no temrinal ubutnu vocÊ pode abrir o explorer a parti do comando a seguir:

````sh
explore.exe .
````

Execute ele dentro do proejto e depois abra o vs-code

## Configurando o intertia

entra no bash do sail com `./vendor/bin/sail bash`

e execute

````sh
npm i
````

vai baixar umas dependeicas basicas que vem por pardao

### Baixar o breeze

Priemrio baixe no laravel pelo composer

````sh
composer require laravel/breeze --dev
````

depois 

````
php artisan breeze:install
````

Escolhavue com interia

````
php artisan breeze:install

 ┌ Which Breeze stack would you like to install? ───────────────┐
 │ › ○ Blade with Alpine                                        │
 │   ○ Livewire (Volt Class API) with Alpine                    │
 │   ○ Livewire (Volt Functional API) with Alpine               │
 │   ○ React with Inertia                                       │
 │   ● Vue with Inertia                                         │
 │   ○ API only                                                 │
 └──────────────────────────────────────────────────────────────┘
````

e tudo a mais coloca como `no`

rode migrate para caregar o banco com tabelas para ldiar com password

````
 
php artisan migrate
npm install
npm run dev
````

###

app/models/User.php coloque `implements``

class User extends Authenticatable implements MustVerifyEmail

## Brezee e o teste de email

O que é o brezze pelo chat gpt:

Laravel Breeze é um kit inicial (starter kit) leve e personalizável para Laravel, projetado para facilitar a configuração inicial de autenticação e fornecer uma estrutura básica para novos projetos Laravel. Ele oferece uma implementação simplificada de autenticação com recursos mínimos para começar a desenvolver rapidamente.

O Laravel Breeze foi criado para ser uma alternativa mais leve e simples ao scaffolding de autenticação mais robusto fornecido pelo Laravel UI. Ele é construído usando o mecanismo de templates Blade do Laravel e estilizado com o framework CSS Tailwind CSS.

O kit inclui as funcionalidades básicas de registro, login e redefinição de senha, o que é particularmente útil quando você precisa de autenticação em seus projetos, mas deseja evitar a complexidade de configurações adicionais que podem ser oferecidas por outras opções mais completas.

A instalação do Laravel Breeze é feita via Composer, e, após a instalação, você pode executar comandos do Artisan para configurar a autenticação em sua aplicação. Aqui está um exemplo básico de instalação:

```bash
composer require laravel/breeze --dev
php artisan breeze:install
npm install && npm run dev
```

O Laravel Breeze foi projetado para ser flexível e fácil de estender. Se você precisar de funcionalidades adicionais, pode personalizar e expandir o código conforme necessário para atender aos requisitos específicos do seu projeto.

Lembre-se de consultar a documentação oficial do Laravel para obter informações mais recentes sobre Laravel Breeze, pois podem ter ocorrido atualizações desde minha última atualização de conhecimento em janeiro de 2022.

### Tesntadno email no brezze

acessae localhost, depois vai em regitrar e regitre-se como um site normal. Via ter enviado um email de confirmaçao.

MAS NAO VAI ENVIAR PAR AO SEU EMIAL. tme um loca que tetar isso, é no servidor de email que tambe foiinciaindo,voce acesasr em:

http://localhost:8025/

vai la e confirma


## criando tabelas

php artisan make:model File -m
php artisan make:model FileShare -m
php artisan make:model StarredFile -m


isso vai cirari arquivos e migrations

agoravamos vamos foca rnas migrations

## Micgarions

coloque as m igratiosn que etao em

``/database/migrations/``


copie do git e cole aqui só a parte do  `up`

depois execute com

php artisan migrate

Agroa deve dar porlbme pois temos que confiugra ro nestedSet

## 3 o que é nestseset pelo chatpgt

Conjunto aninhado, ou Modelo de Conjunto Aninhado, é uma maneira eficaz de armazenar dados hierárquicos em uma tabela relacional. De acordo com a Wikipedia:

O modelo de conjunto aninhado consiste em numerar os nós de acordo com uma travessia de árvore, que visita cada nó duas vezes, atribuindo números na ordem de visitação e em ambas as visitas. Isso deixa dois números para cada nó, que são armazenados como dois atributos. Consultar torna-se econômico: a associação hierárquica pode ser testada comparando esses números. Atualizar requer renúmeração e, portanto, é dispendioso.

Aplicações
O Conjunto Aninhado mostra bom desempenho quando a árvore é raramente atualizada. Ele é ajustado para ser rápido ao obter nós relacionados. É ideal para construir menus ou categorias de várias profundidades para uma loja.

##

## nested set

Será necessa´rio para o nosos banco de dados

pesguise no google `laravel neste-sets`

e vá até a pagina

`https://github.com/lazychaser/laravel-nestedset`

utilize o composer para baixar isos

vamos executar o comando do comporse

````
composer require kalnoy/nestedset
````

so depois disos o `php artisan migrate` deve dá certo

## Agora vamos olhar o mysql do sairl

host: localhost
user: sail
senha: password

A extensao 'MySQL' do Weijan Chen no VSCode, essa funcionu.

## Explorando a estrutura do invetia

fica em  'resources/js' e o csss vem por default o tailwind