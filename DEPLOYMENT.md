# OpenWA Dashboard - Deployment & Setup Guide

Modern web dashboard for managing OpenWA WhatsApp API Gateway.

## 🚀 Local Development

### Prerequisites
- Node.js 20+
- npm or yarn

### Installation

```bash
npm install
```

### Environment Variables

Create `.env.local` file:

```env
VITE_API_URL=http://localhost:3000
```

### Running

```bash
# Development server with hot reload
npm run dev

# Production build
npm run build

# Preview production build
npm run preview
```

Development server will be available at `http://localhost:5173`

## 🐳 Docker

### Build Image

```bash
docker build -t openwa-dashboard:latest .
```

### Run Container

```bash
docker run -d \
  --name openwa-dashboard \
  -p 80:80 \
  -e VITE_API_URL="http://api:3000" \
  openwa-dashboard:latest
```

Dashboard will be available at `http://localhost`

## 📊 Features

- **Session Management** - Create and monitor WhatsApp sessions
- **QR Code Authentication** - Real-time QR code display for pairing
- **Webhook Configuration** - Setup and test webhooks
- **API Key Management** - Generate and manage API keys
- **Infrastructure Monitoring** - View system health and storage
- **Real-time Updates** - Live updates via WebSocket

## 🎨 Tech Stack

- **React 19** - UI framework
- **Vite** - Build tool & dev server
- **TypeScript** - Type safety
- **TanStack Query** - Data fetching
- **TanStack Table** - Table management
- **React Router** - Navigation
- **Socket.io Client** - WebSocket communication
- **i18next** - Internationalization

## 📝 Build

```bash
# Production build
npm run build

# Output in dist/ folder
```

## 🔧 Configuration

### API Endpoint

Set `VITE_API_URL` environment variable to point to your API:

**Development:**
```bash
VITE_API_URL=http://localhost:3000
```

**Production:**
```bash
VITE_API_URL=https://api.yourdomain.com
```

### Nginx Configuration

The `nginx.conf` handles:
- Static file serving
- SPA routing (all routes to index.html)
- Gzip compression
- Cache control

## 🌍 Internationalization

Supports multiple languages via i18next. Language files in `src/i18n/`

## 🆘 Troubleshooting

**Dashboard won't connect to API**
- Check `VITE_API_URL` environment variable
- Verify API is running on the correct port
- Check browser console for errors
- Ensure CORS is configured on the API

**Build Issues**
```bash
# Clear cache and rebuild
rm -rf dist node_modules
npm install
npm run build
```

**Port Already in Use**
```bash
# Use different port with Vite
npm run dev -- --port 5174
```

## 📦 Related Projects

- **API Server**: See `../openwhatsapp/`
- **Documentation**: See `../docs/`

## 🔗 Docker Compose

For running API and Dashboard together, create a `docker-compose.yml` in the parent folder. Example:

```yaml
version: '3.8'
services:
  api:
    build: ../openwhatsapp
    ports:
      - "3000:3000"
    environment:
      - DATABASE_URL=postgres://user:pass@postgres:5432/openwa
  
  dashboard:
    build: .
    ports:
      - "80:80"
    environment:
      - VITE_API_URL=http://api:3000
```

Then run: `docker-compose up`

## 📄 License

MIT - See LICENSE file
