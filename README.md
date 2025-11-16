# 403xAuth SDK

Stateless Web3 authentication for Solana applications. Client and server libraries.

## 📦 Packages

- **@403xauth/client** - Client library for browser and Node.js
- **@403xauth/server-express** - Middleware for Express.js
- **@403xauth/server-fastify** - Plugin for Fastify
- **@403xauth/server-fastapi** - Middleware for FastAPI (Python)

## 🚀 Quick Start

### Client (JavaScript/TypeScript)

```bash
npm install @403xauth/client
```

```javascript
import { AuthClient } from '@403xauth/client';

const client = new AuthClient({
  wallet: window.solana, // or keypair for Node.js
});

const response = await client.fetch('/api/profile');
```

### Server (Express)

```bash
npm install @403xauth/server-express
```

```javascript
import express from 'express';
import { authMiddleware } from '@403xauth/server-express';

const app = express();

app.get('/api/profile', authMiddleware(), (req, res) => {
  res.json({ wallet: req.auth.wallet });
});
```

### Server (FastAPI)

```bash
pip install 403xauth-server-fastapi
```

```python
from fastapi import FastAPI, Request
from x403auth_server_fastapi import auth_middleware

app = FastAPI()

# Apply middleware
app.middleware("http")(auth_middleware())

@app.get("/api/profile")
async def profile(request: Request):
    return {"wallet": request.state.auth.wallet}
```

## 📚 Documentation

Full documentation is available in the `examples/` folder and on the [project website](https://403xauth.xyz/docs).

## 🔐 How It Works

1. Client makes a request to a protected API
2. Server responds with `403 Forbidden` + challenge (nonce + payload)
3. Client cryptographically signs the challenge
4. Client retries the request with signature in headers
5. Server verifies the signature and grants access

## ✨ Features

- ✅ Stateless - no sessions or database
- ✅ Secure - signatures are bound to specific requests
- ✅ Universal - works with any HTTP client
- ✅ NFT/SPL gates - access control based on token ownership
- ✅ Cross-framework - Express, Fastify, FastAPI

## 📄 License

MIT

