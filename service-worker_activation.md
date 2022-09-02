## 👷👷👷 Service Worker

### Ativação

Esta etapa é uma ótima oportunidade para gerenciar caches anteriores.

Uma vez ativado, o **SW** começa a controlar todas as páginas que estiverem no escopo. Importante, a página que registrou o **SW** pela primeira vez não será controlada até que  seja carregada novamente. Depois que o **SW** estiver no controle, ele estará em um dos seguintes estados:

- Menipulando os eventos de busca e mensagem quando uma solicitação ou mensagem de rede é feita a partir da página
- Terminado para economizar memória

Aqui está como o ciclo de vida será semelhante:

<br>

<p align="center">
  <a href="service-worker_instalation.md#-service-worker">⏪️ Service Worker - Instalação</a>
</p>