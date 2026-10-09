# LiDire — TRIGÉSIMO TERCEIRO (correção do cadastro familiar)

Esta versão restaura o `app.js` estável da TRIGÉSIMO SEGUNDO e corrige a migração do D1 usada pelo compartilhamento familiar.

- Preserva o fluxo de cadastro familiar do frontend estável.
- Atualiza tabelas `family_groups`, `family_members` e `family_notifications` de forma compatível com schemas antigos.
- Verifica/adiciona as colunas usadas pelos endpoints antes de executar consultas e índices.
- Não apaga tabelas nem registros existentes.

Após publicar, teste o cadastro familiar. A migração é executada pelo Worker quando os endpoints familiares/notificações são chamados.
