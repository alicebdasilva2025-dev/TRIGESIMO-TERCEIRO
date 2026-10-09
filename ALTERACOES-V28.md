# LiDire — VIGÉSIMO OITAVO

## Segurança — PIN / senha do aplicativo

- A tela **Segurança → PIN / senha** foi transformada em uma configuração funcional.
- O usuário pode criar um PIN ou senha de 4 a 64 caracteres.
- O segredo é armazenado no D1 somente como hash PBKDF2; nunca em texto puro.
- A configuração fica vinculada ao usuário autenticado na tabela `app_lock_settings`.
- O bloqueio pode ser ativado, alterado, desativado e acionado manualmente com **Bloquear agora**.
- Quando o bloqueio estiver ativado, a LiDire apresenta uma tela de desbloqueio antes de liberar o aplicativo após uma nova abertura/recarregamento.
- Para alterar ou desativar um bloqueio já configurado, o PIN/senha atual é exigido.

## Backend

Novos endpoints:
- `GET /api/security/app-lock`
- `PUT /api/security/app-lock`
- `POST /api/security/app-lock/verify`

A tabela `app_lock_settings` é criada automaticamente no D1 na primeira utilização.

## Base da versão

VIGÉSIMO SÉTIMO, preservando o URL público configurado para o VIGÉSIMO QUARTO:
`https://vigesimo-quarto.lidire-lifedirector.workers.dev`
