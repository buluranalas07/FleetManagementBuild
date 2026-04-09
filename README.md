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

```
FleetManagementBuild/
├── README.md
└── client/
    └── FleetManagementThesis/
        ├── index.html                    # App entry point
        ├── package.json                  # Dependencies & scripts
        ├── vite.config.js                # Vite + PWA configuration
        ├── tailwind.config.js            # Tailwind CSS configuration
        ├── postcss.config.js             # PostCSS configuration
        ├── eslint.config.js              # ESLint rules
        ├── components.json               # shadcn/ui configuration
        ├── vercel.json                   # Vercel deployment settings
        ├── jsconfig.json                 # JS path aliases
        │
        ├── public/                       # Static assets & PWA icons
        │   ├── favicon.ico
        │   ├── favicon-16x16.png
        │   ├── favicon-32x32.png
        │   ├── android-chrome-192x192.png
        │   ├── android-chrome-512x512.png
        │   └── apple-touch-icon.png
        │
        └── src/
            ├── main.jsx                  # React DOM entry
            ├── App.jsx                   # Router & app shell
            ├── App.css                   # Global app styles
            ├── index.css                 # Tailwind base styles
            ├── Firebase.js               # Firebase initialization
            │
            ├── assets/                   # Static images & SVGs
            │   ├── react.svg
            │   └── truck.png
            │
            ├── config/
            │   └── config.js             # API base URL (dev/prod)
            │
            ├── lib/
            │   └── utils.js              # shadcn/ui utility (cn)
            │
            ├── hooks/                    # Custom React hooks
            │   ├── useAddAdmins.jsx
            │   ├── useAddDrivers.jsx
            │   ├── useAddTruck.jsx
            │   ├── useFetch.jsx
            │   └── useValidateForm.jsx
            │
            ├── utils/                    # Utility functions
            │   ├── checkGeofenceStatus.js
            │   ├── eventEmitter.js
            │   ├── pathDistance.js
            │   ├── validateAdminForm.jsx
            │   ├── validateDriverForm.jsx
            │   └── validateTruckForm.jsx
            │
            ├── layout/
            │   └── Main-Layout.jsx       # Sidebar + navbar shell
            │
            ├── components/               # Shared UI components
            │   ├── AlarmListener.jsx      # Fuel theft alarm handler
            │   ├── AuthListener.jsx       # Auth state observer
            │   ├── ChangeMapView.jsx      # Map viewport control
            │   ├── Footer.jsx
            │   ├── GeoFence.jsx           # Geofence rendering
            │   ├── GeofenceListener.jsx   # Geofence event handler
            │   ├── GlobalGeofenceHandler.jsx  # App-wide geofence logic
            │   ├── IsLoggedIn.jsx         # Auth route guard
            │   ├── Map.jsx                # Leaflet map wrapper
            │   ├── Modal.jsx              # Reusable modal
            │   ├── Navbar.jsx             # Top navigation bar
            │   ├── PathDistanceListener.jsx   # Distance tracking
            │   ├── Sidebar.jsx            # Side navigation
            │   ├── Spinner.jsx            # Loading indicator
            │   ├── TruckListCard.jsx      # Truck summary card
            │   │
            │   └── ui/                   # shadcn/ui primitives
            │       ├── avatar.jsx
            │       ├── button.jsx
            │       ├── card.jsx
            │       ├── dialog.jsx
            │       ├── input.jsx
            │       ├── label.jsx
            │       ├── radio-group.jsx
            │       ├── scroll-area.jsx
            │       ├── select.jsx
            │       ├── table.jsx
            │       └── tooltip.jsx
            │
            └── pages/                    # Route-level views
                ├── Login.jsx              # Authentication page
                ├── Dashboard.jsx          # GPS map + truck list
                ├── Add-Admin.jsx          # Create admin account
                ├── Add-Driver.jsx         # Register new driver
                ├── Add-Truck.jsx          # Register new truck
                ├── Edit-Admin.jsx         # Update admin details
                ├── Edit-Truck.jsx         # Update truck details
                ├── View-Admins.jsx        # Admin list table
                ├── View-Driver.jsx        # Single driver detail
                ├── View-Drivers.jsx       # Driver list table
                ├── View-Truck.jsx         # Single truck detail
                ├── View-Trucks.jsx        # Truck list table
                ├── View-Report.jsx        # Single report detail
                ├── View-Reports.jsx       # Report list table
                └── Not-Found.jsx          # 404 page
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
