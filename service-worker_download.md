## 👷 Service Worker

O ciclo de vida de um Service Worker é completamente separado da sua página da web. Consiste nas seguintes fases:


### Baixar
É quando o navegador faz o download do arquivo `.js` que contém o ServiceWorker, e isso segue com o próprio registro do mesmo, dizendo ao navegador onde está o arquivo ServiceWorker.

```
if ('serviceWorker' in navigator) {
  window.addEventListener('load', () => {
    navigator.serviceWorker.register('/sw.js')
      .then(
        (registration) => {}, // Success case
        (registration) => {} // Error case
      );
  });
}
```

<br>

<p align="center">
  <a href="how-it-works.md#%EF%B8%8F-como-funciona">⏪️ Como funciona</a>
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
  <a href="service-worker_instalation.md#-service-worker" target="_blank">Service Worker - Instalação ⏩</a>
</p>


