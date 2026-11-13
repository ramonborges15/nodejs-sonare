# nodejs-sonare
Gestão de repertório, preparação de cultos e organização da equipe de louvor.

## **1. Visão do produto**

O Sonare será uma aplicação web para centralizar a preparação dos cultos da igreja, facilitando a organização dos repertórios e a distribuição dos vocalistas.

**Proposta de valor:**

> Organize os cultos, prepare os repertórios e coordene a equipe de louvor em um único lugar.

O produto terá como ponto central a agenda de cultos. A partir dela, o administrador poderá preparar cada celebração e os integrantes poderão consultar as informações.

## **2. Escopo funcional do MVP**

Organizei os requisitos em seis módulos.

**01. Agenda de cultos**

- Visualização em calendário.
- Cadastro manual de cultos extraordinários.
- Programação recorrente de cultos.
- Edição e cancelamento de cultos.
- Identificação do tipo de culto.

**02. Catálogo de músicas**

Cadastro com os seguintes campos:

- Título.
- Tipo.
- Tonalidade.
- Ritmo.
- Letra.
- Link do YouTube.

Também deverá permitir pesquisar, editar e consultar músicas.

**03. Repertório dos cultos**

- Seleção manual de músicas do catálogo.
- Organização por momentos do culto.
- Reordenação manual das músicas.
- Visualização da sequência completa.
- Acesso à letra, tonalidade, ritmo e vídeo de cada música.

**04. Gestão de vocalistas**

- Cadastro de integrantes.
- Identificação de vocalistas ativos.
- Seleção manual para cada culto.
- Histórico de participações.
- Consulta das escalas futuras.

**05. Escalas automáticas**

- Registro manual das disponibilidades recebidas pelo WhatsApp.
- Distribuição automática dos vocalistas.
- Equilíbrio na quantidade de participações.
- Prevenção de escalas consecutivas.
- Possibilidade de ajustes manuais.

**06. Usuários e permissões**

- Administrador: gerenciamento completo.
- Integrantes: acesso somente para consulta.
- Autenticação de usuários.

## **3. Regras de negócio iniciais**

Considerando também as regras de organização de louvor que você já havia estabelecido anteriormente, sugiro começar com estas definições:

| Contexto        | Regra                                                        |
| --------------- | ------------------------------------------------------------ |
| Cultos          | Programação semanal recorrente, com exceções                 |
| Vocalistas      | Dois vocalistas por culto                                    |
| Domingos        | Evitar repetir a mesma pessoa em domingos consecutivos       |
| Quartas-feiras  | Considerar a escala de domingo, com possibilidade de ajustes |
| Disponibilidade | Administrador registra as respostas das enquetes do WhatsApp |
| Escala          | Distribuição equilibrada entre integrantes                   |
| Repertório      | Seleção manual e ordenação por momentos                      |

As categorias musicais iniciais podem contemplar Cantor Cristão, Comunhão, Louvor e Adoração e Reflexão e Arrependimento.&#x20;

## **4. Roadmap de desenvolvimento**

Eu não desenvolveria todos os módulos simultaneamente. A melhor estratégia é construir o fluxo principal primeiro e adicionar as funcionalidades progressivamente.

## **Fase 1 — Fundação**

Prioridade alta

**Objetivo:** estabelecer a estrutura da aplicação.

- Configuração inicial do projeto.
- Autenticação.
- Cadastro de usuários.
- Cadastro de vocalistas.
- Controle de permissões.
- Estrutura visual e navegação.

## **Fase 2 — Catálogo musical**

**Objetivo:** permitir o gerenciamento do repertório.

- Cadastro de músicas.
- Edição e exclusão.
- Cadastro de tonalidade e ritmo.
- Cadastro de letras.
- Integração com links do YouTube.
- Pesquisa e filtros por tipo.

## **Fase 3 — Preparação dos cultos**

Funcionalidade central

**Objetivo:** tornar possível preparar um culto do início ao fim.

- Agenda mensal.
- Programação recorrente.
- Cadastro de cultos extraordinários.
- Cadastro dos momentos do culto.
- Seleção manual de músicas.
- Ordenação do repertório.
- Visualização do repertório completo.

## **Fase 4 — Gestão de escalas**

**Objetivo:** organizar a participação dos vocalistas.

- Registro de disponibilidade.
- Escala manual.
- Histórico de participações.
- Algoritmo de distribuição automática.
- Regras de equilíbrio.
- Prevenção de escalas consecutivas.
- Edição manual das sugestões.

## **Fase 5 — Consulta e publicação**

**Objetivo:** disponibilizar as informações para toda a equipe.

- Visão de consulta dos próximos cultos.
- Consulta dos repertórios.
- Consulta das letras e tonalidades.
- Consulta das escalas.
- Ajustes de experiência para dispositivos móveis.
- Testes e publicação da aplicação.

## **5. O que não entraria no primeiro MVP**

Para evitar que o projeto cresça desnecessariamente, deixaria algumas funcionalidades para versões futuras:

- Integração direta com WhatsApp.
- Confirmação de disponibilidade pelos próprios vocalistas.
- Notificações automáticas.
- Gestão de instrumentistas.
- Sugestão automática de músicas.
- Modelos prontos de repertório.
- Relatórios avançados.
- Aplicativo nativo para Android e iOS.

## **6. Critério de conclusão do MVP**

O Sonare estará pronto para seu primeiro uso quando for possível realizar este fluxo sem depender de planilhas ou listas paralelas:

## **Fluxo principal do Sonare**

1. **Cadastrar músicas**

   O administrador mantém o catálogo atualizado.
2. **Programar os cultos**

   O sistema disponibiliza os cultos recorrentes e extraordinários.
3. **Preparar o repertório**

   O administrador seleciona as músicas e organiza os momentos.
4. **Montar a escala**

   O administrador registra disponibilidades e gera ou ajusta a escala.
5. **Disponibilizar para a equipe**

   Os integrantes consultam as informações do culto.

## **7. Minha recomendação técnica**

Considerando que você já trabalha com NestJS, TypeScript e Angular, eu aproveitaria esse conhecimento:

| Camada         | Tecnologia sugerida              |
| -------------- | -------------------------------- |
| Frontend       | Angular                          |
| Backend        | NestJS                           |
| Banco de dados | PostgreSQL                       |
| ORM            | TypeORM                          |
| Autenticação   | JWT                              |
| Hospedagem     | AWS ou outra plataforma de nuvem |

Arquiteturalmente, começaria com um monólito modular, utilizando Ports & Adapters de maneira gradual. Não vejo necessidade de microserviços ou CQRS neste momento.

## **8. Próximos passos**

Eu seguiria esta ordem:

1. Consolidar o documento de requisitos funcionais.
2. Definir as entidades e relacionamentos do banco.
3. Criar os casos de uso e regras de negócio.
4. Desenhar os wireframes das principais telas.
5. Construir o backlog de desenvolvimento.

**Uma observação importante:** a distribuição automática de vocalistas é a funcionalidade com maior complexidade de regras de negócio. Eu desenvolveria primeiro a escala manual e depois o algoritmo automático, aproveitando a mesma estrutura de dados.

Minha sugestão é tratar este roadmap como a primeira versão do escopo do Sonare. Assim, podemos evoluir o projeto sem perder o controle sobre o que realmente pertence ao MVP.

Se quiser, posso acompanhar semanalmente a evolução do Sonare e ajudar a revisar as prioridades do roadmap toda segunda-feira.

🎵Revisar Sonare toda segunda-feiraToque para configurar
