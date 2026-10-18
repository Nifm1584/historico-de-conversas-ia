# Estado atual — TREG PWA

> Este documento é um ponto de partida rápido. Confirme sempre o estado real no repositório e nos relatórios antes de agir.

## Projeto principal

- Repositório: https://github.com/Nifm1584/plugin-v1-pwa
- Relatórios: https://github.com/Nifm1584/plugin-v1-pwa/tree/main/report
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

## Último estado conhecido no histórico

- A correção do QR Code foi desenvolvida na branch fix/treg-pwa-c7-qrcode-fix.
- O histórico registra o commit 6218f0fd25a2047b5caba09cf854af74058db03d como a versão C7 validada por testes automatizados e depois instalada pelo Hermes para validação no celular.
- O histórico relata que o usuário conseguiu parear o celular e usar áudio/transcrição. Confira o relatório e o estado atual do repositório antes de assumir que esse commit ainda é o HEAD ou que todos os testes estão concluídos.
- A main não foi mesclada com a branch C7 segundo o histórico.
- A etapa seguinte proposta é **Fase 3 — checklist funcional e roadmap**: revisar o código atual, relatórios anteriores e documentação oficial do Hermes/API, classificar recursos por evidência e criar report/17-fase-3-checklist-funcional-e-roadmap.md. O prompt foi preparado e o usuário disse que poderia prosseguir, mas este histórico não comprova que a execução da Fase 3 já ocorreu.

## Próxima ação recomendada

1. Inspecione o repositório e identifique o branch/commit atual, relatórios existentes e estado da CI.
2. Consulte a documentação oficial atual do Hermes/API e os relatórios existentes (principalmente inventário, auditoria mobile, integração API, segurança, testes, plano de evolução, evidências e relatório C7).
3. Execute somente a análise e produza o checklist/roadmap da Fase 3; não altere o código nem a VPS nesta etapa.
4. Publique o relatório numa branch própria apenas conforme o fluxo aprovado, informando commit, links, testes e pendências. Não faça merge na main.
5. Apresente o resultado para o usuário revisar antes de iniciar implementação.

## Regra para resolver divergências

O histórico é cronológico e contém hipóteses antigas que foram corrigidas depois. Use as mensagens mais recentes para entender as decisões finais, mas confirme o estado técnico atual pelo código, documentação e evidências. Nunca transforme uma afirmação de conversa em validação técnica sem comprovação.