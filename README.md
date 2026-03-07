# ALICE-Bridge SaaS

Universal hardware bridge API — protocol-agnostic device communication

## License

AGPL-3.0

## Architecture

```
Frontend :3000  -->  API Gateway :8080  -->  Core Engine :8081
```

| Layer | Port | Technology |
|-------|------|-----------|
| Frontend | 3000 | Next.js 14, Tailwind CSS |
| API Gateway | 8080 | Rust, Axum |
| Core Engine | 8081 | Rust, Axum, ALICE-Bridge |

## Endpoints

| Method | Path | Description |
|--------|------|-------------|
| `POST /api/v1/devices` | デバイス登録 |
| `GET  /api/v1/devices` | 接続デバイス一覧 |
| `POST /api/v1/bridge/send` | デバイスへコマンド送信（WebSocket/MQTT/REST） |
| `GET`  | `/health` | ヘルスチェック |

## Quick Start

```bash
cd services/core-engine
cargo run --release
curl http://localhost:8081/health
```

## Author

Moroya Sakamoto
