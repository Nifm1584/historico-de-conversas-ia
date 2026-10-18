# Análise do plugin PWA

## Objetivo desta pasta

Esta pasta preserva o histórico da conversa **“Análise do plugin PWA”** e orienta qualquer agente de IA a retomar o trabalho com base em evidências, sem fazer o usuário repetir todo o contexto.

## Leia nesta ordem

1. Leia este README.
2. Leia todo o arquivo [historico.md](./historico.md), do início ao fim. Ele contém a conversa cronológica e é a fonte principal para decisões, contexto e histórico.
3. Leia [estado-atual.md](./estado-atual.md) para encontrar rapidamente o projeto de código, as decisões mais recentes e o próximo passo conhecido.
4. Abra o repositório do projeto TREG PWA: **[Nifm1584/plugin-v1-pwa](https://github.com/Nifm1584/plugin-v1-pwa)**. Consulte o README, o código atual, os relatórios em report/, testes, branches e commits relevantes. Não trate o histórico da conversa como substituto do código atual.

## Instruções obrigatórias para o agente

- Use o histórico inteiro para compreender objetivo, decisões, preferências, restrições, testes, problemas e sequência de trabalho.
- Dê prioridade às decisões e correções mais recentes quando uma mensagem antiga contradisser uma atualização posterior. Registre a contradição se ela ainda não estiver resolvida; não esconda nem invente fatos.
- Diferencie **sugestão**, **planejamento**, **alteração implementada**, **teste executado** e **validação real na instalação**. Só declare algo concluído quando houver evidência no histórico, relatório, commit ou teste.
- Antes de recomendar ou implementar qualquer funcionalidade do Hermes, consulte a documentação oficial atualizada do Hermes e da API relevante. Não invente endpoints, campos, eventos ou recursos. Se não houver suporte comprovado, explique a limitação e proponha uma alternativa somente se for viável.
- Preserve o plugin original hermes-pwa e o núcleo do Hermes. O projeto independente é treg-pwa; confira o estado atual do repositório antes de usar nomes de branches ou SHAs citados no histórico.
- Siga o fluxo de trabalho por fases: primeiro inspecionar e reportar; apresentar o relatório para revisão; só implementar após aprovação. Não instale na VPS, reinicie serviços, faça merge na main ou publique alterações sem autorização explícita.
- Para cada fase aprovada, registre evidências, testes, limitações e pendências em um relatório dentro de report/, conforme o fluxo acordado.
- Se faltar informação essencial ou o histórico e o código atual divergirem, pergunte ao usuário em vez de adivinhar.
- Não altere nem substitua o histórico original. Registre atualizações em arquivos separados.

## Repositórios e referências

- **Projeto em desenvolvimento:** https://github.com/Nifm1584/plugin-v1-pwa
- **Relatórios do projeto:** https://github.com/Nifm1584/plugin-v1-pwa/tree/main/report
- **Histórico desta conversa:** https://github.com/Nifm1584/historico-de-conversas-ia/blob/main/conversas/ChatGPT/An%C3%A1lise%20do%20plugin%20PWA/historico.md

## Arquivos desta pasta

- README.md — instruções para qualquer agente que retomar o trabalho.
- historico.md — histórico cronológico completo da conversa.
- estado-atual.md — resumo operacional das decisões mais recentes e próximo passo conhecido.

**Importante:** o histórico é contexto histórico; o repositório do projeto é a fonte para confirmar o estado atual do código.