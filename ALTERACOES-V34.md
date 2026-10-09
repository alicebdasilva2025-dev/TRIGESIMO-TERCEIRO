# LiDire — TRIGÉSIMO QUARTO

## Correção do cadastro de familiares
- Corrige erro D1 `NOT NULL constraint failed: family_members.user_id`.
- Ao cadastrar um familiar cujo e-mail ainda não possui conta na LiDire, `user_id` precisa aceitar `NULL` até que exista uma conta associada.
- Na inicialização das rotas familiares, a migração verifica o esquema real do D1. Se `family_members.user_id` estiver marcado como NOT NULL, recria a tabela com a coluna anulável e copia os registros existentes, preservando os dados.
- Mantém o `app.js` da versão TRIGÉSIMO TERCEIRO para evitar mudanças de interface não relacionadas à correção.

## Publicação
Publique os arquivos do ZIP completo no Worker `trigesimo-terceiro`. A migração acontece na primeira chamada autenticada a uma rota familiar/notificações. Depois, teste o cadastro de um e-mail já registrado e de um e-mail ainda não registrado.

## Limitação de validação
A sintaxe do JavaScript pode ser validada localmente, mas a migração deve ser confirmada nos logs do seu Cloudflare D1 real.
