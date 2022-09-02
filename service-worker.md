## 👷 Service Worker

O ciclo de vida de um Service Worker é completamente separado da sua página da web. Consiste nas seguintes fases:


### Baixar
É quando o navegador faz o download do arquivo .js que contém o Service Worker.

### Instalação
Para instalar um Service Worker para seu aplicativo da Web, você deve registrá-lo primeiro, o que pode ser feito em seu código JavaScript. Quando um Service Worker é registrado, ele solicita ao navegador que inicie uma etapa de instalação do Service Worker em segundo plano.

Ao registrar o Service Worker, você diz ao navegador onde reside o arquivo JavaScript do Service Worker. Vamos ver o seguinte código:


O código verifica se a API do Service Worker é suportada no ambiente atual. Se estiver, o Service Worker /sw.js está registrado.

Você pode chamar o método register() sempre que uma página for carregada sem preocupação - o navegador descobrirá se o funcionário do serviço já foi registrado e o manipulará adequadamente.

Um detalhe importante do método register() é o local do arquivo do service worker. Nesse caso, você pode ver que o arquivo do service worker está na raiz do domínio. Isso significa que o escopo do prestador de serviços será a origem inteira. Em outras palavras, esse service worker receberá eventos de fetch(que discutiremos mais adiante) para tudo nesse domínio. Se registrarmos o arquivo do service worker em /example/sw.js , o service worker só verá eventos de fetch para páginas cujos URLs começam com /example/ ( /example/page1/ , /example/page2/ ).

Durante a fase de instalação, é melhor carregar e armazenar em cache alguns ativos estáticos. Depois que os recursos são armazenados em cache com êxito, a instalação do Service Worker é concluída. Se não (o carregamento falha) — o Service Worker fará uma nova tentativa. Uma vez instalado com sucesso, você saberá que os ativos estáticos estão no cache.

Isso responde à sua pergunta se o registro precisar acontecer depois do evento de carregamento. Não é uma obrigação, mas é definitivamente recomendado.

Por quê? Vamos considerar a primeira visita de um usuário ao seu aplicativo da web. Ainda não há service worker, e o navegador não tem como saber antecipadamente se haverá um service worker que eventualmente será instalado. Se o Service Worker for instalado, o navegador precisará gastar CPU e memória extras para esse encadeamento adicional, caso contrário, o navegador gastará na renderização da página da Web.

O importante é que, se você simplesmente instalar um Service Worker em sua página, estará correndo o risco de atrasar o carregamento e a renderização — não tornando a página disponível para seus usuários o mais rápido possível.

Observe que isso é importante apenas para a primeira visita à página. Visitas de páginas subseqüentes não são afetadas pela instalação do Service Worker. Quando um Service Worker é ativado em uma primeira visita à página, ele pode manipular eventos de carregamento/armazenamento em cache para visitas subsequentes ao seu aplicativo da web. Tudo isso faz sentido, porque precisa estar pronto para lidar com conectividade de rede limitada.

###  Ativação
Depois que o Service Worker for instalado, a próxima etapa será sua ativação.Esta etapa é uma ótima oportunidade para gerenciar caches anteriores.

Uma vez ativado, o Service Worker começará a controlar todas as páginas que estiverem no escopo. Um fato interessante: a página que registrou o Service Worker pela primeira vez não será controlada até que a página seja carregada novamente. Depois que o Service Worker estiver no controle, ele estará em um dos seguintes estados:

Ele manipulará os eventos de busca e mensagem que ocorrem quando uma solicitação ou mensagem de rede é feita a partir da página
Será terminado para economizar memória
Aqui está como o ciclo de vida será semelhante:


