# Fleet Management — Real-Time Fuel Theft Detection & GPS Tracking

> A real-time monitoring system for fuel theft detection with GPS tracking for land-based trucks.

![React](https://img.shields.io/badge/React-18-61DAFB?logo=react&logoColor=white)
![Vite](https://img.shields.io/badge/Vite-5-646CFF?logo=vite&logoColor=white)
![Firebase](https://img.shields.io/badge/Firebase-10-FFCA28?logo=firebase&logoColor=black)
![Leaflet](https://img.shields.io/badge/Leaflet-1.9-199900?logo=leaflet&logoColor=white)
![TailwindCSS](https://img.shields.io/badge/Tailwind_CSS-3.4-06B6D4?logo=tailwindcss&logoColor=white)
![Vercel](https://img.shields.io/badge/Deployed_on-Vercel-000000?logo=vercel&logoColor=white)

---

## About

This project is a **Fuel Theft Detection** system designed to monitor fuel levels and track the location of land-based trucks in real-time. It was developed as part of our **BSCS Thesis** at **STI College Bacoor** and was awarded the **Most Innovative Project and Study**.

The system combines IoT hardware with a modern web dashboard to detect fuel theft, provide GPS location data, enforce geofencing boundaries, and generate detailed fleet reports — giving fleet operators full visibility and security over their operations.

---

## Features

- **Real-Time GPS Tracking** — Live map visualization of truck locations using Leaflet with auto-updating markers
- **Fuel Level Monitoring** — Continuous fuel percentage tracking with theft detection alerts
- **Alarm System** — Instant notifications for abnormal fuel consumption or geofence violations
- **Geofencing** — Define virtual boundaries; receive alerts when trucks enter or leave designated zones
- **Report Generation** — View, filter, and export detailed fleet reports as PDF
- **Admin & Driver Management** — Full CRUD operations for administrators and drivers
- **Truck Management** — Register, edit, and monitor individual trucks
- **Path Distance Tracking** — Calculate and log distance traveled by each truck
- **Authentication** — Firebase-based login with route protection
- **PWA Support** — Installable as a Progressive Web App for mobile use

---

## Tech Stack

| Layer          | Technology                            |
| -------------- | ------------------------------------- |
| **Frontend**   | React 18, Vite 5                      |
| **Styling**    | Tailwind CSS 3.4, shadcn/ui, Radix UI |
| **Maps**       | Leaflet, React-Leaflet, Turf.js       |
| **Charts**     | Chart.js, react-chartjs-2             |
| **Backend**    | Node.js, Express (hosted on Render)   |
| **Database**   | Firebase Realtime Database, Firestore |
| **Auth**       | Firebase Authentication               |
| **Real-Time**  | Socket.IO                             |
| **PDF Export** | jsPDF, html2canvas                    |
| **Deployment** | Vercel (client), Render (API)         |

---

## Hardware Components

| Component                       | Purpose                                             |
| ------------------------------- | --------------------------------------------------- |
| ESP32 Microcontroller           | Core processing and Wi-Fi connectivity              |
| Resistive Fuel Sensor           | Measures fuel levels in the tank                    |
| NEO-6M GPS Module               | Provides real-time location coordinates             |
| LiFePO4 Battery                 | Backup power supply                                 |
| Solar Panel + Charge Controller | Renewable energy source for the system              |
| Buck Converter                  | Voltage regulation                                  |
| Automatic Transfer Switch (ATS) | Reliable switching between primary and backup power |

---

## Project Structure

```text
FleetManagementBuild/
├── README.md
└── client/
    └── FleetManagementThesis/
        ├── package.json                  # Dependencies & scripts
        ├── vite.config.js                # Vite + PWA configuration
        ├── tailwind.config.js            # Tailwind CSS configuration
        ├── public/                       # Static assets & PWA icons
        └── src/
            ├── main.jsx                  # React DOM entry
            ├── App.jsx                   # Router & app shell
            ├── Firebase.js               # Firebase initialization
            ├── hooks/                    # Custom React hooks
            ├── utils/                    # Utility functions
            ├── components/               # UI components & shadcn primitives
            └── pages/                    # Route-level views (Dashboard, reports, etc.)
```

---

## Getting Started

### Prerequisites

- [Node.js](https://nodejs.org/) (v16+)
- npm or yarn

### Installation

```bash
# Clone the repository
git clone https://github.com/yourusername/FleetManagementBuild.git
cd FleetManagementBuild/client/FleetManagementThesis

# Install dependencies
npm install

# Start the development server
npm run dev
```

The app will be available at `http://localhost:5173`.

### Build for Production

```bash
npm run build
npm run preview
```

---

## Deployment

| Service             | URL                                           |
| ------------------- | --------------------------------------------- |
| **Client (Vercel)** | Deployed via `vercel.json` configuration      |
| **API (Render)**    | `https://thesis-api-bmpc.onrender.com/api/v1` |

---

## Team

This project was developed as a thesis requirement at **STI College Bacoor**:

- **John Robin Buluran**
- **Arwill Josh Polinag**
- **Marl Joshua Banaguas**
- **Philip Andrew Guiritan**
- **Andrian Serrano**

---

## Awards

- **Most Innovative Project and Study** — BSCS Thesis

---

## License

This project was developed for academic purposes as part of a BSCS Thesis at STI College Bacoor.
