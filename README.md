# 🚀 Guia de Execução Local

Este repositório contém duas aplicações: **backend** e **frontend**. Siga os passos abaixo para rodar ambas localmente.

---

## 📦 Backend

### ✅ Passo 1: Criação do Arquivo `.env`
- Crie um arquivo `.env` na raiz do projeto backend.
- Utilize como base o arquivo `.env.example` (ou semelhante, se fornecido).
- Modifique as chaves conforme os seus dados pessoais.

#### ⚠️ Atenção:
Para rodar corretamente a migração com o Prisma, a variável `DATABASE_URL` **deve seguir o seguinte padrão**:

```
postgresql://<usuario>:<senha>@<host>:<porta>/<nome_do_banco>?schema=public
```

**Exemplo:**
```
DATABASE_URL="postgresql://postgres:123456@localhost:5432/meubanco?schema=public"
```

> 💡 Se o banco de dados ainda **não existir**, o Prisma irá criá-lo automaticamente ao rodar o comando `npx prisma migrate dev`, desde que a URL esteja correta e o usuário tenha permissão para isso.

---

### ✅ Passo 2: Instalar Dependências

```bash
npm install
```

---

### ✅ Passo 3: Rodar as Migrações

Este comando irá:

- Criar o banco de dados (se ainda não existir),
- Aplicar todas as migrações definidas na pasta `prisma/migrations`,
- Gerar o Prisma Client automaticamente.

```bash
npx prisma migrate dev
```

---

### ✅ Passo 4: Iniciar o Servidor

```bash
npm run dev
```

---

## 💻 Frontend

### ✅ Passo 1: Instalar Dependências

Dentro da pasta do frontend (geralmente chamada `client`):

```bash
cd client
npm install
```

---

### ✅ Passo 2: Iniciar o Frontend

```bash
npm run dev
```

---

## 📌 Observações Finais

- Certifique-se de que o backend esteja rodando corretamente antes de iniciar o frontend.
- Verifique se o `.env` está devidamente configurado.
- Para evitar erros comuns:
  - Garanta que o PostgreSQL esteja ativo e acessível.
  - Verifique permissões do usuário do banco para criação e alteração de schemas.
  - Utilize a versão adequada do Node.js conforme definida no projeto (verifique `package.json` ou `.nvmrc` se houver).

---