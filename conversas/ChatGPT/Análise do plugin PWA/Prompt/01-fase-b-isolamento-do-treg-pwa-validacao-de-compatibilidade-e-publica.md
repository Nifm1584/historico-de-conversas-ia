# FASE B — Isolamento do TREG-PWA, validação de compatibilidade e publicação no GitHub

> Extraído do histórico da conversa. Confira branch, commit, caminhos e estado atual antes de reutilizar.

# FASE B — Isolamento do TREG-PWA, validação de compatibilidade e publicação no GitHub

## 1. Objetivo

Execute a Fase B do projeto diretamente nos arquivos locais aos quais você já tem acesso.

O objetivo é preparar uma cópia independente do plugin original `hermes-pwa`, identificada como `treg-pwa`, para que possa ser instalada simultaneamente com o plugin original no Hermes Agent v0.21.6 (2026.9.24), sem conflitos de identidade, rotas, comandos, armazenamento local, service worker, manifesto PWA ou estilos.

Após implementar e validar as alterações, atualize o repositório GitHub já existente, crie os relatórios técnicos na pasta `report/` e faça o commit e o push das alterações.

O resultado será utilizado para instalar a cópia no Hermes e testar a coexistência real dos dois plugins.

**Esta tarefa não inclui melhorias visuais, novos recursos de chat, integração com Supabase ou qualquer funcionalidade adicional. O escopo é exclusivamente isolamento, compatibilidade, validação e publicação.**

## 2. Ambiente conhecido

Pasta local do projeto:

`C:\Users\Nilton A\Downloads\treg-v1hermes-plugin\hermes-plugins-main\hermes-pwa`

Repositório GitHub de destino:

`https://github.com/Nifm1584/plugin-v1-pwa`

Versão do plugin de origem: `1.7.1`.

Versão do Hermes instalada na VPS: `Hermes Agent v0.21.6 (2026.9.24)`.

A pasta local contém o código-fonte original do plugin e a documentação de auditoria. Ela não possui, segundo a auditoria anterior, um diretório `.git`. Portanto, não presuma que seja um clone do repositório remoto.

O repositório GitHub já contém uma cópia do projeto e uma pasta `report/`. Consulte o conteúdo remoto antes de modificar ou publicar arquivos.

## 3. Regras obrigatórias

1. Preserve o funcionamento e os contratos existentes do Hermes.
2. Não modifique o núcleo do Hermes.
3. Não altere a instalação do Hermes na VPS.
4. Não instale o plugin na VPS nesta fase.
5. Não execute comandos remotos de instalação, reinicialização ou implantação.
6. Não implemente melhorias visuais ou novas funcionalidades.
7. Não remova funcionalidades existentes do plugin.
8. Não publique alterações diretamente na `main` sem antes estabelecer uma estratégia segura de trabalho e verificar o estado remoto.
9. Não sobrescreva conteúdo remoto sem examiná-lo.
10. Preserve a licença MIT, os créditos de AstraOnlineWeb e o cabeçalho de atribuição do `qrcode-generator`.
11. Não adicione chaves, senhas, tokens ou arquivos `.env` ao Git.
12. Não declare que algo foi testado se o teste não tiver sido realmente executado.
13. Faça alterações pequenas, documentadas e reversíveis.
14. Se surgir um bloqueio que exija uma decisão do usuário, não invente uma solução que possa comprometer o projeto. Documente o bloqueio e interrompa somente a parte afetada.

## 4. Etapa E0 — Preparar uma baseline segura

Antes de editar qualquer arquivo:

1. Examine a estrutura completa da pasta local e a pasta `report/`.
2. Consulte o repositório GitHub `Nifm1584/plugin-v1-pwa`, incluindo a branch principal, os arquivos atuais, os relatórios e os commits recentes.
3. Compare a árvore local com a árvore remota.
4. Identifique os arquivos que existem somente localmente, somente remotamente ou em ambas as partes.
5. Preserve o conteúdo original de referência e registre a versão inicial de cada arquivo que será alterado.
6. Como a pasta local não possui `.git`, estabeleça uma baseline versionada de maneira segura, sem apagar, mover ou substituir o código-fonte original.
7. Se a solução mais segura for criar um clone de trabalho separado, faça isso somente após confirmar o estado remoto e garantir que nenhum arquivo local será perdido.
8. Defina uma branch de trabalho dedicada à Fase B. Se o acesso remoto ou as permissões não permitirem isso, registre o problema antes de tentar publicar alterações.

Registre o SHA do commit remoto inicial e os hashes dos arquivos de referência relevantes, quando as ferramentas disponíveis permitirem.

Não misture artefatos de publicação, relatórios e código de origem sem compreender suas diferenças.

## 5. Etapa E1 — Isolar a identidade declarativa

Utilize `treg-pwa` como identidade-alvo.

Examine e atualize, conforme a estrutura real encontrada:

- Identificador do plugin em `plugin.yaml`.
- Nome correspondente no manifesto do dashboard.
- Registro do plugin e função `register()` ou mecanismo equivalente.
- Identificador e caminho da aba do dashboard.
- Comando de abertura do plugin: `/treg`.
- Rotas próprias do plugin.
- Referências internas que dependam do nome anterior.
- Textos e documentação que identifiquem a cópia como uma instalação independente.

Use `/treg` como rota e comando próprios, quando compatível com o contrato oficial do Hermes.

Verifique se o nome registrado pelo backend corresponde exatamente ao nome declarado no manifesto.

Não altere os endpoints oficiais compartilhados do Hermes, como `/api/sessions` e `/v1/runs`, somente porque eles contêm referências à API.

Não faça substituições globais indiscriminadas de `hermes-pwa`: cada ocorrência deve ser classificada como identidade própria do plugin, referência legítima ao upstream, nome de dependência, atribuição ou contrato compartilhado.

## 6. Etapa E2 — Isolar o estado de execução

Examine os seguintes componentes e implemente o isolamento necessário:

### 6.1 Armazenamento do navegador

- Separe as chaves próprias do `localStorage`, utilizando um namespace consistente como `treg-pwa-*`.
- Evite colisões com as chaves do plugin original.
- Preserve o comportamento de retomada das execuções.
- Não elimine dados existentes de forma indiscriminada.
- Não mova dados sensíveis para o frontend.

### 6.2 Service worker e cache

- Atualize a identidade e a versão do cache para um namespace próprio, por exemplo `treg-pwa-v1`.
- Confirme o escopo do service worker.
- Garanta que a limpeza de caches do TREG não apague caches pertencentes ao plugin original.
- Verifique a coerência entre o registro do service worker, o caminho do arquivo e o escopo permitido pelo servidor.

### 6.3 Estilos

- Preserve o CSS original como referência.
- Identifique as classes específicas do plugin e o prefixo `.hp-*`.
- Renomeie para `.tg-*` somente as classes pertencentes ao plugin que precisam de isolamento.
- Atualize de maneira consistente os seletores correspondentes no CSS, HTML e JavaScript.
- Não renomeie indiscriminadamente classes de bibliotecas externas ou estilos compartilhados do Hermes.

### 6.4 Variáveis de ambiente

Se existir uma configuração própria do plugin, adote o nome `TREG_PWA_API_HOST` apenas se isso for realmente necessário e compatível com o código atual.

Mantenha as variáveis compartilhadas do Hermes intactas, especialmente as relacionadas à autenticação e ao servidor.

Não introduza uma variável sem uso real e não altere a configuração global do Hermes.

## 7. Etapa E3 — Isolar a identidade da PWA

Examine o manifesto web, o HTML e os arquivos de instalação.

Garanta que a cópia tenha identidade própria em:

- `id`.
- `start_url`.
- `scope`.
- Nome completo e nome curto.
- Ícones.
- Cor de tema, quando necessário.
- Referências do manifesto e do service worker.
- Identificadores de cache.

Use valores coerentes com o caminho efetivo da PWA no dashboard do Hermes.

Não presuma que `start_url` e `scope` devam apontar para a raiz do servidor. Eles precisam respeitar o caminho de publicação real da cópia.

Preserve os ícones, a licença e os créditos da origem quando forem reutilizados. Se precisar criar novos ícones, não simule que os arquivos foram produzidos caso isso não tenha sido feito.

A identidade visual pode ser diferenciada minimamente para permitir reconhecer a cópia, mas não execute uma reformulação de design.

## 8. Etapa E4 — Compatibilidade com o Hermes v0.21.6

Use a documentação oficial do Hermes compatível com a versão instalada, sempre que disponível.

Confira:

- Registro e descoberta de plugins.
- Identidade do manifesto e registro do dashboard.
- Registro de comandos.
- Montagem das rotas de backend.
- Publicação de assets.
- Autenticação herdada pelo dashboard.
- Uso das APIs compartilhadas de sessões e execuções.
- Compatibilidade do service worker com a rota publicada.
- Tratamento de dependências privadas.

O código original utiliza `hermes_cli.web_server_profiles._config_profile_scope`. Investigue se a versão v0.21.6 oferece uma alternativa pública compatível.

Não substitua essa função por uma alternativa inventada. Se não existir uma alternativa confirmada, mantenha o comportamento original e documente a dependência. Qualquer adaptação deve ser localizada, ter fallback seguro e preservar as aprovações existentes.

Não altere as regras de autorização para facilitar os testes.

## 9. Etapa E5 — Validar antes de publicar

Execute os testes realmente disponíveis no ambiente.

### 9.1 Testes estáticos

- Conferir os manifestos e suas identidades.
- Verificar se todas as referências aos novos caminhos estão consistentes.
- Procurar referências residuais ao nome antigo que representem colisões reais.
- Procurar referências novas incorretas a `treg-pwa`.
- Verificar o escopo e os nomes do service worker.
- Verificar as chaves de armazenamento.
- Conferir as classes CSS.
- Verificar a preservação das licenças.
- Verificar que nenhum segredo foi incluído nos arquivos destinados ao commit.

### 9.2 Testes automatizados

Executar os testes existentes, incluindo `pytest`, se o ambiente permitir.

Executar também uma verificação sintática de JavaScript, se houver um runtime Node.js disponível.

Não instale dependências, não altere o ambiente global e não faça modificações na VPS apenas para tentar executar esses testes. Se faltar alguma ferramenta, registre exatamente o que não foi possível executar.

### 9.3 Validação das rotas

Quando houver um ambiente de teste autorizado:

- Verificar se o plugin original continua registrado com o nome e a rota originais.
- Verificar se o TREG aparece com o nome e a rota próprios.
- Verificar os endpoints e os assets servidos para cada plugin.
- Verificar o comando `/treg`.
- Verificar a autenticação e a recuperação de sessões.
- Verificar se os recursos compartilhados do Hermes continuam funcionando.

Não afirme que a coexistência foi comprovada somente por uma inspeção estática.

### 9.4 Limitação importante

A instalação simultânea e o funcionamento real dos dois plugins dependem de um ambiente Hermes de teste em que ambos possam ser habilitados sem afetar a instalação de produção.

Se não existir esse ambiente, conclua a validação estática e automatizada possível, publique o resultado com as limitações documentadas e deixe a validação de coexistência como pendência explícita para a instalação controlada pelo usuário.

Não instale automaticamente na VPS de produção.

## 10. Relatórios obrigatórios

Crie ou atualize os documentos abaixo na pasta `report/`, respeitando o padrão de nomes e a organização já existentes.

### Relatório 10 — `report/10-fase-b-isolamento.md`

Documente:

- Objetivo da fase.
- Baseline utilizada.
- Branch e commit inicial.
- Arquivos modificados.
- Mudanças em identidade, rotas, comandos, storage, service worker, CSS e manifesto.
- Contratos compartilhados que foram preservados.
- Dependências privadas identificadas.
- Testes executados e seus resultados reais.
- Testes não executados e motivos.
- Limitações conhecidas.
- Instruções de instalação manual para o usuário.
- Checklist de validação da coexistência.

### Relatório 11 — `report/11-instalacao-e-coexistencia.md`

Crie um plano de validação prático para a instalação da cópia junto com o original.

Inclua uma checklist para verificar:

1. Descoberta dos dois plugins.
2. Identidade e registro de cada plugin.
3. Comandos `/pwa` e `/treg`.
4. Rotas de backend.
5. Carregamento de HTML, JavaScript, CSS e ícones.
6. Autenticação.
7. Listagem e abertura de sessões.
8. Envio e recebimento de mensagens.
9. Streaming e retomada de execuções.
10. Aprovações.
11. Uploads e downloads.
12. Estado e cache independentes.
13. Persistência das preferências.
14. Funcionamento do plugin original após habilitar a cópia.
15. Verificação de que desabilitar a cópia não desativa o original.

Diferencie claramente:

- Teste executado e aprovado.
- Teste executado e reprovado.
- Teste não executado.
- Hipótese ainda não confirmada.

Inclua instruções para recolher logs e evidências sem expor credenciais ou conteúdo sensível.

### Atualização dos relatórios anteriores

Não reescreva nem apague os relatórios existentes sem necessidade. Preserve o histórico da auditoria. Se houver informação que ficou desatualizada, adicione uma nota de atualização referenciando o novo relatório.

## 11. Atualização do GitHub

O repositório de destino é:

`https://github.com/Nifm1584/plugin-v1-pwa`

Antes de publicar:

1. Consulte novamente a branch de destino.
2. Confirme que os relatórios anteriores continuam presentes.
3. Compare as mudanças locais com o estado remoto.
4. Preserve `.gitignore`, `LICENSE`, `README.md` e todos os documentos preexistentes.
5. Inclua os relatórios 10 e 11.
6. Inclua os arquivos de código realmente modificados.
7. Não publique arquivos temporários, caches de execução, credenciais ou arquivos não relacionados.
8. Revise o diff completo antes do commit.
9. Faça o commit em uma branch dedicada à Fase B.
10. Publique essa branch no repositório existente.
11. Não faça merge automático na `main`.
12. Não crie uma release nem declare o plugin pronto para produção antes da validação real de coexistência.

Mensagem de commit sugerida:

`feat(treg-pwa): isolate plugin identity for side-by-side installation`

Se o acesso ao GitHub não estiver disponível, não invente o resultado. Deixe o trabalho local documentado e informe exatamente o que falta para concluir a publicação.

## 12. Critérios de conclusão

A tarefa só estará concluída quando:

- A identidade do TREG estiver separada nos pontos aplicáveis.
- Os contratos compartilhados do Hermes tiverem sido preservados.
- A licença e as atribuições continuarem corretas.
- Os testes possíveis tiverem sido executados e seus resultados registrados.
- Os relatórios 10 e 11 estiverem na pasta `report/`.
- As alterações estiverem publicadas em uma branch dedicada do repositório GitHub, ou a impossibilidade de publicação estiver documentada.
- O diff final estiver revisado.
- O usuário receber uma lista precisa dos arquivos modificados e dos testes realizados.
- As limitações da validação de coexistência estiverem explícitas.

## 13. Relatório final de execução

Ao terminar, apresente um resumo em português contendo:

1. Resultado geral.
2. Branch criada e commit publicado.
3. Link do commit ou da branch.
4. Lista dos arquivos alterados.
5. Relatórios criados.
6. Testes executados, com resultados reais.
7. Testes que ficaram pendentes.
8. Eventuais bloqueios ou decisões ainda necessárias.
9. Instruções exatas para o usuário instalar e validar a cópia.
10. Confirmação explícita de que não houve instalação ou alteração na VPS de produção.

Não avance para melhorias visuais ou novas funcionalidades. A próxima etapa só começa depois que o usuário instalar a cópia e confirmar os resultados da coexistência.
