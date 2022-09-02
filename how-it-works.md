## 🛠️ Como funciona?

Combinando diversos componentes técnicos:

<br>

### Service worker

<img width="145" alt="Captura de Tela 2022-09-01 às 21 52 00" src="https://user-images.githubusercontent.com/10121394/188036253-800c937f-3eca-493a-85ae-f4c466e11101.png">

Componente Javascript, que funciona como um proxy entre o navegador e a rede, gerenciando as notificações por push e possibilitando a criação de um aplicativo web offline, através da API de cache do navegador.

Ele armazena todos os recursos necessários no cache do navegador. Dessa forma, quando um usuário utilizar um aplicativo e decidir retornar seu uso novamente, tudo vai estar da mesma maneira que ele deixou, como seria em um app, de fato.

<br>

### Manifest

<img width="166" alt="Captura de Tela 2022-09-01 às 21 52 11" src="https://user-images.githubusercontent.com/10121394/188036216-a76f0120-7c56-4856-9de8-d719d1b04b29.png">

Arquivo que contém todas as informações do aplicativo, como o ícone que aparece na tela inicial do dispositivo, o nome abreviado do app, o plano de fundo ou o tema, entre outras configurações.

<br>

### HTTPS

<img width="72" alt="Captura de Tela 2022-09-01 às 21 54 57" src="https://user-images.githubusercontent.com/10121394/188036483-461a9761-79e8-4b3d-a30e-dae333b94da8.png">

Com o service worker realizando a ponte entre as solicitações de rede e os resultados no aplicativo para o usuário, o PWA precisa do HTTPS e seu protocolo para total segurança do funcionamento.

<br>

### Responsividade

Apesar de uma aplicação não ser responsiva não a impede de ser instalável, ela ser instalável sem ser responsiva é o mesmo:

<p align="center">
  <img alt="PWA - responsividade = Fuck shit" src="https://user-images.githubusercontent.com/10121394/188037030-f5b6a1c7-321d-4233-b83f-313573d38b2a.gif">
</p>

<br>

<p align="center">
  <a href="introduction.md#-introdução">⏪️ Introdução</a>
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
  <a href="how-it-works.md#%EF%B8%8F-como-funciona">Como funciona ⏩</a>
</p>
