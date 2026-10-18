# Estado atual — TREG PWA

> Este documento é um ponto de partida rápido. Confirme sempre o estado real no repositório e nos relatórios antes de agir.

## Projeto principal

- Repositório: https://github.com/Nifm1584/plugin-v1-pwa
- Relatórios do projeto: https://github.com/Nifm1584/plugin-v1-pwa/tree/main/report
- Relatório mais recente conhecido da Fase 3: https://github.com/Nifm1584/plugin-v1-pwa/blob/docs/fase-3-checklist-roadmap/report/17-fase-3-checklist-funcional-e-roadmap.md
- Projeto: plugin independente treg-pwa para o Hermes, separado do plugin original hermes-pwa.
- Objetivo geral: melhorar a experiência de mensageiro no celular, mantendo identidade independente e implementando somente recursos reais e compatíveis com a API/documentação oficial do Hermes.

## Decisões e restrições importantes

- Não modificar o núcleo do Hermes nem remover/alterar o plugin original hermes-pwa.
- Antes de planejar ou implementar uma função, consultar a documentação oficial atual do Hermes e os contratos da API relevantes. Não inventar endpoints, campos ou eventos.
- Interface desejada: experiência de mensageiro inspirada no WhatsApp, legibilidade mobile, avatares, menus e tema claro/escuro; mensagens e blocos de código devem permitir copiar o conteúdo.
- Não exibir estados como “concluído”, “respondido” ou “resolvido” sem evidência de dados/eventos reais do Hermes.
- O usuário confirmou que o acesso pelo celular funciona no navegador e que o Chrome pode oferecer “adicionar à tela inicial”; isso não significa que a interface atual tenha instalação automática própria. Não marcar como defeito sem nova decisão.
- O usuário informou que uma imagem enviada anteriormente foi visualizada/validada; respeite a confirmação mais recente no histórico. Diferencie imagem incorporada à mensagem de envio como arquivo/anexo se o teste específico não estiver claro.
- Fluxo de trabalho: uma fase por vez; inspecionar e reportar antes de alterar; aguardar revisão/aprovação; testes e relatório por fase; sem VPS, reinício, merge na main ou publicação sem autorização explícita.

## Último estado conhecido no GitHub

- Branches que foram verificadas: main em 07cacfeb7a5af3650a1bdf3335af2be3262806aa; fix/treg-pwa-c7-qrcode-fix em 6218f0fd25a2047b5caba09cf854af74058db03d; e docs/fase-3-checklist-roadmap em bafed16675cf6bc2268a98f79ddeb13be16a3b05.
- O relatório 17 da Fase 3 existe na branch docs/fase-3-checklist-roadmap: https://github.com/Nifm1584/plugin-v1-pwa/blob/docs/fase-3-checklist-roadmap/report/17-fase-3-checklist-funcional-e-roadmap.md
- O commit conhecido mais recente nessa branch é bafed16675cf6bc2268a98f79ddeb13be16a3b05, que corrigiu a redação do relatório 17.
- O relatório 17 declara que esta fase foi de análise e planejamento: não alterou código do plugin, não instalou na VPS, não reiniciou serviços, não tocou no hermes-pwa original e não fez merge na main.
- O relatório recomenda a ordem P0 (validar em dispositivos reais), P1 (legibilidade e estrutura da conversa), P2 (menus, avatares e tema manual), P3 (status semânticos apenas com contratos reais), P4 (mídia persistente/câmera) e P5 (escala/offline/notificações).
- O relatório 17 ainda diz que PWA instalada, upload real de imagem/arquivo, áudio/transcrição em dispositivos e vários comportamentos mobile precisam de teste. O histórico também contém relatos posteriores do usuário sobre testes reais. Compare as evidências e esclareça divergências; não ignore o relato do usuário nem marque como comprovado tecnicamente sem verificar.
- Não assuma que uma branch histórica continua sendo a versão instalada na VPS. Confirme o commit instalado com o usuário ou com evidência do ambiente antes de qualquer instrução de instalação.

## Próxima ação recomendada

1. Leia o relatório 17 completo e confira os arquivos e commits na branch docs/fase-3-checklist-roadmap.
2. Compare o checklist com o histórico completo, dando atenção especial às confirmações do usuário sobre QR/pareamento, áudio, imagem enviada e comportamento de instalação pelo navegador. Se houver divergência entre a experiência relatada e o relatório estático, registre-a e peça validação específica apenas quando necessária.
3. Apresente o relatório 17 ao usuário para revisão. Não inicie implementação automaticamente.
4. Após aprovação, comece somente a fase autorizada, em branch própria, com relatório, testes e evidências. Não faça merge na main nem alterações na VPS sem autorização explícita.

## Regra para resolver divergências

O histórico é cronológico e contém hipóteses antigas que foram corrigidas depois. Use as mensagens mais recentes para entender as decisões finais, mas confirme o estado técnico atual pelo código, documentação e evidências. Nunca transforme uma afirmação de conversa em validação técnica sem comprovação, nem descarte uma validação feita pelo usuário sem explicar a diferença entre o teste manual e o teste automatizado.

## Protocolo obrigatório de continuidade entre sessões

Todo prompt de tarefa futuro deve terminar com a seção **“ENCERRAMENTO OBRIGATÓRIO — PRESERVAR O PONTO DE RETOMADA”**. O agente que executar a tarefa deve registrar resultado real, arquivos alterados, testes e evidências, repositório/branch/commits, pendências, próximo passo único e aprovações necessárias. Deve atualizar este arquivo quando tiver acesso e autorização; manter `historico.md` intacto; e nunca afirmar que publicou uma atualização sem confirmar. Se não puder gravar no GitHub, deve devolver o checkpoint completo no relatório/resposta.

Esta regra é de continuidade documental e não autoriza mudanças no código, na VPS, na branch principal, nem publicação/merge. A próxima sessão deve comparar este estado com o histórico e com o repositório real antes de agir.

## Protocolo de histórico por sessões

- `historico.md` é o histórico original: preservar integralmente, sem substituir pelo acumulado de novas sessões.
- Novas sessões ficam em `sessoes/AAAA-MM-DD-assunto-curto.md`, um arquivo por sessão, sem sobrescrever arquivos anteriores.
- Na retomada, ler todos os arquivos de `sessoes/` em ordem cronológica, depois conferir `estado-atual.md` e validar o estado real do repositório.
- Distinguir transcrição completa de resumo/checkpoint. Não apresentar resumo como se fosse a conversa integral.

## Atualização documental — 2026-10-18

- Foi definido e documentado o arquivamento de cada nova sessão em um arquivo separado dentro de `sessoes/`, com nome `AAAA-MM-DD-assunto-curto.md`.
- Foi criado `sessoes/README.md` com as regras e `sessoes/2026-10-18-organizacao-do-historico-por-sessoes.md`, que é um resumo estruturado, não uma transcrição integral.
- As instruções de retomada e os arquivos do modelo foram revisados e publicados na branch principal do repositório de arquivo.
- O PR #1 foi integrado por squash merge à `main`: https://github.com/Nifm1584/historico-de-conversas-ia/pull/1
- Commit de merge confirmado na `main`: `3c304c8bb1ede58b2eff88793ca43698dda06789`.
- A sessão `sessoes/Correção documental — Fase 3 do TREG PWA.md` também foi enviada ao repositório; ela registra o material disponível sobre a correção documental da Fase 3. Não presumir que seja uma transcrição integral sem verificar seu conteúdo e sua classificação.
- `historico.md` original foi preservado. Nenhum código do TREG PWA foi alterado nesta manutenção documental, e nenhuma ação foi feita na VPS.
- **Estado atual do arquivo de memória:** a organização documental e as instruções de retomada já estão na `main`; não há merge documental pendente daquela branch.
- **Próxima retomada do projeto TREG PWA:** seguir o procedimento de leitura definido em `INSTRUCAO-PARA-NOVO-AGENTE.md`, ler o histórico original e todas as sessões em ordem cronológica, conferir `estado-atual.md` e verificar branches, commits e relatório 17 no repositório real do projeto antes de recomendar ou executar qualquer etapa.
- A publicação anterior no arquivo de memória não autoriza mudanças no código do TREG PWA, instalação ou alterações na VPS, nem novos merges/publicações. Continuam valendo as aprovações por fase.
