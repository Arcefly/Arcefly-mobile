# Arcefly — Mobile App

Ionic mobile app for Arcefly, built for passengers/clients to browse flights, book seats, and manage their own reservations from their phone.

🔗 **Backend repo**: [Arcefly-backend](https://github.com/Arcefly/Arcefly-backend)
🔗 **Admin panel repo**: [Arcefly-fronted](https://github.com/Arcefly/Arcefly-fronted)
🔗 **Project page**: [crissdeev.netlify.app/proyecto-arcefly](https://crissdeev.netlify.app/proyecto-arcefly)

> ⚠️ **Status: on hold.** The app is fully designed and works correctly when run locally (`ionic serve` / dev build). The compiled Android APK currently fails to reach the production backend due to a CORS configuration issue with the `capacitor://` origin — this affects only the packaged app, not local development. Fix planned for a future iteration.

## Features

- User registration and login
- Browse available flights
- Seat selection and booking confirmation flow
- View and manage personal reservations
- User profile management
- Premium client tier with gated features (`premium.guard`)

## Tech Stack

- **Framework**: Ionic 8 + Angular 19
- **Native runtime**: Capacitor 7 (Android target)
- **UI**: Angular Material, Angular CDK, Ionicons
- **Storage**: Ionic Storage
- **Styling**: Sass

## Architecture

```
src/app/
├── guards/           Route guards (auth, premium tier gating)
├── interceptors/      HTTP interceptor for auth tokens
├── models/            TypeScript interfaces (viaje, reserva, usuario...)
├── pages/
│   ├── home/           Landing/dashboard page
│   ├── login/          Login page
│   ├── registro/       Registration page
│   ├── perfil/         User profile page
│   ├── vuelos/         Flight browsing page
│   └── reservas/
│       └── confirmar-reserva/   Seat selection & booking confirmation
├── pipes/             Custom pipes (truncate, etc.)
└── services/          API communication (auth, cliente, viaje, reserva, asiento)
```

## Running Locally

```bash
git clone https://github.com/Arcefly/Arcefly-mobile.git
cd Arcefly-mobile
npm install
ionic serve
```

To build the Android APK:

```bash
ionic build
npx cap sync android
npx cap open android
```

## Related Repositories

| Repo | Description |
|---|---|
| [Arcefly-backend](https://github.com/Arcefly/Arcefly-backend) | Spring Boot REST API |
| [Arcefly-fronted](https://github.com/Arcefly/Arcefly-fronted) | Angular admin panel |
