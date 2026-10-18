# Modelo padrão — histórico de conversa de projeto

Copie esta pasta para cada nova conversa/projeto que precise preservar contexto para continuidade com qualquer agente de IA.

## Arquivos obrigatórios

1. `README.md` — finalidade da pasta, ordem de leitura e links do projeto.
2. `historico.md` — histórico completo em ordem cronológica, sem substituir por resumo.
3. `estado-atual.md` — decisões vigentes, situação confirmada, pendências e próximo passo.
4. `INSTRUCAO-PARA-NOVO-AGENTE.md` — instrução pronta para copiar e colar no agente novo.

## Ao copiar o modelo

- Renomeie a pasta com o título da conversa/projeto.
- Coloque o histórico integral no arquivo `historico.md`.
- Preencha `estado-atual.md` usando evidências do histórico e do repositório de código.
- Atualize no README e na instrução todos os links: repositório do histórico, pasta desta conversa, repositório do projeto e pasta de relatórios.
- Remova exemplos e detalhes herdados de outros projetos. Nunca deixe links do TREG PWA em outro projeto.
- Registre o que está planejado separadamente do que foi executado e validado.
- Remova segredos, tokens, chaves de API, cookies e dados privados antes de publicar.
- Preserve o histórico original; atualizações de estado devem ficar em arquivos separados.

## Exemplo de estrutura

```text
NOME-DA-CONVERSA/
├── README.md
├── historico.md
├── estado-atual.md
└── INSTRUCAO-PARA-NOVO-AGENTE.md
```

Este modelo é a referência padrão para as novas pastas de histórico neste repositório.