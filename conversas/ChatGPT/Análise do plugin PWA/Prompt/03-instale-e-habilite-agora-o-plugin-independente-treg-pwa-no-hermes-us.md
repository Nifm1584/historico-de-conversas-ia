# Instale e habilite agora o plugin independente treg-pwa no Hermes, usando o repositório...

> Extraído do histórico da conversa. Confira branch, commit, caminhos e estado atual antes de reutilizar.

Instale e habilite agora o plugin independente `treg-pwa` no Hermes, usando o repositório privado `Nifm1584/plugin-v1-pwa` e exclusivamente o commit `a5485bd03174b02ee66ab6d338ff1b8b3cc5ed6f`, correspondente à versão de teste da branch `fase-b-treg-pwa`.

Execute:
`hermes plugins install Nifm1584/plugin-v1-pwa --ref a5485bd03174b02ee66ab6d338ff1b8b3cc5ed6f --enable`

Mantenha o `hermes-pwa` original instalado e habilitado. Após a instalação, recarregue ou reinicie os serviços necessários, confirme que `/treg` e `/api/plugins/treg-pwa/` funcionam e verifique se `/pwa` continua funcionando normalmente. Não altere o núcleo do Hermes, não desinstale o original e não substitua a revisão solicitada por `main` ou outra versão. Ao terminar, apresente o resultado da instalação, os testes executados e eventuais erros.
