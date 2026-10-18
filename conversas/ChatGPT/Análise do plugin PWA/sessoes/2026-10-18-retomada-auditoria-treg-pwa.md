# Retomada e auditoria do estado do TREG PWA — 2026-10-18

> **Tipo de registro:** resumo estruturado/checkpoint desta sessão. **Não é uma transcrição integral.** O histórico original `historico.md` foi preservado sem alterações.

## O que foi consultado

Foram lidos integralmente o `README.md` desta pasta, o `historico.md` do início ao fim, todos os três Markdown presentes em `sessoes/` (`README.md`, `Correção documental — Fase 3 do TREG PWA.md` e `2026-10-18-organizacao-do-historico-por-sessoes.md`) e `estado-atual.md`. Os registros de sessão anteriores foram preservados.

O estado técnico foi conferido no GitHub de `Nifm1584/plugin-v1-pwa`, incluindo a lista de branches, o README de `main`, a branch C7, o relatório 16, a branch de documentação e o relatório 17. A documentação oficial atual do Hermes sobre integração programática/API também foi consultada.

## Estado real do repositório do projeto

Branches e HEAD observados no GitHub em 2026-10-18:

| Branch | HEAD |
|---|---|
| `main` | `07cacfeb7a5af3650a1bdf3335af2be3262806aa` |
| `fase-b-treg-pwa` | `a5485bd03174b02ee66ab6d338ff1b8b3cc5ed6f` |
| `fix/treg-pwa-c3-publicacao-segura` | `1e8c15988c815b73bab3a028e1ecc17edd58268f` |
| `fix/treg-pwa-c6-validacao-publicacao` | `a1bbe18553998284dcaf7ac99751624f6fd7e1e7` |
| `fix/treg-pwa-c7-qrcode-fix` | `6218f0fd25a2047b5caba09cf854af74058db03d` |
| `docs/fase-3-checklist-roadmap` | `4c066feb1191b37bf9d307e33b1249d9ca6627e7` |

- A CI do commit C7 `6218f0fd25a2047b5caba09cf854af74058db03d` foi confirmada como `success` na execução [39075301916](https://github.com/Nifm1584/plugin-v1-pwa/actions/runs/39075301916). A suíte registra 3/3 decodificações de QR com `jsQR`, teste de regressão que falha na versão antiga, verificações de sintaxe JS, compilação Python e 2 testes pytest.
- O relatório 16 está em [`fix/treg-pwa-c7-qrcode-fix`](https://github.com/Nifm1584/plugin-v1-pwa/blob/fix/treg-pwa-c7-qrcode-fix/report/16-fase-c7-correcao-qr-code.md).
- O relatório 17 está em [`docs/fase-3-checklist-roadmap`](https://github.com/Nifm1584/plugin-v1-pwa/blob/docs/fase-3-checklist-roadmap/report/17-fase-3-checklist-funcional-e-roadmap.md). O HEAD atual é `4c066feb...`; esse commit ajusta somente a redação do relatório 17. Os hashes dos seis arquivos centrais comparados (`plugin.yaml`, `dashboard/manifest.json`, `__init__.py`, `dashboard/pwa/app.js`, `dashboard/plugin_api.py`, `dashboard/dist/qrcode.js`) são iguais entre a branch de documentação e a branch C7.
- A `main` do repositório do plugin continua em `07cacfeb...` e seu `plugin.yaml` ainda declara `hermes-pwa`. Isso é coerente com a decisão de não fazer merge: a versão independente `treg-pwa` está em branches específicas, não na `main`.

## Instalação e evidências de uso

Segundo o último relatório do Hermes incluído no histórico, a instalação na VPS foi fixada no commit C7 `6218f0fd...`; `dashboard/dist/qrcode.js` instalado e publicado tinha SHA-256 idêntico, os assets do TREG respondiam corretamente e o `hermes-pwa` original permanecia intacto. Nesta sessão não houve acesso direto à VPS.

O histórico do usuário registra uso real após a instalação C7: leitura do QR pelo celular e abertura/uso do TREG pelo navegador; envio de foto do celular e análise visual pelo Hermes; conversas, criação de conversas e botões usados no desktop; além de mensagens de áudio enviadas pelo celular e uma transcrição exibida na conversa. Isso é evidência relatada pelo usuário/histórico, não execução independente nesta sessão.

## Divergências que precisam ser reconciliadas

1. `estado-atual.md` apontava a branch de documentação em `bafed166...`; o HEAD atual verificado é `4c066feb...`.
2. O relatório 17 ainda classifica a leitura física do QR como pendente, embora o histórico registre que o usuário testou o QR no celular após instalar o C7.
3. O relatório 17 classifica áudio/transcrição como não validado. O histórico aparenta registrar ao menos um envio real de áudio com texto transcrito; isso deve ser documentado como teste de usuário limitado, sem assumir que foram validados todos os tempos de gravação, player, fallback sem chave ou navegadores.
4. O envio/análise de foto foi validado pelo usuário; isso não comprova persistência da foto após reload ou em outro dispositivo. Persistência é uma questão distinta.
5. O usuário não exige botão próprio de instalação do PWA. O TREG é usado pelo navegador; “adicionar à tela inicial” pelo menu do navegador é opcional, não defeito nem critério obrigatório.
6. Há divergência histórica sobre a versão do Hermes em execução: documentação de fase anterior usa v0.21.6, enquanto um diagnóstico posterior cita v0.22.2. Antes de qualquer integração nova, confirmar a versão real no ambiente alvo e conferir o contrato oficial correspondente.
7. Um relatório de reinstalação C6 registrou a criação de uma pasta de backup na VPS apesar da preferência expressa do usuário por não criar backups adicionais; o relatório da instalação C7 posterior declara que não criou backup. Nenhuma pasta foi removida ou verificada nesta sessão.

## Decisões vigentes

- `treg-pwa` é independente; preservar o `hermes-pwa` original e não alterar o núcleo do Hermes.
- OpenCloud é o responsável por desenvolver/corrigir código; Hermes é auxiliar para inspeção/instalação no ambiente real.
- Não pedir nem criar backups adicionais na VPS por padrão; o usuário já usa snapshot e pediu evitar arquivos de backup.
- Uma fase por vez; inspeção/relatório antes de implementação; revisão do usuário antes de fases seguintes; sem merge na `main`, publicação adicional ou alteração na VPS sem autorização.
- Consultar documentação oficial e contratos da API Hermes antes de qualquer integração; não inventar endpoints, campos ou recursos.
- Design desejado: mensageiro inspirado no WhatsApp, modo claro/escuro com alternância manual, avatares e menus; permitir copiar mensagens e conteúdo integral de blocos de código.
- Não mostrar checkmarks de entregue/lido sem dados reais; `run.completed` não significa que uma tarefa foi semanticamente resolvida.
- Todo prompt futuro deve terminar com `ENCERRAMENTO OBRIGATÓRIO — PRESERVAR O PONTO DE RETOMADA`.

## Próximo ponto de retomada

Primeiro passo recomendado: uma atualização **documental somente** do relatório 17 na branch de documentação, reconciliando as evidências históricas de QR e áudio/transcrição, mantendo explícito o escopo limitado dos testes e sem editar código ou VPS. Após revisão dessa atualização, decidir a próxima fase de implementação, com prioridade inicial de legibilidade/cópia de código e depois tema manual/menus, respeitando o roadmap e validando APIs antes de qualquer integração.

Nenhum código do projeto foi modificado nesta sessão. Nenhuma ação na VPS, instalação, reinício, merge ou alteração na `main` do repositório do projeto foi feita.
