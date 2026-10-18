# Instrução padrão para retomar um projeto com um agente de IA

Copie e cole este texto em uma sessão nova. Antes de usar, substitua todos os campos entre colchetes pelos links corretos do projeto correspondente.

Leia integralmente, nesta ordem:
1. [LINK_DA_PASTA_DO_HISTORICO]/README.md
2. [LINK_DA_PASTA_DO_HISTORICO]/historico.md — do início ao fim, não apenas o resumo.
3. [LINK_DA_PASTA_DO_HISTORICO]/estado-atual.md.

Depois, acesse o repositório de código [LINK_DO_REPOSITORIO_DO_PROJETO] e confira o README, o código, os relatórios, branches, commits e testes relevantes. O histórico explica como o projeto evoluiu; o código atual e as evidências confirmam o estado técnico.

## Referências deste projeto

- Repositório de histórico: [LINK_DO_REPOSITORIO_DE_HISTORICO]
- Pasta do histórico: [LINK_DA_PASTA_DO_HISTORICO]
- Repositório do projeto: [LINK_DO_REPOSITORIO_DO_PROJETO]
- Relatórios: [LINK_DA_PASTA_DE_RELATORIOS]

## Tarefa inicial

Reconstrua o objetivo, a arquitetura, as decisões aprovadas, as preferências e restrições do usuário, o que foi realmente executado, os testes e validações, as pendências e o próximo passo acordado. Compare as mensagens antigas com as mais recentes e identifique decisões corrigidas.

Diferencie claramente:
- ideia/sugestão;
- plano não executado;
- alteração implementada;
- teste automatizado;
- validação manual do usuário;
- validação no ambiente real.

Não declare algo concluído sem evidência. Se o relato do usuário divergir de um relatório, preserve ambos e explique o que falta confirmar. Consulte documentação oficial atual antes de propor ou alterar APIs e integrações. Não invente recursos.

Respeite o fluxo e as restrições do projeto. Se a instrução exigir inspeção e relatório primeiro, não implemente antes da revisão/aprovação. Não publique, faça merge, instale ou altere produção sem autorização explícita. Não peça que o usuário repita informações já documentadas.

Apresente a análise inicial com: objetivo/arquitetura; decisões vigentes; branch e commit examinados; implementações e validações com evidências; riscos e pendências; próximo passo recomendado e se exige aprovação. Se faltar informação essencial, pergunte antes de adivinhar.

Preserve o histórico original. Registre novas decisões em arquivos separados quando fizer parte do fluxo aprovado.

## Regra obrigatória para todo prompt de tarefa e encerramento

Sempre que criar um prompt para a próxima tarefa, inclua **no final do prompt** uma seção chamada “ENCERRAMENTO OBRIGATÓRIO — PRESERVAR O PONTO DE RETOMADA”. Ela deve exigir que o agente:

1. Registre o que foi feito e o que não foi feito, sem alegar sucesso sem evidência.
2. Liste arquivos criados/alterados/removidos e resuma as mudanças.
3. Registre testes e evidências, separando teste automatizado, validação manual e validação em ambiente real.
4. Informe repositório, branch, commit inicial/final quando aplicável, e declare se não houve commit, publicação, instalação ou mudança de ambiente.
5. Atualize `estado-atual.md` com decisões vigentes, estado confirmado, pendências, divergências e próximo passo; preserve `historico.md` sem reescrevê-lo.
6. Atualize/crie relatório da fase na pasta de relatórios do projeto quando previsto no fluxo aprovado.
7. Termine com “PONTO EXATO DE RETOMADA”: tarefa/fase, estado confirmado, evidências, pendências, próximo passo único, aprovação necessária e próxima ação/prompt.
8. Se não tiver acesso ou autorização para gravar no histórico, devolva o checkpoint completo e diga claramente que não atualizou o GitHub.

O registro não autoriza a próxima fase. Respeite limites de escopo e não publique, faça merge, instale nem altere produção sem autorização explícita. Em uma sessão nova, leia `estado-atual.md`, confira o histórico e valide branch/commit/estado real antes de continuar.

## Antes de usar

Substitua todos os campos [LINK_...] pelos endereços reais. Nunca deixe referências de outro projeto nesta instrução.