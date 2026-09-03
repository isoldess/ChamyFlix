# Modelo de caso de uso — Site de streaming personalizado

## 1. Casos de uso de negócio por ator

Ator: Usuário
- UC01 — Visualizar catálogo personalizado
- UC02 — Receber descoberta semanal
- UC03 — Pesquisar conteúdo com sugestões de termos
- UC04 — Avaliar conteúdo assistido

Ator: Administrador de conteúdo
- UC05 — Gerenciar catálogo (cadastrar e atualizar títulos)

Ator secundário (sistema): Serviço de notificação
- UC06 — Notificar lançamentos (recebe o gatilho do sistema e dispara o push ao usuário)

## 2. Descrição resumida dos casos de uso

| ID | Caso de uso | Ator principal | Descrição resumida |
|----|-------------|-----------------|----------------------|
| UC01 | Catálogo personalizado | Usuário | O usuário acessa a home e vê o catálogo organizado dinamicamente por gêneros, com base em seu histórico e preferências recentes. |
| UC02 | Descoberta semanal | Usuário | O sistema apresenta ao usuário uma seleção semanal de conteúdos inéditos alinhados ao seu perfil de gosto. |
| UC03 | Busca com sugestões | Usuário | Ao pesquisar, o usuário recebe sugestões de termos relacionados aos gêneros mais assistidos em seu perfil. |
| UC04 | Avaliar conteúdo | Usuário | O usuário avalia ou reage a um conteúdo assistido, retroalimentando o algoritmo de recomendação. |
| UC05 | Gerenciar catálogo | Administrador de conteúdo | O administrador cadastra, atualiza ou remove títulos do catálogo geral da plataforma. |
| UC06 | Notificar lançamentos | Usuário / Serviço de notificação | O usuário recebe um push no celular avisando sobre lançamentos, nos dias e horários em que costuma assistir. |

## 3. Caso de uso crítico completo — UC01 Catálogo personalizado

Este é o caso de uso mais importante do sistema pois concentra o valor central do produto: organizar a home de forma dinâmica para reduzir a sensação de excesso de opções que hoje afasta o usuário do formato longa-metragem.

Nome: Visualizar catálogo personalizado

Ator principal: Usuário

Descrição: Permite que o usuário, ao acessar a plataforma, visualize uma home organizada dinamicamente em fileiras de gêneros calculadas a partir de suas preferências recentes, em vez de um catálogo genérico e extenso.

Pré-condições:
- O usuário está autenticado na plataforma.
- Existe histórico mínimo de consumo ou preferências declaradas pelo usuário.

Fluxo principal:
1. O usuário acessa a plataforma (web, celular ou TV).
2. O sistema identifica o perfil do usuário autenticado.
3. O algoritmo calcula os gêneros e títulos mais relevantes com base no histórico recente.
4. O sistema monta a home com fileiras dinâmicas de gêneros (ex.: "Continue assistindo", "Baseado no que você viu", "Top para o seu perfil").
5. O usuário visualiza a home personalizada.
6. O usuário seleciona um título para mais detalhes ou para assistir.

Fluxos alternativos:
- 3a. Usuário novo, sem histórico suficiente: o sistema exibe uma home baseada em curadoria geral e nas preferências declaradas no cadastro, até acumular dados suficientes.
- 5a. Usuário troca de dispositivo (ex.: do celular para a TV): o sistema deve exibir a mesma organização e o mesmo histórico, mantendo consistência entre telas.

Fluxos de exceção:
- 3e. Falha no cálculo das recomendações: o sistema exibe uma home padrão (fallback) com os títulos mais populares gerais, registrando o erro para monitoramento.
- 2e. Falha de autenticação: o usuário é redirecionado à tela de login.

Pós-condições:
- A home personalizada é exibida com sucesso, ou o fallback é acionado sem interromper a navegação do usuário.
- As interações do usuário na home (cliques, tempo de permanência) são registradas para realimentar o algoritmo de recomendação.

Regras de negócio associadas:
- A recomendação deve ser transparente (o usuário entende por que um título foi sugerido).
- O histórico e as recomendações precisam ser idênticos entre celular, PC e TV.
- Os dados de preferência usados devem respeitar as regras de privacidade de dados da plataforma.

