# Instrução padrão para retomar um projeto com um agente de IA

Copie e cole esta instrução ao iniciar uma nova sessão com qualquer agente.

Leia integralmente os arquivos desta pasta, nesta ordem:
1. README.md
2. `historico.md` — leia do início ao fim, não apenas o resumo ou as mensagens mais recentes.
3. Todos os arquivos `sessoes/*.md`, ordenados pela data no nome do arquivo (do mais antigo ao mais recente); leia cada arquivo completo. Se a pasta `sessoes/` não existir ou estiver vazia, registre isso e continue.
4. `estado-atual.md`, se existir.

Ao iniciar, informe os nomes dos arquivos de sessão encontrados e confirme quais foram lidos integralmente. Não presuma que o arquivo mais recente substitui os anteriores.

Depois, abra o repositório do projeto indicado abaixo e confira o estado real do código, documentação, relatórios, branches, commits e testes relevantes. O histórico explica como chegamos aqui; o repositório atual é a fonte para confirmar o estado técnico.

## Referências deste projeto

- Repositório de histórico: https://github.com/Nifm1584/historico-de-conversas-ia
- Pasta deste histórico: https://github.com/Nifm1584/historico-de-conversas-ia/tree/main/conversas/ChatGPT/An%C3%A1lise%20do%20plugin%20PWA
- Repositório do projeto: https://github.com/Nifm1584/plugin-v1-pwa
- Relatórios do projeto: https://github.com/Nifm1584/plugin-v1-pwa/tree/main/report

## O que você deve fazer

Reconstrua o objetivo do projeto, decisões aprovadas, preferências e restrições do usuário, o que foi realmente executado, os testes e validações feitos, problemas pendentes e próximo passo acordado. Compare as mensagens mais recentes com as antigas e identifique decisões que foram corrigidas ou substituídas.

Diferencie claramente:
- ideia ou sugestão;
- plano ainda não executado;
- alteração implementada;
- teste automatizado executado;
- validação manual feita pelo usuário;
- validação no ambiente real.

Não declare concluído algo sem evidência. Se o relato do usuário divergir de um relatório técnico, preserve os dois fatos e explique o que ainda precisa ser confirmado.

Antes de propor ou alterar integração, API, biblioteca ou serviço externo, consulte a documentação oficial atual e verifique os contratos existentes. Não invente endpoints, campos, eventos ou capacidades.

Respeite as restrições e o fluxo de trabalho registrados no histórico. Quando o fluxo exigir, comece apenas com inspeção e relatório; não modifique arquivos, não publique, não faça merge, não instale nem altere ambientes de produção sem autorização explícita.

Ao final da análise inicial, apresente:
1. resumo do objetivo e arquitetura;
2. decisões e restrições vigentes;
3. estado real do repositório, branch e commit analisados;
4. o que está implementado e o que foi validado, com evidências;
5. divergências, riscos e pendências;
6. próximo passo recomendado, indicando se precisa de aprovação.

Se faltar informação essencial, pergunte ao usuário. Não peça que ele repita informações que já estão documentadas. Preserve o histórico original e registre novas decisões em arquivos separados quando isso fizer parte do fluxo aprovado.

## Regra obrigatória para todo prompt de tarefa e encerramento

Sempre que você preparar um prompt para executar a próxima tarefa deste projeto — seja para OpenCode, OpenCloud, outro agente ou ferramenta — inclua **no final do prompt** uma seção chamada “ENCERRAMENTO OBRIGATÓRIO — PRESERVAR O PONTO DE RETOMADA”. Essa seção deve instruir o agente a, antes de encerrar:

1. Informar o que foi feito e o que não foi feito, sem declarar sucesso sem evidência.
2. Listar arquivos criados, alterados ou removidos e resumir cada mudança.
3. Informar testes executados, resultados e evidências; separar testes automatizados, validações manuais e validações no ambiente real.
4. Registrar repositório, branch, commit inicial e commit final (quando aplicável); dizer explicitamente se não houve commit, publicação, instalação ou alteração de ambiente.
5. Atualizar `estado-atual.md` com o estado confirmado, decisões vigentes, pendências, divergências e próximo passo acordado; preservar `historico.md` integral e cronológico, sem reescrevê-lo.
6. Criar/atualizar um relatório de fase em `report/` no repositório do projeto quando isso fizer parte do fluxo autorizado.
7. Entregar um bloco final “PONTO EXATO DE RETOMADA” contendo: fase/tarefa concluída; estado real; evidências; o que falta; próximo passo único recomendado; aprovação necessária; e o prompt/ação que deve vir a seguir.
8. Se o agente não tiver acesso ao repositório de histórico, não puder editar os arquivos ou não tiver autorização para publicar, deve fornecer o conteúdo atualizado ou o bloco de checkpoint na resposta e declarar claramente que não o gravou no GitHub. Nunca alegar que atualizou um arquivo sem confirmar.

O prompt deve manter as restrições de escopo já aprovadas: não tocar em partes validadas sem necessidade, não executar fases futuras por conta própria e não publicar, fazer merge, instalar ou alterar produção sem autorização explícita. O checkpoint registra o estado; não concede autorização para a próxima fase.

Ao iniciar uma nova sessão, leia o `estado-atual.md`, compare-o com o histórico e confirme o estado real do repositório antes de continuar. Se houver conflito, não escolha silenciosamente: documente e peça esclarecimento quando necessário.

## Para reutilizar esta instrução em outro projeto

Ao copiar esta estrutura para outra pasta de histórico, atualize obrigatoriamente os links do repositório do projeto, da pasta do histórico e dos relatórios para apontarem para o projeto correspondente. Não deixe links específicos do TREG PWA em pastas de outros projetos.

## Protocolo de arquivamento de sessões

Cada nova sessão/conversa deve ser preservada em um arquivo próprio dentro de `sessoes/`, com nome `AAAA-MM-DD-assunto-curto.md` (ex.: `2026-10-18-organizacao-do-historico.md`). Preserve os arquivos de sessões anteriores sem sobrescrevê-los. Não cole a conversa nova por cima de `historico.md` nem reconstrua o histórico inteiro a cada atualização. Quando disponível, arquive a transcrição completa da sessão; se só houver um resumo/checkpoint, identifique-o explicitamente como resumo, nunca como transcrição integral. Atualize `estado-atual.md` com o ponto de retomada confirmado e registre no README o protocolo. Se não conseguir criar/gravar o arquivo no GitHub, forneça o conteúdo pronto para o usuário salvar e diga que não foi publicado.
