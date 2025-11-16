# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [1.0.0] - 2025-01-XX

### Added
- Client library `@403xauth/client` for browser and Node.js
- Server library `@403xauth/server-express` for Express.js
- Server library `@403xauth/server-fastify` for Fastify
- Server library `x403auth-server-fastapi` for FastAPI
- Browser wallet support (Phantom, Backpack, Solflare)
- Solana Keypair support for Node.js
- Automatic 403 response handling and retry logic
- Solana signature verification on server
- NFT/SPL gates for access control
- Usage examples for all platforms
- Full documentation

### Features
- Stateless architecture - no sessions or database
- Signatures are bound to specific requests
- Challenge expires after 60 seconds
- Protection against replay attacks

