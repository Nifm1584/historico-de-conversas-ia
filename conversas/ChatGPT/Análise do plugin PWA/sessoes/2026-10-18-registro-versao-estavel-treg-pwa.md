# Registro da versão estável C7 do TREG PWA — 2026-10-18

> **Tipo de registro:** resumo estruturado/checkpoint desta sessão. **Não é uma transcrição integral.** O `historico.md` original foi preservado sem alterações.

## Escopo

Fase 1: registrar a versão C7 validada como referência estável do TREG PWA, por meio de tag anotada e Release, sem alterar código, a `main`, a instalação existente ou a VPS.

## Verificações prévias

- Commit C7: `6218f0fd25a2047b5caba09cf854af74058db03d`.
- Branch `fix/treg-pwa-c7-qrcode-fix` com HEAD nesse commit.
- Nenhuma tag e nenhuma Release existiam antes do registro.
- A referência da tag `treg-pwa-v1.0.0-estavel` retornou 404 antes da criação.
- CI do commit: workflow run `39075301916`, conclusão `success`.
- Documentação oficial do GitHub consultada para criação da Release; a tag foi criada como objeto anotado.

## Tag e Release

- Tag anotada: `treg-pwa-v1.0.0-estavel`.
- Objeto da tag: `1d4137e21d127cf2e7490d171c5502bcbfb75155`.
- Commit apontado: `6218f0fd25a2047b5caba09cf854af74058db03d`.
- URL da tag: https://github.com/Nifm1584/plugin-v1-pwa/tree/treg-pwa-v1.0.0-estavel
- Release: `TREG PWA — Versão estável validada C7`, ID `416672282`.
- URL da Release: https://github.com/Nifm1584/plugin-v1-pwa/releases/tag/treg-pwa-v1.0.0-estavel
- Estado: publicada, `draft: false`, `prerelease: false`, publicada em 2026-10-18T19:55:42Z.
- A tag não foi movida nem reutilizada.

## Evidências e limites

- A Release registra a correção do QR Code e os testes automatizados documentados no projeto: suíte Node 3/3, CI `39075301916` success, checagens de sintaxe JS, compilação Python e 2 testes pytest.
- A leitura física do QR Code, o funcionamento no navegador do celular e o uso do aplicativo instalado na VPS são **validações manuais relatadas pelo usuário**, não reexecuções desta fase.
- A tag é anotada, mas não assinada criptograficamente; o GitHub a marca como `unsigned`.
- Nenhum teste foi reexecutado durante a criação da tag/Release.
- A Release não representa garantia de ausência de defeitos nem substitui testes futuros.

## Documentação publicada

- Relatório de fase: `report/18-fase-1-registro-versao-estavel-c7.md`, branch `docs/fase-1-versao-estavel-c7`, commit `5c892ef5ba1ce57ce9cc36292bc409e7086f3882`.
- Link: https://github.com/Nifm1584/plugin-v1-pwa/blob/docs/fase-1-versao-estavel-c7/report/18-fase-1-registro-versao-estavel-c7.md
- Este arquivo de sessão e a atualização de `estado-atual.md` serão publicados em branch própria do repositório de histórico.
- `historico.md` original não foi alterado.

## Integridade e operações não realizadas

- `main` do projeto: `07cacfeb7a5af3650a1bdf3335af2be3262806aa`, intacta.
- Nenhum arquivo de código foi alterado.
- Nenhuma tag foi movida ou reutilizada.
- Nenhuma operação na VPS: sem instalação, reinstalação, reinício, backup ou alteração do plugin original.
- Nenhum merge na `main`.
- A Fase 2 não foi iniciada.

## Ponto exato de retomada

- **Concluído:** tag anotada e Release publicadas e verificadas; relatório 18 publicado; documentação de histórico em publicação.
- **Pendente:** revisão do usuário e autorização explícita para a próxima fase.
- **Próximo passo único:** aguardar autorização. Não reinstalar nem alterar a VPS.
- **Referência estável:** tag `treg-pwa-v1.0.0-estavel` → commit `6218f0fd25a2047b5caba09cf854af74058db03d`.
