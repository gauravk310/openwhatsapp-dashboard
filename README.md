# OpenWA Dashboard

Modern web dashboard for managing OpenWA WhatsApp API Gateway sessions, webhooks, and infrastructure.

> 📦 **Standalone Project** - See [DEPLOYMENT.md](./DEPLOYMENT.md) for setup and deployment guide.

## ✨ Features

- **Session Management** - Create, monitor, and control WhatsApp sessions
- **QR Code Authentication** - Real-time QR code display for device pairing
- **Webhook Configuration** - Configure and test webhook endpoints
- **API Key Management** - Generate and manage API keys
- **Infrastructure Monitoring** - View system health and storage status
- **Real-time Updates** - Live session status via WebSocket

## 🛠️ Tech Stack

| Technology       | Purpose                 |
| ---------------- | ----------------------- |
| React 19         | UI Framework            |
| TypeScript       | Type Safety             |
| Vite 7           | Build Tool              |
| React Router 7   | Client-side Routing     |
| TanStack Query   | Server State Management |
| TanStack Table   | Data Tables             |
| Socket.IO Client | Real-time Communication |
| Lucide React     | Icons                   |

## 🚀 Getting Started

### Prerequisites

- Node.js 20+
- npm or yarn

### Development

```bash
# Install dependencies
npm install

# Start development server
npm run dev
```

Dashboard will be available at `http://localhost:5173`

### Production Build

```bash
# Build for production
npm run build

# Preview production build
npm run preview
```

## 🔗 API Connection

Configure the API URL via environment variable in `.env.local`:

```env
VITE_API_URL=http://localhost:3000
```

See [DEPLOYMENT.md](./DEPLOYMENT.md) for full setup instructions.

## 📄 License

MIT License - Part of the [OpenWA](https://github.com/rmyndharis/OpenWA) project.
