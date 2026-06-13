# 🌴 TROPICO - AI-Powered Digital Business Generator

> Generate complete digital businesses in minutes. From landing pages to marketing campaigns to full automation - all powered by AI.

![Tropico](https://img.shields.io/badge/Tropico-v1.0-green)
![Node](https://img.shields.io/badge/Node-18%2B-blue)
![AI](https://img.shields.io/badge/AI-OpenAI%20%7C%20Claude-purple)
![License](https://img.shields.io/badge/License-MIT-yellow)

---

## 🎯 Co to jest TROPICO?

TROPICO to **platforma SaaS zasilana sztuczną inteligencją** która generuje kompletne, gotowe do uruchomienia cyfrowe biznesy. Bez kodowania. Bez umiejętności projektowania. Wystarczy odpowiedzieć na kilka pytań a AI zrobi resztę.

### ✨ Co otrzymujesz:
- 🌐 **AI-Generated Websites** - Responsywne, zoptymalizowane SEO, skoncentrowane na konwersji
- 📧 **Email Automation** - Sekwencje powitalne, przepływy pielęgnacyjne, kampanie
- 📱 **Social Media Content** - 30-dniowy kalendarz zawartości, pomysły postów, tekst
- 🎯 **Ad Campaigns** - Google Ads, Facebook Ads, TikTok copy gotowy do uruchomienia
- 💼 **Business Plans** - Kompletne pitch decki, modele przychodów, KPI
- 🔄 **Clone Competitor Analysis** - Ucz się od najlepszych stron w Twojej niszy
- 📊 **Analytics Dashboard** - Śledź wydajność, konwersje, ROI
- 🎨 **Brand Identity** - Logo, kolory, typografia, głos marki

---

## 🚀 Szybki Start

### Wymagania
```bash
- Node.js 18+
- npm lub yarn
- Git
- OpenAI API Key (lub Claude API Key)
```

### Instalacja

```bash
# Klonuj repozytorium
git clone https://github.com/uimasters/tropic.git
cd tropic

# Zainstaluj zależności
npm install

# Utwórz plik .env
cp .env.example .env

# Dodaj swoje klucze API
# Edytuj .env i dodaj:
# OPENAI_API_KEY=sk-...
# ANTHROPIC_API_KEY=sk-ant-...
# DATABASE_URL=postgresql://...
```

### Uruchamianie TROPICO

#### Opcja 1: Tryb CLI (Szybko i Prosto)
```bash
npm run tropico:cli

# Postępuj zgodnie z poleceniami:
# 1. Jaki biznes chcesz stworzyć?
# 2. Kim są Twoi docelowi klienci?
# 3. Jaki jest Twój budżet?
# 4. Wybierz co chcesz generować (strona, reklamy, maile, itp.)

# Output: Plik ZIP ze wszystkim gotowym
```

#### Opcja 2: Dashboard Web (Pełna Kontrola)
```bash
npm run dev

# Otwórz http://localhost:3000
# Zaloguj się/Zarejestruj
# Kliknij "Create New Business"
# Odpowiedz na pytania AI
# Pobierz wygenerowane zasoby
```

#### Opcja 3: Tryb API (Dla Developers)
```bash
# Uruchom serwer API
npm run server

# Serwer działa na http://localhost:5000
# Zobacz API_DOCS.md dla endpointów
```

---

## 📋 Dostępne Komendy

### Rozwój
```bash
npm run dev              # Uruchom Next.js dashboard (port 3000)
npm run server           # Uruchom Express API (port 5000)
npm run tropico:cli      # Uruchom CLI
npm run worker           # Uruchom worker
npm run db:migrate       # Uruchom migracje bazy danych
npm run db:seed          # Zasianie przykładowych danych
```

### Budowanie
```bash
npm run build            # Buduj do produkcji
npm run build:cli        # Buduj CLI
npm run build:docker     # Buduj Docker image
```

### Testowanie
```bash
npm run test             # Uruchom wszystkie testy
npm run test:watch       # Tryb obserwacji
npm run test:coverage    # Raport pokrycia
npm run lint             # ESLint check
npm run format           # Prettier format
```

### Deployment
```bash
npm run deploy:vercel    # Deploy na Vercel
npm run deploy:docker    # Deploy Docker container
npm run deploy:aws       # Deploy na AWS
```

---

## 🎮 Przykłady Użycia

### Przykład 1: Wygeneruj Sklep E-Commerce
```bash
$ npm run tropico:cli

? Co chcesz stworzyć?
> Sklep e-commerce sprzedający vintage fashion

? Kim jest Twoja grupa docelowa?
> Millenialsowie, wiek 25-40, kochają zrównoważoną modę

? Miesięczny budżet na reklamy?
> $500

? Co chciałbyś wygenerować?
> [x] Strona internetowa
> [x] Sekwencje email
> [x] Kalendarz mediów społecznych
> [x] Kampanie Google Ads
> [x] Plan biznesowy

✨ Generowanie Twojego biznesu...
📦 Tworzenie sklepu e-commerce...
📧 Pisanie sekwencji email...
📱 Budowanie zawartości mediów społecznych...
🎯 Tworzenie tekstu reklam...

✅ Gotowe! Twój biznes jest gotowy.
📥 Pobrano do: ./tropico-vintage-fashion-2026.zip
```

### Przykład 2: Analiza Konkurentów
```bash
$ npm run tropico:clone

? URL konkurenta do analizy:
> https://www.example-fashion-store.com

? Jakie aspekty analizować?
> [x] Struktura strony
> [x] Tekst i wiadomości
> [x] Wzory projektowe
> [x] Kąty marketingowe

✨ Analiza konkurenta...
📊 Znaleziono 47 unikalnych elementów
✅ Wygenerowano unikalne wariantacje
📥 Output: competitor-analysis.json
```

### Przykład 3: Wygeneruj Kampanię Marketingową
```bash
$ npm run tropico:marketing

? Nazwa kampanii?
> Letnia Sprzedaż

? Docelowi klienci?
> Studenci z małym budżetem

? Kanały kampanii?
> [x] Email
> [x] Instagram
> [x] TikTok
> [x] Google Ads

✅ Kampania wygenerowana!
📧 20 szablonów email stworzone
📱 30 postów na media społeczne
🎯 4 wariantacje reklam na platformę
```

---

## 📁 Struktura Projektu

```
tropic/
├── apps/
│   ├── dashboard/           # Interfejs Next.js
│   ├── api/                 # Backend Express.js
│   └── cli/                 # Narzędzie CLI
├── packages/
│   ├── tropico-core/        # Główny silnik AI
│   ├── tropico-templates/   # Wstępnie przygotowane szablony
│   ├── tropico-db/          # Warstwa bazy danych
│   └── tropico-types/       # Typy TypeScript
├── docker/
├── tests/
├── docs/
├── .env.example
├── package.json
├── tsconfig.json
├── turbo.json
└── README.md
```

---

## 🤖 Wyjaśnienie Umiejętności AI

### 1. Website Generator
Generuje w pełni funkcjonalne strony internetowe na podstawie analizy AI Twojego biznesu.
```bash
$ npm run skill:website-generator
```

### 2. Marketing Engine
Tworzy kompletne strategie marketingowe i kalendarze zawartości.
```bash
$ npm run skill:marketing-engine
```

### 3. Email Automation
Buduje sekwencje email dla różnych podróży klientów.
```bash
$ npm run skill:email-automation
```

### 4. Ad Generator
Tworzy tekst reklam specyficzny dla platformy i wariantacje.
```bash
$ npm run skill:ad-generator
```

### 5. Content Cloner
Analizuje konkurentów i generuje unikalne wariantacje.
```bash
$ npm run skill:content-cloner
```

### 6. Brand Identity
Generuje tożsamość wizualną i wytyczne marki.
```bash
$ npm run skill:brand-identity
```

---

## 🔌 Zmienne Środowiska

Utwórz plik `.env`:

```env
# AI APIs
OPENAI_API_KEY=sk-...
ANTHROPIC_API_KEY=sk-ant-...

# Baza danych
DATABASE_URL=postgresql://user:password@localhost:5432/tropico
REDIS_URL=redis://localhost:6379

# Serwer
NODE_ENV=development
PORT=3000
API_PORT=5000

# Integracje
STRIPE_API_KEY=sk_...
MAILCHIMP_API_KEY=...
KLAVIYO_API_KEY=...

# URLs
NEXT_PUBLIC_API_URL=http://localhost:5000
NEXT_PUBLIC_APP_URL=http://localhost:3000
```

---

## 🐳 Setup Docker

### Uruchom z Docker Compose
```bash
docker-compose up

# Usługi uruchamiają się:
# - Web Dashboard: http://localhost:3000
# - API: http://localhost:5000
# - Baza danych: localhost:5432
# - Redis: localhost:6379
```

---

## 🧪 Testowanie

```bash
# Uruchom wszystkie testy
npm run test

# Tryb obserwacji
npm run test:watch

# Raport pokrycia
npm run test:coverage
```

---

## 🚀 Deployment

### Deploy na Vercel (Rekomendowane)
```bash
npm install -g vercel
vercel login
vercel
```

### Deploy na AWS
```bash
npm run build:docker
aws ecr get-login-password --region us-east-1 | docker login --username AWS --password-stdin
docker push [your-ecr-uri]/tropico:latest
```

---

## 📚 Dokumentacja

- **[API Documentation](./docs/API_DOCS.md)** - Kompletna referencia API
- **[Skills Guide](./docs/SKILLS_GUIDE.md)** - Zagłębianie się w umiejętności AI
- **[Architecture](./docs/ARCHITECTURE.md)** - Architektura systemu
- **[Quick Start](./docs/QUICK_START.md)** - Szybki start

---

## 💰 Modele Cenowe

### Bezpłatnie
- 1 strona/miesiąc
- Podstawowe szablony email

### Pro ($29/miesiąc)
- Nieograniczone strony
- Zaawansowane funkcje AI
- Email automation

### Agency ($99/miesiąc)
- Wszystko w Pro
- Zarządzanie zespołem
- White-label option

---

## 🤝 Współpraca

Patrz [CONTRIBUTING.md](./CONTRIBUTING.md) dla wytycznych.

```bash
git clone https://github.com/uimasters/tropic.git
git checkout -b feature/amazing-feature
git commit -m "Add amazing feature"
git push origin feature/amazing-feature
```

---

## 📄 Licencja

MIT License - patrz [LICENSE](./LICENSE)

---

## 🌟 Roadmap

- [x] Website Generator
- [x] Email Automation
- [x] Marketing Calendar
- [ ] AI Video Generation
- [ ] Podcast Generator
- [ ] SEO Optimizer
- [ ] Advanced Analytics
- [ ] Mobile App

---

## 🐛 Bug Reports

Znalazłeś bug? Zgłoś go na [GitHub Issues](https://github.com/uimasters/tropic/issues)

---

## 💬 Społeczność

- 🌐 Website: [tropico.ai](https://tropico.ai)
- 📧 Email: support@tropico.ai

---

**🌴 Gotowy wygenerować swój następny biznes? Zaczynajmy! 🚀**
