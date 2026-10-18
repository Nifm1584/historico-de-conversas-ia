# Análise do plugin PWA

## Objetivo desta pasta

Esta pasta preserva o histórico da conversa **“Análise do plugin PWA”** e orienta qualquer agente de IA a retomar o trabalho com base em evidências, sem fazer o usuário repetir todo o contexto.

## Leia nesta ordem

1. Leia este README.
2. Leia todo o arquivo [historico.md](./historico.md), do início ao fim.
3. Leia [estado-atual.md](./estado-atual.md) para encontrar rapidamente as decisões mais recentes e o próximo passo conhecido.
4. Copie e use as orientações de [INSTRUCAO-PARA-NOVO-AGENTE.md](./INSTRUCAO-PARA-NOVO-AGENTE.md) ao iniciar uma sessão com um agente novo.
5. Abra o repositório do projeto TREG PWA: [Nifm1584/plugin-v1-pwa](https://github.com/Nifm1584/plugin-v1-pwa). Confira o código, os relatórios, testes, branches e commits relevantes. Não trate o histórico como substituto do código atual.

## Regras para o agente

- Use o histórico inteiro e priorize decisões/correções mais recentes.
- Diferencie sugestão, plano, implementação, teste automatizado, validação manual e validação no ambiente real.
- Consulte a documentação oficial atual do Hermes e da API antes de recomendar ou implementar funcionalidades. Não invente endpoints, campos ou recursos.
- Preserve o plugin original hermes-pwa e o núcleo do Hermes; o projeto independente é treg-pwa.
- Siga o fluxo por fases: inspecionar e reportar primeiro; aguardar revisão antes de implementar.
- Não instale na VPS, reinicie serviços, faça merge na main nem publique alterações sem autorização explícita.
- Não altere nem substitua o histórico original. Registre novas decisões em arquivos separados.
- Se histórico, relato do usuário e código divergirem, descreva a divergência e peça validação quando necessário.

## Repositórios e referências

- **Projeto:** https://github.com/Nifm1584/plugin-v1-pwa
- **Relatórios:** https://github.com/Nifm1584/plugin-v1-pwa/tree/main/report
- **Histórico desta conversa:** https://github.com/Nifm1584/historico-de-conversas-ia/blob/main/conversas/ChatGPT/An%C3%A1lise%20do%20plugin%20PWA/historico.md

## Estrutura obrigatória desta pasta

- README.md — explica a finalidade e a ordem de leitura.
- historico.md — histórico integral e cronológico da conversa.
- estado-atual.md — estado conhecido, decisões vigentes e próximo passo.
- INSTRUCAO-PARA-NOVO-AGENTE.md — prompt pronto para copiar e colar em um agente novo.

Use a mesma estrutura em **todas as pastas de histórico de projetos**. Para criar novas pastas de forma consistente, copie o modelo em [MODELO-PARA-NOVAS-CONVERSAS](https://github.com/Nifm1584/historico-de-conversas-ia/tree/main/MODELO-PARA-NOVAS-CONVERSAS) e substitua todos os links e textos específicos pelo projeto correspondente.

**Importante:** o histórico explica o caminho percorrido; o repositório do projeto é a fonte para confirmar o estado técnico atual.