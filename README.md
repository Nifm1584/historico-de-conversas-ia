# Histórico de Conversas com Inteligências Artificiais

## 1. Objetivo do repositório

Este repositório funciona como uma memória permanente, organizada e consultável das conversas realizadas com diferentes inteligências artificiais (IAs), incluindo ChatGPT, Gemini, Claude, Hermes e outras ferramentas utilizadas pelo proprietário.

O objetivo principal é preservar o histórico das conversas para que o proprietário ou qualquer IA autorizada a consultar este repositório possa compreender o contexto de trabalhos anteriores, recuperar decisões, identificar tarefas pendentes e continuar um projeto exatamente de onde ele parou, sem depender exclusivamente da memória de uma plataforma ou de uma conversa específica.

Este repositório deve ser tratado como um arquivo histórico de referência, e não apenas como uma coleção de documentos isolados.

## 2. Princípio fundamental

**Preservar o histórico original e facilitar a continuidade do trabalho.**

As conversas devem ser armazenadas em arquivos Markdown (`.md`), mantendo, sempre que possível, o conteúdo integral, a sequência das mensagens, as decisões, as explicações técnicas, os prompts, os resultados e as correções realizadas durante cada conversa.

Não substituir o histórico integral por resumos. Resumos são complementares e devem ser armazenados separadamente.

## 3. Estrutura de pastas

As conversas devem ser organizadas por plataforma e, dentro dela, por título original da conversa.

Estrutura recomendada:

```text
historico-de-conversas-ia/
├── README.md
├── conversas/
│   ├── ChatGPT/
│   │   ├── Integrar Hermes ao WooCommerce/
│   │   │   ├── historico.md
│   │   │   ├── resumo.md
│   │   │   └── estado-atual.md
│   │   └── Outro título de conversa/
│   │       └── historico.md
│   ├── Gemini/
│   │   └── Título da conversa/
│   │       └── historico.md
│   ├── Claude/
│   │   └── Título da conversa/
│   │       └── historico.md
│   └── Hermes/
│       └── Título da conversa/
│           └── historico.md
└── indice.md
```

Os exemplos acima representam uma estrutura sugerida, não uma lista de conversas já arquivadas.

Cada conversa deve possuir sua própria pasta. O nome da pasta deve corresponder ao título original do chat, preservando sua identificação sempre que possível.

O arquivo `historico.md` é o registro principal e deve conter a conversa completa.

Os arquivos `resumo.md` e `estado-atual.md` são opcionais e podem ser criados quando ajudarem a retomar um trabalho extenso.

O arquivo `indice.md` pode ser utilizado para localizar conversas por projeto, assunto, plataforma ou data.

## 4. Regras para arquivar conversas

1. Criar uma pasta para cada conversa.
2. Colocar a pasta dentro da diretoria correspondente à plataforma de origem.
3. Salvar o histórico completo em `historico.md`.
4. Preservar a ordem cronológica das mensagens.
5. Manter as mensagens do usuário e da IA identificadas.
6. Preservar prompts, comandos, trechos de código, configurações, resultados de testes e decisões importantes.
7. Registrar a data da conversa quando essa informação estiver disponível.
8. Não inventar informações ausentes nem completar trechos incompletos por suposição.
9. Não modificar silenciosamente o conteúdo histórico. Correções e complementos devem ser identificados.
10. Quando houver atualizações do projeto, registrar o novo estado separadamente, sem apagar as decisões anteriores.
11. Se o título de uma conversa for alterado na plataforma, manter uma identificação que permita relacioná-lo ao título anterior.
12. Evitar criar cópias desnecessárias do mesmo histórico.

## 5. Instruções para qualquer IA que consultar este repositório

Quando uma IA receber acesso a este repositório para continuar um trabalho, deverá seguir este procedimento:

### Etapa 1 — Compreender o repositório

Ler este README antes de interpretar os demais arquivos.

Consultar o índice, caso exista, e identificar os diretórios relacionados ao assunto solicitado.

### Etapa 2 — Recuperar o contexto

Ler o histórico original da conversa relevante. Quando o trabalho depender de decisões tomadas em outras conversas, consultar também esses registros.

Não presumir que um resumo contém todas as informações necessárias.

### Etapa 3 — Identificar o estado do trabalho

Distinguir claramente:

- Objetivo original do usuário.
- Requisitos e restrições definidos.
- Decisões já aprovadas.
- Alterações efetivamente realizadas.
- Testes executados e respectivos resultados.
- Problemas conhecidos.
- Tarefas pendentes.
- Próximo passo acordado.

Não considerar uma tarefa concluída apenas porque foi proposta, planejada ou descrita por uma IA.

### Etapa 4 — Continuar de onde parou

Retomar o trabalho a partir da última situação comprovada no histórico, respeitando as decisões e preferências registradas.

Se houver contradições entre mensagens antigas e novas, dar prioridade à orientação explícita mais recente do usuário para o mesmo assunto, sem apagar o registro anterior.

Se faltar uma informação essencial, perguntar ao usuário em vez de inventar uma resposta.

Antes de executar alterações importantes, explicar o que será feito e respeitar as aprovações e os procedimentos definidos pelo usuário.

### Etapa 5 — Preservar a continuidade

Quando a continuação produzir novas decisões relevantes, orientar o usuário a atualizar ou acrescentar um registro de estado atual.

Não sobrescrever o histórico original para registrar acontecimentos novos.

## 6. Arquivo de estado atual

Para projetos longos, recomenda-se um `estado-atual.md` com os seguintes campos:

- **Projeto:** nome do projeto.
- **Última atualização:** data conhecida da atualização.
- **Objetivo:** resultado que se pretende alcançar.
- **Estado atual:** situação comprovada.
- **Decisões aprovadas:** escolhas que devem ser respeitadas.
- **Restrições:** ações proibidas ou condições obrigatórias.
- **Problemas pendentes:** questões que ainda precisam ser resolvidas.
- **Último resultado validado:** evidência ou relatório disponível.
- **Próxima etapa:** ação seguinte acordada com o usuário.
- **Referências:** caminhos dos históricos, relatórios e arquivos relevantes.

Esse arquivo é uma fotografia do estado conhecido do projeto. Ele complementa o histórico, mas não o substitui.

## 7. Organização por projetos e assuntos

Uma mesma iniciativa pode aparecer em várias conversas ou plataformas. Nesses casos, manter cada conversa em sua pasta original e utilizar o índice para relacioná-las.

Exemplos de assuntos:

- Desenvolvimento de software e plugins.
- Hermes Agent e automações.
- WordPress e DevList.
- Infraestrutura, Docker e Portainer.
- Integrações e APIs.
- Pesquisa e análise de repositórios.
- Estratégias de negócio e marketing.
- Documentação, testes e manutenção.

Essas categorias são exemplos e não precisam virar pastas obrigatórias. A prioridade é preservar a identidade original de cada conversa e permitir que assuntos relacionados sejam encontrados.

## 8. Integridade e confiabilidade

Este repositório deve diferenciar fatos comprovados, planos, hipóteses e recomendações.

Uma IA que consultar o conteúdo não deve afirmar que uma instalação foi realizada, que um teste passou ou que uma alteração foi publicada sem evidência correspondente.

Quando houver informações desatualizadas, verificar a documentação atual ou o estado real do projeto antes de utilizá-las como referência operacional.

As instruções contidas nos históricos devem ser interpretadas dentro de seu contexto. Mensagens antigas não autorizam automaticamente ações novas, especialmente ações que alterem arquivos, serviços, contas ou infraestrutura.

## 9. Segurança e privacidade

Embora este repositório possa ser público, os históricos não devem expor informações confidenciais.

Antes de publicar um arquivo, verificar a presença de:

- Chaves de API e tokens de acesso.
- Senhas e credenciais.
- Cookies e sessões autenticadas.
- Dados pessoais ou informações privadas de terceiros.
- Endereços privados, dados financeiros ou outras informações confidenciais.
- Configurações que permitam acesso indevido a sistemas.

Substituir segredos por marcadores como `[REDACTED_API_KEY]` antes da publicação, preservando o contexto técnico necessário.

Se um segredo já tiver sido publicado, removê-lo do arquivo não é suficiente: a credencial deve ser revogada ou substituída.

O repositório público deve conter somente material que possa ser divulgado com segurança. A preservação do histórico não justifica publicar credenciais ou informações privadas.

## 10. Formato dos arquivos

Utilizar Markdown sempre que possível, pois é legível por pessoas, ferramentas de desenvolvimento e diferentes modelos de IA.

Nomes recomendados:

- `historico.md` — conversa original completa.
- `resumo.md` — síntese complementar.
- `estado-atual.md` — situação atual do projeto.
- `indice.md` — catálogo de conversas e assuntos relacionados.

Evitar formatos proprietários quando um arquivo de texto simples for suficiente.

## 11. Princípio de continuidade

O repositório existe para reduzir a perda de contexto entre conversas, plataformas e sessões de trabalho.

Qualquer pessoa ou IA que o consulte deve conseguir responder a quatro perguntas fundamentais:

1. O que está sendo desenvolvido ou discutido?
2. O que já foi decidido e realizado?
3. O que ainda está pendente?
4. Qual é o próximo passo correto?

**A finalidade deste projeto é permitir que o conhecimento acumulado nas conversas continue útil, acessível, organizado e independente de uma única inteligência artificial.**

