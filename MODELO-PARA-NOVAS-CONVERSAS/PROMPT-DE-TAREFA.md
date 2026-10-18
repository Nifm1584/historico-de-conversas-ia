# Modelo de prompt para executar uma tarefa

> Preencha os campos entre colchetes. Mantenha o escopo limitado à fase aprovada. Use este modelo junto com `INSTRUCAO-PARA-NOVO-AGENTE.md` e `estado-atual.md`.

## Fase / tarefa
[Nome curto da fase e da tarefa]

## Objetivo
[Resultado esperado, observável e verificável]

## Antes de agir
- Leia `README.md`, o histórico relevante e `estado-atual.md`.
- Inspecione o repositório real; informe branch e commit inicial.
- Confira os relatórios e evidências existentes para não repetir trabalho nem contradizer decisões aprovadas.
- Se a tarefa depender de APIs ou ferramentas externas, consulte a documentação oficial atual.
- Se houver conflito, risco ou requisito essencial ausente, pare e relate antes de alterar.

## Escopo autorizado
**Fazer:** [ações permitidas nesta fase]

**Não fazer:** [áreas validadas que devem permanecer intocadas; fases futuras; produção; merge/publicação, salvo autorização explícita]

## Execução e validação
1. Faça apenas o trabalho autorizado.
2. Execute os testes adequados e registre comandos/resultados ou evidências disponíveis.
3. Não alegue sucesso se não houver evidência. Separe teste automatizado, validação manual e validação no ambiente real.
4. Crie/atualize o relatório da fase no local combinado, se isso fizer parte do fluxo autorizado.
5. Pare ao concluir esta fase. Não avance automaticamente para a próxima.

## Resultado esperado
[Arquivos/funcionalidades/relatório que devem resultar desta tarefa]

## ENCERRAMENTO OBRIGATÓRIO — PRESERVAR O PONTO DE RETOMADA

Antes de encerrar, entregue o relatório e atualize `estado-atual.md` no repositório de histórico, se houver acesso e autorização. Preserve `historico.md` integral e cronológico; não o substitua por resumo. Registre:

- **Tarefa/fase:** o que foi concluído e o que ficou fora do escopo.
- **Resultado confirmado:** fatos observáveis, sem exagerar o que foi validado.
- **Arquivos:** caminhos criados, alterados ou removidos e resumo das mudanças.
- **Testes/evidências:** o que foi executado, resultados e limitações; separar testes automatizados, validações manuais e ambiente real.
- **Git:** repositório, branch, commit inicial e commit final, se aplicável.
- **Ações não realizadas:** por exemplo, sem commit, push, merge, instalação, reinício ou alteração de produção.
- **Pendências/divergências:** o que falta confirmar e quais evidências estão ausentes.
- **PONTO EXATO DE RETOMADA:** estado real ao parar, próximo passo único recomendado, aprovação necessária e a próxima ação/prompt sugerida.

Se não puder editar o repositório de histórico, não tiver permissão para publicar ou não houver ferramenta disponível, devolva na resposta o conteúdo completo para atualizar `estado-atual.md` e diga claramente que não gravou no GitHub. Nunca afirme que atualizou um arquivo sem verificar.

Este checkpoint documenta o ponto de parada; **não concede autorização para iniciar a próxima fase**. Respeite o escopo, não toque em partes validadas sem necessidade e não publique, faça merge, instale nem altere produção sem autorização explícita.

## Arquivamento separado da sessão

Ao encerrar a tarefa, preserve a sessão atual em `sessoes/AAAA-MM-DD-assunto-curto.md`, sem sobrescrever arquivos de sessões anteriores e sem substituir o `historico.md` original. Use a transcrição integral quando disponível; se produzir apenas resumo/checkpoint, rotule-o claramente. Atualize `estado-atual.md`. Se não houver acesso/autorização para gravar o arquivo no repositório, devolva o conteúdo pronto para salvar e informe que não foi publicado.
