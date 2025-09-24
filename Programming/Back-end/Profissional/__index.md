---
type: "[[Map of Content]]"
tags:
  - planetary_system
  - programming
date: 24-09-2025
---
## 🗺️ Overview
Este roadmap cobre os tópicos avançados de backend que eu ainda não estudei, focando em sistemas escaláveis, assíncronos e profissionais, incluindo mensageria, GraphQL, arquitetura avançada, escalabilidade e DevOps. Ele é estruturado em níveis, com mini-projetos práticos para aplicar cada conceito.

## 📂 Planets
- [[Nível 1 – Mensageria e Assíncrono]]
- [[Nível 2 – GraphQL]]
- [[Nível 3 – Arquitetura Avançada]]
- [[Nível 4 – Escalabilidade]]
- [[Nível 5 – DevOps / Monitoramento]]

---

## [[Nível 1 – Mensageria e Assíncrono]]
- **RabbitMQ**
  - Conceitos: filas, exchanges, routing keys.
  - Prática: criar API que envia emails ou processa imagens via fila.
- **Kafka**
  - Conceitos: tópicos, producers, consumers, partitions.
  - Prática: criar sistema de logs de eventos (ex.: pedidos criados → eventos processados em outro serviço).
- **Mini-projeto:** API de pedidos → envia eventos para RabbitMQ ou Kafka → outro serviço consome eventos e atualiza status do pedido.

---

## [[Nível 2 – GraphQL]]
- Conceitos: queries, mutations, subscriptions.
- Ferramentas Python: Graphene, Ariadne, Strawberry.
- Prática: converter uma API REST simples em GraphQL.
- **Mini-projeto:** API de usuários e posts com GraphQL: cliente pede posts e autores em uma única query, sem overfetching.

---

## [[Nível 3 – Arquitetura Avançada]]
- **Event-driven:** serviços reagem a eventos em vez de chamarem uns aos outros diretamente.
- **Microservices:** dividir aplicação monolítica em serviços independentes; comunicação via HTTP, mensageria ou gRPC.
- **CQRS:** separar leitura e escrita para otimizar performance.
- **Event Sourcing:** armazenar eventos e reconstruir estado.
- **Mini-projeto:** Sistema de e-commerce simples:
  - Serviço de pedidos → evento “pedido criado”.
  - Serviço de estoque → consome evento e atualiza inventário.
  - Serviço de notificação → envia email para o usuário.

---

## [[Nível 4 – Escalabilidade]]
- **Load Balancing:** distribuir requisições entre múltiplos servidores (Nginx, HAProxy).
- **Caching:** Redis ou Memcached para reduzir carga no banco.
- **Rate Limiting / Throttling:** limitar requisições para evitar sobrecarga (FastAPI/Flask).
- **Mini-projeto:** API de posts com Redis cache para queries mais comuns e limite de requisições por IP.

---

## [[Nível 5 – DevOps / Monitoramento]]
- **CI/CD:** GitHub Actions, GitLab CI, Jenkins; pipeline: testes → build docker → deploy.
- **Monitoramento:**
  - Prometheus + Grafana → métricas da API (latência, requests/sec, erros).
  - Sentry → captura de exceções em produção.
- **Mini-projeto:**
  - Configurar pipeline CI/CD para a API do mini-projeto de e-commerce.
  - Integrar métricas com Prometheus + Grafana.
  - Captura de erros via Sentry.

---

## 🔎 Review in the future
- Adicionar tópicos sobre **gRPC** e comunicação entre microservices.
- Explorar **serverless** e **cloud functions**.
- Implementar **event-driven patterns mais avançados**.
- Integrar **mensageria e GraphQL em sistemas reais**.