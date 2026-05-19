# Dash Rio 2026

Dashboard analítico privado para inteligência digital da campanha eleitoral do Rio de Janeiro em 2026.

O projeto é mantido pela organização **DataSocialRJ2026** e reutiliza a base técnica da operação `Eleicoes2026`, agora separada em repositórios próprios, com foco em dados, monitoramento eleitoral, análise de sentimento, menções públicas, comparativos e operação segura.

## Visão executiva

O Dash Rio 2026 centraliza a leitura de menções, sentimentos, temas, redes sociais, publicadores, audiência, evolução temporal e comparativos entre candidatos. A plataforma é privada e voltada para coordenação de campanha, comunicação, marketing político, analistas de dados e liderança executiva.

## Objetivos

- Consolidar dados sociais e analíticos em um dashboard único.
- Acompanhar temperatura digital da campanha.
- Comparar exatamente 2 candidatos por análise.
- Exibir panorama geral, perfil de candidato, últimas menções e visualização bubbles.
- Operar coleta Brandwatch, enriquecimento com IA, indexação Solr e APIs analíticas.
- Garantir segurança, rastreabilidade, TDD, documentação e governança.

## Repositórios principais

| Repositório | Responsabilidade |
|---|---|
| `eleicoesrio2026.backend` | API principal, autenticação, regras analíticas, PostgreSQL, Solr e contratos para o frontend. |
| `eleicoesrio2026.frontend` | Dashboard Angular privado com panorama geral, perfil, menções, comparativo e visualizações analíticas. |
| `eleicoesrio2026.brandwatch.collector` | Coleta Brandwatch, backfill, processamento em lote, Anthropic e indexação Solr. |
| `eleicoesrio2026.gitops` | Kubernetes, ArgoCD, Tekton, Kustomize, observabilidade, deploy e operação. |

## Arquitetura em alto nível

```text
Brandwatch
   -> Collector
      -> Anthropic (enriquecimento quando habilitado)
      -> Solr / PostgreSQL
         -> Backend API
            -> Frontend Angular
               -> Usuários autenticados
```

## Stack

- Java 17/21
- Spring Boot 4
- Angular 21
- TypeScript
- PostgreSQL
- Apache Solr
- Brandwatch API
- Anthropic Batch API
- Docker
- Kubernetes
- ArgoCD
- Tekton
- Kustomize
- Grafana / Prometheus / Alertmanager
- GitHub Actions

## Status do projeto

O projeto está em fase de normalização Rio 2026.

Itens já presentes:

- Backend analítico com JWT e endpoints REST.
- Frontend Angular com login, panorama, perfil, menções e comparativo.
- Collector com Brandwatch, backfill, Solr e Anthropic.
- GitOps com Kubernetes, ArgoCD, Tekton e observabilidade.

Itens em execução/planejamento:

- Ambiente `dashrio`.
- Parametrização de 4 candidatos Rio.
- QueryIds e coleções Rio.
- Visualização bubbles no Dashboard Web.
- Trava de comparativo para exatamente 2 candidatos.
- Remoção de secrets de arquivos versionados.
- Ampliação de testes automatizados com TDD.
- Homologação, observabilidade e go-live assistido.

## Qualidade

A abordagem de qualidade do projeto é **TDD - Test Driven Development**:

1. Red - criar teste falhando antes da implementação.
2. Green - implementar o mínimo necessário para passar.
3. Refactor - melhorar sem quebrar a suíte.

Cada entrega técnica deve possuir:

- Testes automatizados.
- Critérios de aceite verificáveis.
- Pull request revisável.
- Evidência de execução.
- Ausência de regressão conhecida.

## Segurança e LGPD

O projeto trata menções públicas com finalidade específica de inteligência eleitoral. A operação deve seguir:

- Acesso privado e autenticado.
- Controle de perfis e roles.
- Segredos fora do Git.
- HTTPS obrigatório em ambientes publicados.
- Logs sem credenciais.
- Rotação de credenciais antes de produção.
- Minimização e governança de dados.

## Roadmap

O roadmap principal está organizado em sprints semanais:

1. Fundação técnica, segurança e ambientes Rio.
2. Backend/API, candidatos, queries e contratos.
3. Collector, Brandwatch, Solr, Anthropic e backfill.
4. Frontend, UX analítica, bubbles e comparativo 2x.
5. GitOps/Hostinger, QA, observabilidade, homologação e go-live.

## Observação

Esta organização não publica credenciais, tokens, senhas, IPs internos ou detalhes sensíveis de operação. A documentação pública apresenta apenas a visão executiva, técnica e governável do projeto.

