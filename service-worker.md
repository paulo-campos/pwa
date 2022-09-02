## 👷 Service Worker

O ciclo de vida de um Service Worker é completamente separado da sua página da web. Consiste nas seguintes fases:


### Baixar
É quando o navegador faz o download do arquivo `.js` que contém o Service Worker.

### Instalação
Para instalar um Service Worker, primeiro deve-se registrá-lo.

Ao registrar o Service Worker, você diz ao navegador onde reside o arquivo JavaScript do Service Worker. Vamos ver o seguinte código:

```
if ('serviceWorker' in navigator) {
  window.addEventListener('load', function() {
    navigator.serviceWorker.register('/sw.js').then(function(registration) {
      // Registration was successful
      console.log('ServiceWorker registration successful');
    }, function(err) {
      // Registration failed
      console.log('ServiceWorker registration failed: ', err);
    });
  });
}
```

###  Ativação
Depois que o Service Worker for instalado, a próxima etapa será sua ativação.Esta etapa é uma ótima oportunidade para gerenciar caches anteriores.

Uma vez ativado, o Service Worker começará a controlar todas as páginas que estiverem no escopo. Um fato interessante: a página que registrou o Service Worker pela primeira vez não será controlada até que a página seja carregada novamente. Depois que o Service Worker estiver no controle, ele estará em um dos seguintes estados:

Ele manipulará os eventos de busca e mensagem que ocorrem quando uma solicitação ou mensagem de rede é feita a partir da página
Será terminado para economizar memória
Aqui está como o ciclo de vida será semelhante:


