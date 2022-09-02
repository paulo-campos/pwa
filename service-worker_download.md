## 👷 Service Worker

O ciclo de vida de um ServiceWorker, ou **SW**, é completamente separado da sua página da web. Consiste nas seguintes fases:


### Baixar
É quando o navegador faz o download do arquivo `.js` que contém o **SW**, e isso segue com o próprio registro do mesmo, dizendo ao navegador onde está o arquivo **SW**.

```
if ('serviceWorker' in navigator) {
  window.addEventListener('load', () => {
    navigator.serviceWorker.register('/sw.js')
      .then(
        (registration) => {}, // Success case
        (error) => {} // Error case
      );
  });
}
```

O `register()` pode ser chamado em todo carregamento de página, o próprio navegador descobre se o **SW** já foi registrado e o manipula adequadamente.

O local do arquivo do **SW**, nesse caso, está na raiz do domínio, com isso seu escopo será a origem, então esse **SW** receberá eventos de fetch, para tudo nesse domínio.

Registrando o arquivo do **SW** em `/example/sw.js`, por exemplo , ele só verá eventos de fetch para páginas com a URL a partir de `/example/`, ex: `/example/page1/`.

<br>

<p align="center">
  <a href="how-it-works.md#%EF%B8%8F-como-funciona">⏪️ Como funciona</a>
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
  <a href="service-worker_instalation.md#-service-worker" target="_blank">Service Worker - Instalação ⏩</a>
</p>


