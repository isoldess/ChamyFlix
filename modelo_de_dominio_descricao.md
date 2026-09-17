# Modelo de domínio — Site de streaming personalizado

## Casos de uso considerados para a modelagem

A modelagem partiu da leitura dos seis casos de uso já definidos para o sistema, buscando os substantivos e conceitos que se repetem de forma relevante em suas descrições:

- UC01 — Visualizar catálogo personalizado:** o usuário acessa a home e vê o catálogo organizado por gênero, com base em seu histórico, em qualquer dispositivo (celular, PC ou TV) com consistência entre telas.
- UC02 — Receber descoberta semanal:** o sistema apresenta conteúdos inéditos, organizados por gênero, alinhados ao perfil do usuário.
- UC03 — Pesquisar com sugestões:** o usuário busca conteúdo e recebe sugestões de termos relacionados aos gêneros mais assistidos.
- UC04 — Avaliar conteúdo assistido:** o usuário avalia um conteúdo que já assistiu, retroalimentando o algoritmo de recomendação.
- UC05 — Gerenciar catálogo:** o administrador cadastra e atualiza os títulos disponíveis na plataforma.
- UC06 — Notificar lançamentos:** o usuário recebe um push no dispositivo, no dia e horário em que costuma assistir.

## Identificação das classes conceituais

A partir desses casos de uso, foram extraídos os seguintes conceitos como classes do domínio:

- Usuário — quem realiza as ações em UC01 a UC04; atributos `nome` e `email` bastam para identificar o conceito no domínio, sem entrar em dados de autenticação (isso seria implementação, não domínio).
- SessãoDeVisualização — o evento de "acessar/assistir" descrito em UC01; guarda `data` e `hora`, permitindo depois relacionar histórico, dispositivo usado e avaliação.
- ItemAssistido — cada conteúdo específico visto dentro de uma sessão (necessário para UC01, que depende do histórico item a item, e para UC04, que avalia um conteúdo específico); atributo `progresso` guarda o quanto foi assistido.
- Conteúdo — o título em si (filme, série, documentário), citado em praticamente todos os casos de uso; atributos `título` e `duração`.
- Gênero — conceito central em UC01, UC02 e UC03, usado tanto para organizar a home quanto para sugerir termos de busca; virou classe própria (e não apenas um atributo de texto) porque é reaproveitado por várias partes do sistema.
- Catálogo — de onde os conteúdos vêm e onde o administrador atua em UC05; atributo `nome`.
- Dispositivo — necessário para expressar a consistência entre telas exigida em UC01 e o hábito de uso citado em UC06 (dias/horários costumeiros); atributo `tipo` (celular, PC, TV).
- Avaliação — o resultado de UC04; atributos `nota` e `comentário`.

## Associações do diagrama e sua origem nos casos de uso

- Usuário — Realiza — SessãoDeVisualização (1 / 0..*):** todo acesso à plataforma (UC01) parte de um usuário.
- SessãoDeVisualização — Contido-em — ItemAssistido (1 / 1..*):** uma sessão pode reunir um ou mais conteúdos vistos, necessário para reconstruir o histórico usado em UC01.
- ItemAssistido — Registra-visualização-de — Conteúdo (0..1 / 1):** liga o registro de visualização ao título real do catálogo.
- Conteúdo — Classificado-como — Gênero (\* / 1..\*):** suporta a organização por gênero de UC01, UC02 e UC03.
- Conteúdo — Armazenado-em — Catálogo (\* / 1):** reflete a gestão de títulos feita pelo administrador em UC05.
- Catálogo — Disponível-em — Dispositivo (1 / 1..\*):** garante que o mesmo catálogo esteja acessível em celular, PC e TV, como pede UC01.
- SessãoDeVisualização — Assistida-em — Dispositivo (\* / 1):** cada sessão ocorre em um dispositivo específico, base para o hábito de horário usado em UC06.
- **SessãoDeVisualização — Avaliada-por — Avaliação (1 / 0..1):** uma sessão pode gerar, opcionalmente, uma avaliação (UC04).

## O que foi deixado de fora

Conforme o escopo de um modelo de domínio, o diagrama não contém:
- Artefatos de software (nenhuma classe representa tela, banco de dados ou API);
- Responsabilidades/métodos (as classes têm apenas atributos, sem operações);
- Projeção de arquitetura (sem camadas, controladores ou padrões de projeto de software).
