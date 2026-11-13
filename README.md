# ChamyFlix

## Visão geral

ChamyFlix é um projeto de concepção de um site de streaming personalizado, voltado para organizar a experiência de consumo com base em preferências do usuário, histórico de visualização e relevância por gênero. O objetivo principal é reduzir a sobrecarga de escolhas e oferecer uma home mais inteligente, com recomendações mais alinhadas ao comportamento e ao perfil de cada pessoa.

O repositório reúne a documentação e a modelagem do sistema, incluindo cenário de negócio, casos de uso, diagrama de domínio, arquitetura em camadas e prototipação, com foco em especificação conceitual e análise de requisitos.

## Objetivo do produto

O produto proposto busca:

- apresentar um catálogo personalizado por gênero e perfil de consumo;
- reforçar a descoberta de conteúdos inéditos por meio de recomendações semanais;
- melhorar a transparência e a aderência das sugestões ao gosto do usuário;
- oferecer uma experiência consistente em celular, computador e TV;
- permitir que o administrador gerencie o catálogo de conteúdos;
- enviar notificações relevantes sobre lançamentos e novidades.

## Contexto de negócio

O problema identificado é a dificuldade de manter atenção em conteúdos de longa duração em um ambiente dominado por vídeos curtos e pelo excesso de opções disponíveis. Nesse cenário, a plataforma precisa ajudar o usuário a encontrar rapidamente algo pertinente, com base em hábitos de consumo e em preferências recentes.

O sistema propõe uma solução que combina:

- organização dinâmica da página inicial;
- classificação por gênero e por interesse individual;
- sugestões com base no histórico de uso;
- notificações com foco em horários e dispositivos de consumo;
- autonomia administrativa para atualização do catálogo.

## Público-alvo

O produto foi pensado para:

- consumidores de maratona que buscam conteúdos com boa aderência ao perfil;
- usuários com rotina acelerada, que precisam de escolhas rápidas e relevantes;
- fãs de nichos específicos, como documentários, animes e doramas;
- pessoas que valorizam consistência entre dispositivos e experiências personalizadas.

## Casos de uso principais

Os principais casos de uso do sistema são:

- UC01 — Visualizar catálogo personalizado
- UC02 — Receber descoberta semanal
- UC03 — Pesquisar conteúdo com sugestões de termos
- UC04 — Avaliar conteúdo assistido
- UC05 — Gerenciar catálogo
- UC06 — Notificar lançamentos

Esses fluxos definem o comportamento central da plataforma e servem de base para a modelagem de domínio e para a estruturação das especificações do projeto.

## Modelo de domínio

A modelagem de domínio identificou conceitos centrais do problema, como:

- Usuário
- Sessão de visualização
- Item assistido
- Conteúdo
- Gênero
- Catálogo
- Dispositivo
- Avaliação

Esses elementos representam os principais atores e objetos do sistema e reforçam a lógica de recomendação, histórico, organização por gênero e consistência entre telas.

## Arquitetura conceitual

A estrutura conceitual do sistema foi organizada em camadas, incluindo:

- Camada de apresentação
- Camada de aplicação
- Camada de domínio
- Camada de infraestrutura

A arquitetura sugere uma separação entre interface do usuário, regras de negócio, modelo de domínio e mecanismos de persistência e notificação. O objetivo é manter a solução organizada, legível e adequada para evolução em etapas futuras.

## Documentação e artefatos do projeto

Este repositório contém a base documental para a concepção do sistema. A seguir, o mapa dos principais arquivos:

### Base de cenário e requisitos

- [TG1_-_Site_de_streaming.md](./TG1_-_Site_de_streaming.md) — visão geral do cenário de negócio, proposta do sistema e modelo de caso de uso.
- [sitedestreaming_tg1.md](./sitedestreaming_tg1.md) — detalhamento dos casos de uso e do fluxo principal do caso crítico.
- [cenario_de_negocio.md](./cenario_de_negocio.md) — resumo do contexto econômico e funcional do produto.
- [TG3_levantamento_especificacao_requisitos.pdf](./TG3_levantamento_especificacao_requisitos.pdf) — levantamento e especificação de requisitos.
- [TG4_modelos_interacao_grasp.pdf](./TG4_modelos_interacao_grasp.pdf) — modelos de interação e abordagens de projeto.
- [TG6_site de streaming.pdf](./TG6_site%20de%20streaming.pdf) — documento complementar com a consolidação do projeto.

### Modelagem e diagramas

- [modelo_de_dominio_descricao.md](./modelo_de_dominio_descricao.md) — descrição das classes conceituais e das associações do domínio.
- [modelo_de_dominio_diagrama.puml](./modelo_de_dominio_diagrama.puml) — diagrama UML do modelo de domínio.
- [diagrama_caso_uso_streaming.puml](./diagrama_caso_uso_streaming.puml) — representação dos casos de uso do sistema.
- [diagrama_pacotes_streaming.puml](./diagrama_pacotes_streaming.puml) — diagrama de pacotes em arquitetura em camadas.
- [TG5_diagrama_componentes_chamyflix.puml](./TG5_diagrama_componentes_chamyflix.puml) — diagrama de componentes do sistema.
- [TG5_conexoes_entre_componentes.pdf](./TG5_conexoes_entre_componentes.pdf) — material visual complementar sobre conexões entre componentes.

### Prototipação

- [prototipacaoSite.md](./prototipacaoSite.md) — referência para o protótipo em Figma.

## Navegação rápida do wiki

A documentação foi organizada para permitir a leitura em ordem crescente de aprofundamento:

1. Entender a ideia central do produto.
2. Revisar o cenário de negócio e os casos de uso.
3. Entender os requisitos e a modelagem operacional.
4. Visualizar a estrutura do sistema em diagramas.
5. Consultar a prototipação e a referência visual.

## Estado do repositório

Este repositório está focado em documentação, análise e especificação do projeto. A maioria dos artefatos é textual ou gráfica, com apoio de diagramas UML, materiais em PDF e documentos de descrição conceitual.

## Conclusão

O ChamyFlix é uma proposta de plataforma de streaming que combina personalização, recomendações inteligentes, organização de conteúdo por gênero e experiências consistentes entre dispositivos. A documentação presente neste repositório oferece uma base sólida para compreender a visão do produto, as regras de negócio e a estrutura conceitual do sistema.

Esta página funciona como ponto central de navegação do projeto, servindo como wiki inicial para consulta dos diferentes documentos e representações produzidas.
