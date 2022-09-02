## 👷👷 Service Worker

### Instalação

Durante a instalação, é melhor carregar e manter em cache os ativos estáticos. Depois que são armazenados em cache, a instalação do **SW** finaliza. Se não, o carregamento falha e o **SW** tenta novamente

Com isso sabemos que o registro não precisar acontecer depois do evento de carregamento, mas é altemente recomendado.

Considere a primeira visita de um usuário ao seu aplicativo web. Ainda não há **SW**, e o navegador não sabe antecipadamente se haverá um que eventualmente será instalado. Se o **SW** for instalado, o navegador precisagastar CPU e memória extras para esse encadeamento, caso contrário, o navegador gasta na renderização da página.

O importante é que, se você simplesmente instalar um **SW** em sua página, corre o risco de atrasar o carregamento e a renderização.

Mas isso é importante apenas para a primeira visita à página. Visitas subseqüentes não são afetadas pela instalação do **SW**. Quando é ativado em uma primeira visita à página, ele pode manipular eventos de carregamento/armazenamento em cache para visitas subsequentes.

<br>

<p align="center">
  <a href="service-worker_download.md#-service-workersw">⏪️Service Worker - Download ⏩</a>
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
  <a href="service-worker_activation.md#-service-worker">Service Worker - Ativação ⏩</a>
</p>