# Y3D Creations — Backend (API)

Express 5 + TypeScript + MySQL + JWT.

## Rodar

```bash
cp .env.example .env        # ajuste as variáveis
npm install
npm run dev                 # desenvolvimento (porta 3000)
# ou: npm run build && npm start
```

O banco é criado com o script `database/database.sql` (estrutura + catálogo inicial):

```bash
mysql -u y3d_user -p y3d < database/database.sql
```

## Docker

```bash
docker build -t y3d-backend .
docker run --env-file .env -p 3000:3000 y3d-backend
```

O container precisa alcançar o MySQL (`DB_HOST`).

## Rotas

Tudo sob `/api`. Exceto `/api/auth/*` e `/api/health`, toda rota exige JWT; `/api/admin/*` exige também o claim de administrador (e-mails em `ADMIN_EMAILS`).
