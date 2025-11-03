# 🍳 Flavora - Recipe Management Application

Modern web and mobile application for managing culinary recipes built with Clean Architecture principles.

## 🏗️ Architecture

- **Backend**: .NET 8, Clean Architecture, CQRS with MediatR
- **Frontend**: React 18, TypeScript, Vite
- **Database**: PostgreSQL 15
- **Storage**: Supabase/Cloudinary
- **CI/CD**: GitHub Actions
- **Hosting**: Vercel (Frontend) + Render (Backend)

## 📁 Project Structure

```
flavora/
├── src/
│   ├── backend/          # .NET Clean Architecture
│   │   ├── Domain/       # Entities, Value Objects, Events
│   │   ├── Application/  # Use Cases, DTOs, Interfaces
│   │   ├── Infrastructure/ # EF Core, External Services
│   │   └── Api/          # REST API Controllers
│   └── frontend/         # React SPA
├── infrastructure/       # Docker, IaC
└── tests/               # Unit, Integration, E2E tests
```

## 🚀 Getting Started

### Prerequisites

- .NET 8 SDK
- Node.js 20+
- Docker & Docker Compose
- PostgreSQL 15 (lub Docker)

### Local Development

1. **Clone repository**

```bash
git clone https://github.com/milewsk/flavora.git
cd flavora
```

2. **Start with Docker Compose**

```bash
docker-compose up -d
```

3. **Or run manually:**

**Backend:**

```bash
cd src/backend
dotnet restore
dotnet ef database update --project src/Flavora.Infrastructure --startup-project src/Flavora.Api
dotnet run --project src/Flavora.Api
```

**Frontend:**

```bash
cd src/frontend
npm install
npm run dev
```

4. **Access the application:**

- Frontend: http://localhost:3000
- Backend API: http://localhost:5000
- Swagger: http://localhost:5000/swagger

## 🧪 Testing

```bash
# Backend tests
cd src/backend
dotnet test

# Frontend tests
cd src/frontend
npm run test
```

## 📦 Deployment

### Automatic Deployment (via GitHub Actions)

Push to `main` branch triggers automatic deployment:

- Frontend → Vercel
- Backend → Render
- Database → Supabase

### Manual Deployment

See [docs/deployment.md](docs/deployment.md) for detailed instructions.

## 🤝 Contributing

1. Fork the repository
2. Create feature branch (`git checkout -b feature/amazing-feature`)
3. Commit changes (`git commit -m 'Add amazing feature'`)
4. Push to branch (`git push origin feature/amazing-feature`)
5. Open Pull Request

## 📝 License

This project is licensed under the MIT License - see [LICENSE](LICENSE) file.

## 👥 Authors

- Your Name - [@milewsk](https://github.com/milewsk)

## 🙏 Acknowledgments

- Clean Architecture by Jason Taylor
- Domain-Driven Design by Eric Evans
