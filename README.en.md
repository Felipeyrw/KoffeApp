# 🔗 koffe

> Offline-first management system for barbershops and small businesses.

[![Flutter](https://img.shields.io/badge/Flutter-3.4+-02569B?logo=flutter)](https://flutter.dev)
[![Platform](https://img.shields.io/badge/Platform-Android-blue?logo=android)](https://flutter.dev)
[![License](https://img.shields.io/badge/License-Copyright-red)](LICENSE)

---

## 📱 About the App

**koffe** is a complete management system, built with an **offline-first** approach:
all data is stored locally first, syncing automatically with the cloud when connected. This means the app works **100% even without internet**.

The goal is to become a scalable **SaaS** (Software as a Service), starting with barbershops but prepared for other segments.

### Key Differentials

- **Offline-First** — Works without internet, syncs when connected
- **Smart Notifications** — Customizable reminders with contextual messages
- **Financial Control** — Income, expenses, profit and detailed reports
- **Theme Customization** — 3 exclusive themes (Classic, Clean, Dark)
- **Modular Architecture** — Solid foundation for growth and maintenance

---

## ✨ Features

### 🗓️ Scheduling & Appointments

Complete scheduling with visual calendar (table_calendar). Status management, client + service + payment method association. Historical appointments by period with advanced filters. Support for walk-in and registered clients.

### 👥 Clients

Full registration with phone, WhatsApp, email and notes. Service history per client. Search and filter by name. Soft delete with undo — prevents accidents. Offline-first synchronization.

### 💰 Financial Control

Tracking of **fixed and variable expenses** with due date control. Pay/receive payment records. Filters by period and status. Visual progress bar for partial payments. **Daily/monthly closing** with profit calculation.

### 📊 Reports

Visual dashboards with **performance charts** (fl_chart). Period filters: week, month, bimonthly, semester, year. Best/worst day analysis. Automatic **tax calculation** on gross revenue. Export in **PDF and Excel** via share_plus.

### ⚙️ Flexible Settings

- **Taxes** — Registration of types and categories with different rates. Automatic calculation on revenue. Historical calculation records by period.

- **Services** — Complete catalog with name, price (R$) and duration (minutes). Direct association with the schedule. Edit and delete with undo.

- **Hours & Availability** — **Shift control by day of week** (max 3/day). Breaks between appointments. **Day-off requests** and **vacation**. Full weekly visualization.

- **Payment Methods** — Flexible configuration of accepted payment methods. Inline activate/deactivate. Synchronization between devices.

### 🔔 Notification System

Scheduled notifications via **flutter_local_notifications** with timezone awareness. **Contextual messages** generated dynamically:
- Appointment reminder (X minutes before, customizable)
- Day summary (number of appointments + expected revenue)
- Tomorrow's schedule (next day agenda)
- Expense due date reminder

Messages in Brazilian style, motivational and humorous. Exact alarms support (Android).

### 🎨 Themes

3 exclusive themes with color preview:
- **Santos Classic** — Coffee/brown traditional tones (woody feel)
- **Santos Clean** — Minimalist white and clean
- **Santos Dark** — Elegant dark background with coffee tones

All themes use **Material Design 3** with consistent colors throughout the app.

### 🔒 Security

- **Local encryption** — SQLCipher for SQLite database
- **Secure storage** — flutter_secure_storage for tokens (Keychain/Keystore)
- **Biometric authentication** — Fingerprint / Face ID via local_auth
- **Device tracking** — Suspicious login detection
- **Two-factor verification** — Via Supabase Edge Functions (Deno)

### 📡 Synchronization

Offline-first architecture with **14 specialized sync managers**:
- Appointments, Clients, Expenses, Services, Barbearia
- Schedules, Shifts, Days-off, Vacation, Breaks
- Payment methods, Taxes, Expense payments

Each record receives an `operacao_pendente` flag and is synced in the background when connected.

---

## 🛡️ Architecture

**Simplified Modular Monolith** — well-separated modules that can evolve into microservices when needed.

```
lib/
├── main.dart, sec.dart, auth_gate.dart
│
├── base/                           # Infrastructure
│   ├── banco/                      # SQLite + SQLCipher
│   │   ├── DAO/                    # Data Access Objects
│   │   ├── modelos/                # Data entities
│   │   ├── db.dart                 # SqliteController
│   │   └── migracoes/              # Migration scripts
│   ├── sync/                       # Background sync
│   │   ├── gerenciadores/          # 14 sync managers
│   │   ├── repositoriosSync/       # Sync logic
│   │   └── servico_sincronizacao.dart
│   ├── servicos/                   # Business services
│   │   ├── notificacoes/           # Notifications + scheduler
│   │   └── telaService/            # Screen services
│   ├── seguranca/                  # Security
│   │   ├── secure_storage_service.dart
│   │   └── securityServices/       # Device + Auth + Connectivity
│   ├── util/                       # Helpers (formatters, logger, etc.)
│   └── constantes/                 # Global constants
│
├── comum/                         # Shared
│   ├── fallback/                  # SBToast, fallbacks
│   └── widgets/                   # Reusable widgets
│
└── modulos/                        # Features/Pages
    ├── autenticacao/               # Login, signup, recovery
    ├── home/                       # Main navigation
    ├── dashboard/                  # Financial overview
    ├── atendimentos/              # Schedule and appointments
    ├── clientes/                   # Client management
    ├── despesas/                   # Expense registration
    ├── controleFinanceiro/          # Pay/receive + reports
    ├── configuracoes/             # Services, schedules, themes, etc.
    ├── perfil/                     # Barbearia data
    ├── relatorios/                 # Exportable reports
    └── importar/                  # Data import
```

### Offline-First Flow

```
┌──────────────────┐       ┌──────────────────┐
│   SQLite Local   │ ←───→  │   Supabase DB    │
│  (SQLCipher)      │ sync   │    (Remote)      │
└──────────────────┘       └──────────────────┘
         ↑
  base/sync/
  (background)
```

---

## 🧩 Tech Stack

| Layer | Technology |
|-------|------------|
| **Frontend** | Flutter 3.4+ |
| **State Management** | Provider + Get |
| **Local Database** | SQLite + SQLCipher (encrypted) |
| **Backend & Auth** | Supabase (PostgreSQL) |
| **Edge Functions** | Deno (Supabase Edge) |
| **Security** | flutter_secure_storage, local_auth, device_info_plus |
| **Notifications** | flutter_local_notifications, flutter_timezone, timezone |
| **Charts** | fl_chart |
| **Export** | excel, pdf, printing, share_plus |
| **Calendar** | table_calendar |
| **Localization** | flutter_localizations (PT-BR, EN-US) |
| **Image** | image_picker, cached_network_image |
| **Networking** | connectivity_plus, http |
| **Utils** | intl, uuid, logger |

---

## 🚀 Getting Started

> This repository is for demonstration only. Source code is not publicly available.

### Prerequisites

- Flutter SDK 3.4+
- Supabase Account (for backend)
- Android Studio / VS Code + Extensions

### Setup

```bash
# Clone the repository
git clone https://github.com/Felipeyrw/koffe.git
cd koffe

# Install dependencies
flutter pub get

# Configure environment variables
# Create a .env file in the root with:
# SUPABASE_URL=https://your-project.supabase.co
# SUPABASE_ANON_KEY=your-anon-key

# Build Android
flutter build apk --release
```

---

## 📖 FAQ

> Frequently asked questions about the project.

**Q: Does the app work without internet?**

Yes! koffe is 100% offline-first. All data is stored locally first and syncs automatically when connected. You can register clients, schedule appointments, log expenses — everything works offline.

**Q: Which platforms are supported?**

Currently, **Android** only. Support for iOS, Linux Desktop and Web (PWA) is on the roadmap for future phases.

**Q: How does synchronization work?**

The app uses a **write-local-first** architecture. Each record is saved to local SQLite first, with an `operacao_pendente` flag. When connected, sync managers send changes to Supabase in the background — no user intervention needed.

**Q: Can I use it on multiple devices?**

Yes, with the same account. Data syncs across devices through Supabase. Offline changes are merged when connected.

**Q: Is the app secure?**

Yes. Uses **SQLCipher** for local database encryption, **flutter_secure_storage** (Keychain/Keystore) for tokens, **biometric authentication** (fingerprint / Face ID) and **device tracking** for suspicious login detection.

**Q: Can I export reports?**

Yes! Reports can be exported in **PDF** and **Excel**, with period filters (week, month, bimonthly, semester, year).

**Q: How do notifications work?**

The notification system is smart and contextual. There are 4 types: **appointment reminder** (X minutes before), **day summary** (morning), **tomorrow's schedule** (night) and **expense reminder**. Messages are dynamically generated in motivational Brazilian style.

**Q: How do I customize themes?**

Go to Settings → Themes. You can preview each theme with its colors before selecting. Preference is stored locally.

**Q: How does schedule management work?**

In Settings → Schedules, you define shifts by day of week (max 3 per day), breaks between appointments, day-off requests and vacation. The system respects these hours in the schedule.

---

## 🗺️ Roadmap

### 🔴 Now (Implemented)

- [x] Scheduling and appointments (visual calendar, status, client+service association)
- [x] Client registration and management (with delete undo)
- [x] Fixed and variable expense control
- [x] Pay/receive payment system
- [x] Daily/monthly closing with profit calculation
- [x] Financial reports with charts (fl_chart)
- [x] PDF / Excel export
- [x] Service management (name, price, duration)
- [x] Shift, break, day-off and vacation control
- [x] Notification system with scheduler
- [x] 3 themes (Classic, Clean, Dark)
- [x] Biometric authentication
- [x] Offline-first synchronization (14 sync managers)
- [x] Local encryption (SQLCipher)
- [x] Secure token storage

### 🟡 Next (Coming Soon)

- [ ] Google Play Store publication
- [ ] Multi-barber support (multiple professionals in the same barbershop)
- [ ] Home screen widgets (Android)
- [ ] Real-time shared history across devices
- [ ] Automatic cloud backup (configurable)
- [ ] Web companion dashboard (remote management)

### 🟢 Later (Planned)

- [ ] **iOS** support (App Store)
- [ ] **Linux Desktop** support
- [ ] **Web** support (PWA)
- [ ] Complete PWA version
- [ ] **WhatsApp Business API** integration
- [ ] Full web dashboard for remote management
- [ ] AI for predictive financial analysis
- [ ] Loyalty / points program module
- [ ] Support for other segments (beauty salons, aesthetic clinics)
- [ ] Public API for integrations (webhooks)

---

## 🤝 Contributing

This is a **private project**.

Contributions are open for **business partnership**. If you have expertise in Flutter, UI/UX, backend, mobile or business development and are interested in a strategic partnership, reach out.

This repository serves as a **public demonstration** of the **koffe** app, containing product documentation.

---

## 📄 License

Copyright (c) 2024 koffe. All rights reserved.
