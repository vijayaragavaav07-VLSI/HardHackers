# 🌱 AgriSense AI

## AI-Powered Smart Agricultural Irrigation and Crop Monitoring System

Implementation Plan - AgriSense AI: Smart Agriculture IoT + AI Platform
Project Overview
AgriSense AI is a multi-field, IoT and AI-driven smart agriculture platform designed to empower farmers who manage multiple agricultural fields in dispersed geographic locations. Rather than physically commuting between plots or operating disconnected pump timers, farmers can remotely monitor soil health, ambient weather, rain events, water consumption, power interruptions, and camera feeds—while triggering smart, automated, and power-failure-resilient irrigation.

The platform simultaneously provides agricultural administrators with fleet-level observability, device telemetry, farmer support ticketing, and hardware provisioning tools. Built on React, TypeScript, Vite, Tailwind CSS, Firebase (Auth, Firestore, Storage, Cloud Functions, Hosting) and NVIDIA NIM AI APIs, AgriSense AI matches the visual design, tactile micro-interactions, responsive mobile layout, and multilingual fidelity of the agrisense-ai.html prototype while architecting a modular, enterprise-grade full-stack system.

Visual Design Reference Analysis (agrisense-ai.html)
A complete audit of agrisense-ai.html reveals a curated design language inspired by modern agricultural tech:

1. Colors & Design Tokens
Base Surfaces & Light Mode:
Background: #EDF1E8 (Soft muted earthen sage)
Surface: #FFFFFF
Surface-2: #F5F8F1
Sunken: #E4EADE
Borders: --line: #DAE2D3, --line-2: #C6D2BE
Inks: --ink: #16221A, --ink-2: #47594D, --ink-3: #6E8175
Forest & Nature Core:
Forest tones: #0D2718, #143823, #1D4F32
Leaf tones: #22793E (Primary button/brand), #2E9550, Soft: #DCEFE0
High-impact Lime accent: #B8E14A (Badge/glow/hero accents), Soft: #EAF6C4, Ink: #18340C
Functional Semantics:
Water: #0F8794, Secondary: #22B3C2, Soft: #D5EFF2
Soil: #8A5A38, Soft: #F0E2D5
Warning/Power alert: #A96A00, Soft: #FBEFCD
Bad/Critical: #C0392B, Soft: #F9DFDA
Dark Mode Palette:
Deep chlorophyll darks: --bg: #0A130D, --surface: #111D15, --surface-2: #16251A
Elevated contrast lines (#22362B, #2F4739) and neon green/lime glows (#C4EC55, #3FAF63).
Diagram Tokens (sysdiag):
Field sky #E5F0DF, ground #CDE2C1, soil #6B4A2F, crop rows #4FA765 & #3B9155, pipe #12707B.
2. Typography & Hierarchy
Display Font: Bricolage Grotesque (opsz 12..96, wght 500; 700; 800) for headers, large metric numerals, and brand marks.
Body Font: Figtree (wght 400; 500; 600; 700; 800) for high-legibility UI copy and dashboard data.
Multilingual Native Fonts: Noto Sans Tamil and Noto Sans Devanagari embedded seamlessly.
Monospace: Clean monospace (ui-monospace, JetBrains Mono, Consolas) for technical Field IDs, ESP32 MAC addresses, and sensor timestamps.
3. Layout & App Shell
Desktop Layout: 2-column grid (256px fixed sticky sidebar + minmax(0, 1fr) main content).
Mobile Layout (< 900px): Auto collapses sidebar into sticky top navigation bar with full-width field selector + fixed bottom app navigation dock with quick action badges.
Header: Sticky blurred backdrop (backdrop-filter: blur(16px)), field switcher dropdown with crop pattern swatches, live simulation/synced clock, language selector pills, notification drawer bell, and profile avatar.
4. Interactive Components & Micro-interactions
Cards: Rounded (border-radius: 22px - 26px), clean 1px solid var(--line), subtle layered drop shadows (--shadow, --shadow-lg).
Motor Control Card:
Dynamic state morphing: Off (neutral surface), Running (intense gradient #0E3B26 to #1F8552 with pulsating concentric ripple waves), Paused/Power Interrupted (amber caution state #3A2C08 to #6B4D0B).
Circular SVG countdown timer arc (pathLength="100" with smooth dasharray transition).
Sensors & Visualizations:
240° multi-zone capacitive soil moisture gauge (Dry <45%, Moist 45-80%, Wet >80%).
SVG sparkline trendlines (24-hour historical curves with gradient fills).
Dynamic responsive bar charts with tooltip hover previews for hourly, daily, and monthly water usage.
Interactive SVG system hardware diagram illustrating borewell, pump motor, flow meter, ESP32 controller, cloud uplink, and field crop rows with animated water flow and pulse indicators.
Camera View: Simulated ESP32-CAM snapshot capture with flash animation, live OSD overlays, and historical photo cards.
AI Assistant: Chat thread with streaming message bubbles, typing indicators, quick suggestion chips, voice wave animation modal, and leaf disease scanning canvas with animated laser scanline.
Modals & Drawers: Backdrop blur scrim, bottom sheet on mobile devices, smooth entrance scaling (cubic-bezier(.2, .9, .3, 1.1)).
User Review Required
IMPORTANT

Tailwind CSS Strategy: The prototype uses custom CSS custom properties (variables) with rich color scales and SVG animations. We will configure Tailwind CSS (v3.4) with custom theme extensions that directly map to --leaf, --lime, --forest, --water, --soil, and --surface design tokens so we preserve 100% of the prototype's aesthetic without writing unmaintainable spaghetti styles.

NVIDIA NIM API: Real-world image analysis and agricultural LLM queries will be routed securely via Firebase Cloud Functions so that NVIDIA API keys are never bundled into the client browser build. In local development or demo mode, fallback mock responses can be toggled without requiring an active paid API quota.

Multi-field Isolation: Every field has an immutable fieldId (e.g., FIELD_001). Farmers may only update the human-friendly displayName. Cloud Firestore Security Rules will strictly enforce tenant isolation so farmers only ever read/write fields assigned to their UID.

1. Complete Project Overview
AgriSense AI serves two primary personas:

The Farmer: Needs immediate, high-reliability visibility into remote plots, instant motor on/off override, automatic time-based and soil-based schedules, rain cutoff safeguards, battery-backed power failure recovery, water volume tracking, camera monitoring, and intelligent crop advisory.
The Admin: Needs a control tower to register farmers, provision ESP32 hardware, link fields, inspect controller connectivity (RSSI, battery, heartbeat), monitor network-wide motor activity, and respond to farmer maintenance tickets.
2. Farmer User Flow
No
Yes
No
Yes
Open AgriSense AI
Select Role: Farmer
Farmer Login Screen / Demo Fill
Authenticated?
Show Error & Shake Animation
Has Assigned Fields?
Show No Fields Empty State + Contact Admin
Field Selection Screen
Select Field e.g. Main Road
Field Dashboard
Switch Field Dropdown
Motor & Irrigation Control
Start Pump with Timer
Set Daily Automation Schedule
Review Power Failure Recovery Flow
Configure Rain Protection Threshold
Sensor Hub: Soil, DHT22, Rain, Flow
Water Usage Charts & PDF/CSV Export
ESP32-CAM Snapshots & Capture
AI Agricultural Advisor & Voice Simulation
Crop Disease Leaf Scanner
Crop Recommendations & Profit Estimates
Notification History & Filters
Support Ticket & Chat with Admin
Farmer Profile, Rename Fields, Language EN/TA/HI
3. Admin User Flow
Yes
Open AgriSense AI
Select Role: Admin
Admin Login Screen
Admin Auth?
Admin Fleet Overview Dashboard
Manage Farmers: List, Add, Filter, Inspect
Manage Fields: Add Field, Assign Farmer, Link ESP32
Device Monitoring: Battery, RSSI, Firmware, Reboot
Real-time Farm Health & Motor Grid
Support Tickets: Assign Tech, Reply, Resolve
Admin Profile, Language, Security
4. Required Pages and Routes
We will implement client-side routing using react-router-dom with role-based Route Guards:

Route Path	Allowed Roles	Description	Prototype Reference
/	Public	Role selection landing page	.landing
/login	Public	Farmer and Admin login with demo switch	.login
/forgot-password	Public	Password reset modal/view	login.forgot
/farmer/select-field	Farmer	Multi-field selection grid with search	.pick
/farmer/dashboard	Farmer	Selected field live dashboard	PAGES.farmer.dashboard
/farmer/fields	Farmer	My Fields management & rename modal	PAGES.farmer.fields
/farmer/irrigation	Farmer	Motor control, schedule, power, rain	PAGES.farmer.irrigation
/farmer/sensors	Farmer	Soil, DHT22, Rain, Flow, ESP32 status	PAGES.farmer.sensors
/farmer/water	Farmer	Daily/Weekly/Monthly consumption, PDF	PAGES.farmer.water
/farmer/camera	Farmer	Latest snapshot, capture, image gallery	PAGES.farmer.camera
/farmer/ai	Farmer	AgriSense AI Chat, Voice modal, Leaf scan	PAGES.farmer.ai
/farmer/crops	Farmer	Top 3 crops recommendation & profit	PAGES.farmer.crops
/farmer/notifications	Farmer	Filtered alerts (motor, rain, power, etc.)	PAGES.farmer.notifications
/farmer/support	Farmer	Submit technician request, chat thread	PAGES.farmer.support
/farmer/settings	Farmer	Profile, field names, language, password	PAGES.farmer.settings
/admin/overview	Admin	Fleet overview, motor counts, fleet health	PAGES.admin.overview
/admin/farmers	Admin	Farmer list, add farmer modal, inspect	PAGES.admin.farmers
/admin/fields	Admin	Add field, assign farmer, link ESP32	PAGES.admin.fieldsA
/admin/devices	Admin	Hardware inventory, RSSI, battery, sync	PAGES.admin.devices
/admin/monitoring	Admin	Real-time field grid & sensor metrics	PAGES.admin.monitoring
/admin/requests	Admin	Support ticket inbox, technician assignment	PAGES.admin.requests
/admin/settings	Admin	Admin profile, credentials, preferences	PAGES.admin.settings
5. Frontend Features Architecture
Component Architecture

src/
├── assets/                  # Static assets & SVG icons
├── components/
│   ├── common/              # Button, Input, Modal, Chip, Toggle, Badge, Sparkline
│   ├── layout/              # Sidebar, Topbar, BottomNav, Shell, PageHead
│   ├── dashboard/           # MotorCard, LiveDiagram, SoilGauge, StatCard, WaterMiniBar
│   ├── irrigation/          # MotorControlPanel, SchedulePanel, PowerRecoveryFlow, RainProtection
│   ├── sensors/             # SensorCard, PinoutTable, SignalBars, HistoricalSparklines
│   ├── water/               # WaterChart, UsageTable, PDFReportDocument
│   ├── camera/              # CamViewer, CaptureFlash, ImageGallery
│   ├── ai/                  # ChatList, VoiceModal, ScannerCanvas, CropCards
│   └── admin/               # FleetStatCard, FarmerTable, DeviceTable, TicketThread
├── context/                 # AuthContext, FieldContext, LanguageContext, ThemeContext
├── hooks/                   # useFieldData, useMotorControl, useSensors, useSpeechRecognition
├── i18n/                    # English, Tamil, Hindi translation dictionaries
├── services/                # Firebase client, Firestore repositories, Cloud Function caller
├── types/                   # TypeScript models (User, Field, Telemetry, Ticket, etc.)
└── utils/                   # Geometry math (polar/arc), formatters (date, liters, rupees)
Core Design System Implementation
Theme Variables: Embedded in Tailwind CSS theme config to ensure standard utility classes like bg-leaf, text-lime, border-line-2, and bg-forest.
Sensors Gauge Component: Porting the custom 240-degree SVG circular gauge with dry/opt/wet color zones and animated tick marks.
Dynamic Motor Ripple Card: CSS animations (@keyframes ripple, @keyframes pulse) replicated faithfully for motor state changes.
Interactive System Diagram: Vector SVG system diagram component visualizing the water pipeline, borehole, ESP32 controller, and field sensors with real-time status props.
6. Firebase Backend Features
Firebase Authentication:
Email/Password authentication for Farmers and Admins.
Phone OTP option support ready.
Custom User Claims (role: 'farmer' | 'admin') set via Cloud Functions.
Cloud Firestore:
Real-time listeners (onSnapshot) for instant motor status changes and sensor telemetry.
Batched writes for irrigation start/stop state updates.
Firebase Cloud Storage:
Storing ESP32-CAM daily field images and leaf disease photos uploaded by farmers.
Storage path: /fields/{fieldId}/cam/{timestamp}.webp and /farmers/{uid}/scans/{scanId}.jpg.
Firebase Cloud Functions (Node.js/TypeScript):
onMotorCommand: Secure callable function validating field ownership before toggling motor state.
onPowerFailure: Cloud webhook to log power outages, compute remaining duration, and trigger resumption state.
analyzeCropHealth: Secure proxy to NVIDIA NIM Vision/LLM API with server-side API keys.
generateAgriAdvisory: Context-aware prompt engine combining live soil/weather telemetry with NVIDIA LLMs.
generateWaterReport: Server-side or client-side PDF synthesis with tabular consumption data.
Firebase Hosting:
Fast, global CDN deployment with SPA rewrite rules (rewrites: [ { "source": "**", "destination": "/index.html" } ]).
7. Firestore Collections and Fields
users collection
typescript

interface UserDocument {
  uid: string;
  email: string;
  phone: string;
  displayName: string;
  role: 'farmer' | 'admin';
  assignedFieldIds: string[]; // Permanent internal field IDs
  preferredLanguage: 'en' | 'ta' | 'hi';
  notificationPreferences: {
    motor: boolean;
    power: boolean;
    rain: boolean;
    sensor: boolean;
    ai: boolean;
  };
  district?: string;
  createdAt: FirebaseFirestore.Timestamp;
  lastLoginAt: FirebaseFirestore.Timestamp;
}
fields collection
typescript

interface FieldDocument {
  id: string;                    // Permanent internal ID e.g. "FIELD_001"
  ownerUid: string;              // Farmer's user UID
  displayName: string;           // Custom name editable by farmer (e.g. "Main Road")
  location: string;              // "Main Road, Poonamallee"
  areaAcres: number;             // e.g. 3.5
  soilType: 'red' | 'clay' | 'sandy' | 'alluvial' | 'black';
  currentCrop: string;           // e.g. "groundnut"
  cropStageDays: number;         // e.g. 42
  
  // Hardware Assignment
  esp32Id: string;               // e.g. "ESP32-A1F4C2"
  camId: string;                 // e.g. "ESP32-CAM-001"
  pumpDetails: {
    name: string;                // "Water Pump 01"
    hp: number;                  // 5
  };
  
  // Real-time State
  isOnline: boolean;
  lastHeartbeat: FirebaseFirestore.Timestamp;
  rssiDbm: number;
  batteryPercent: number;
  firmwareVersion: string;
  
  // Live Telemetry
  telemetry: {
    soilMoisturePercent: number; // e.g. 68
    temperatureC: number;        // e.g. 31
    humidityPercent: number;     // e.g. 72
    rainStatus: 'none' | 'light' | 'heavy';
    flowRateLpm: number;         // Liters per minute
    waterTodayLiters: number;
  };
  // Motor & Schedule State
  motorState: {
    isOn: boolean;
    isPaused: boolean;           // True if paused by power failure or rain
    startedAt: FirebaseFirestore.Timestamp | null;
    durationMinutes: number;
    elapsedMinutes: number;
    source: 'manual' | 'auto';
    pauseReason?: 'power_failure' | 'rain_protection' | null;
  };
  schedule: {
    isEnabled: boolean;
    startTime: string;           // "06:00"
    durationMinutes: number;
    activeDays: boolean[];       // [Sun, Mon, Tue, Wed, Thu, Fri, Sat]
  };
  rainProtection: {
    isEnabled: boolean;
    thresholdMinutes: number;    // e.g. 3 minutes continuous
  };
  powerRecovery: {
    hasFailed: boolean;
    failedAt: FirebaseFirestore.Timestamp | null;
    remainingIrrigationMinutes: number;
  };
}
Subcollections & Additional Collections:
fields/{fieldId}/telemetryHistory: Hourly/Daily aggregate documents for graphs (waterLiters, soilAvg, tempAvg, humAvg).
fields/{fieldId}/irrigationRuns: Completed/interrupted irrigation runs (startedAt, endedAt, durationMin, litersUsed, status).
fields/{fieldId}/camImages: Recorded snapshots (imageUrl, timestamp, isSaved, mood).
notifications: Notifications collection indexed by uid and fieldId.
supportRequests: Tickets (id, farmerUid, farmerName, fieldId, type, status: 'pending'|'assigned'|'done', technicianName, thread: []).
8. Authentication and User Roles
Role Selection: Clean initial view presenting the choice between Farmer and Admin, seamlessly persisting role preference.
Farmer Authentication:
Farmers login with mobile or email + password.
Upon successful auth, farmer profile loads and reads assigned fieldIds.
If multiple fields exist, routes to /farmer/select-field. If one exists, directly opens that field.
Admin Authentication:
Secure email/password login.
Custom claims verify role === 'admin'. Non-admins are prevented from accessing any admin routes.
Demo Mode Account: Quick one-click demo credentials as demonstrated in the prototype (9876543210 / farm123 for Farmer, admin@agrisense.ai / admin123 for Admin).
9. Multi-field Management
Permanent Internal Field IDs: System uses FIELD_001, FIELD_002, etc. Immutable to prevent orphaned telemetry or hardware cross-talk.
Farmer Display Name Customization: Farmers can rename their fields anytime via Settings or My Fields without breaking hardware routing.
Active Field Context Provider: A React Context (FieldContext) tracks the currently selected field ID across all farmer sub-pages (/dashboard, /irrigation, /sensors, /water, /camera, /ai).
Global Field Switcher Dropdown: Accessible from the top header on any page, displaying live motor status dot and soil percentage for each plot.
10. Irrigation and Motor-Control Architecture
Control Flow:
Farmer initiates irrigation with custom duration (e.g., 45 min) or schedule triggers automatically.
Frontend issues Cloud Function call startMotor({ fieldId, durationMinutes }).
Cloud Function verifies field ownership, writes motorState: { isOn: true, durationMinutes, elapsedMinutes: 0 } to Firestore.
The ESP32 listens via MQTT or Firestore real-time listener and triggers the GPIO relay.
Power Failure Recovery:
ESP32 has continuous controller battery backup.
If mains pump power drops, ESP32 notes interrupted timestamp and remaining minutes, updating powerRecovery: { hasFailed: true, remainingIrrigationMinutes }.
When power returns, ESP32 automatically resumes the relay for the remaining duration.
Rain Protection:
FC-37 rain sensor detects precipitation.
If rain duration exceeds configured threshold (e.g., 3 minutes), ESP32 safely stops the motor and updates Firestore with pauseReason: 'rain_protection'.
Push notification is dispatched to the farmer.
11. Sensor and ESP32 Integration Plan
Primary Field Sensors:
Soil Moisture: Capacitive analog sensor connected to ADC pin.
Temperature & Humidity: DHT22 connected via single digital data pin.
Rain Sensor: FC-37 digital interrupt pin.
Water Flow: YF-S201 Hall-effect pulse sensor to compute Liters per Minute.
Integration Phases:
Phase 1 (MVP): React frontend with simulated mock telemetry and WebSocket/Firestore state transitions.
Phase 2 (IoT Deployment): ESP32 firmware written in Arduino C++/ESP-IDF publishing JSON payloads over HTTPS/MQTT to Firebase Realtime Database or Cloud Functions endpoint.
Backup Weather API: OpenWeatherMap or Open-Meteo API integrated as secondary backup if local DHT22 reads disconnected.
12. ESP32-CAM Integration Plan
ESP32-CAM takes high-resolution OV2640 snapshot at periodic intervals (e.g., once every 24 hours at 08:00 AM or on-demand via farmer trigger).
Image is uploaded to Firebase Storage via signed URL.
Metadata is appended to fields/{fieldId}/camImages.
Farmer dashboard displays the latest image with OSD timestamp and allows image bookmarking or export to the AI Crop Health Scanner.
13. NVIDIA AI Integration Plan
Secure Backend Integration:
Client sends prompt or image base64 to Firebase Cloud Function queryNvidiaNim.
Cloud Function securely loads NVIDIA_NIM_API_KEY from Google Secret Manager.
NVIDIA NIM Models:
Language Advisory: meta/llama-3.1-70b-instruct or mistralai/mixtral-8x22b-instruct for context-aware farmer query answering (soil advice, irrigation recommendation, multilingual responses).
Vision / Disease Diagnosis: NVIDIA multimodal vision model (meta/llama-3.2-11b-vision-instruct) analyzing leaf images to identify leaf blight, nutrient deficiencies, or pests.
Crop Recommendation Engine:
Algorithmic + LLM recommendation factoring in soil type (red, clay, sandy), soil moisture history, season, and market pricing for the farmer's geographic region.
14. Reports and Notifications
PDF & CSV Export:
Client-side PDF generation using @react-pdf/renderer or jspdf matching the prototype's sheet-doc layout.
CSV export for spreadsheets.
Notification Center:
In-app notification bell with unread badge counter.
Notification categorizations: Motor, Power, Rain, Sensor, AI, and Support Admin replies.
Browser Push Notifications via Firebase Cloud Messaging (FCM).
15. Multilingual Support
Built-in multi-language dictionary for:
English (en)
Tamil - தமிழ் (ta)
Hindi - हिन्दी (hi)
Translations cover 100% of labels, cards, status chips, sensor terminology, motor states, tooltips, and AI assistant prompts.
Farmer's language choice is persisted to localStorage and saved in their Firestore user profile.
16. Security Requirements
Frontend Security:
Zero API keys exposed (Firebase configuration is public by design, but rules strictly constrain it).
NVIDIA API keys, email SMTP credentials, and ESP32 shared secrets exist exclusively in Cloud Functions environment variables / Secret Manager.
Firestore Security Rules:
javascript

rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    function isAuthenticated() { return request.auth != null; }
    function isAdmin() { return request.auth.token.role == 'admin'; }
    function isFieldOwner(fieldId) {
      return request.auth.uid in get(/databases/$(database)/documents/fields/$(fieldId)).data.ownerUid;
    }
    match /users/{userId} {
      allow read, write: if isAuthenticated() && (request.auth.uid == userId || isAdmin());
    }
    match /fields/{fieldId} {
      allow read: if isAuthenticated() && (resource.data.ownerUid == request.auth.uid || isAdmin());
      allow update: if isAuthenticated() && (
        // Farmers can only edit displayName and schedule, not hardware IDs
        (resource.data.ownerUid == request.auth.uid && !request.resource.data.diff(resource.data).affectedKeys().hasAny(['ownerUid', 'id', 'esp32Id', 'camId']))
        || isAdmin()
      );
      allow create, delete: if isAdmin();
    }
    match /supportRequests/{requestId} {
      allow read, create: if isAuthenticated();
      allow update: if isAuthenticated() && (resource.data.farmerUid == request.auth.uid || isAdmin());
    }
  }
}
17. Deployment Requirements (Without Vercel)
The user specifically requested deployment without Vercel.
Target Hosting: Firebase Hosting (Google Cloud CDN).
Setup with firebase.json defining single-page app redirects and caching headers.
Command: firebase deploy --only hosting,functions.
Alternatively supported: Self-hosted Node/Nginx server, Docker container, or Netlify.
18. MVP Features vs. 19. Future Features
Feature Area	MVP (Phase 1)	Future Roadmap (Phase 2 & 3)
Authentication	Email/Password, Role Switcher, Demo Mode	Phone SMS OTP with Twilio / Firebase Auth
Multi-field	Dynamic switching, Renaming, ID preservation	Geofencing, GPS boundary polygon mapping
Irrigation	Manual countdown, Daily schedule, Pause states	Weather forecast predictive watering algorithms
Power Recovery	Simulated flow & historical interruption log	Physical dual-channel relay hardware controller
Sensors	Live telemetry, sparklines, 240° soil gauge	Multi-depth soil moisture probes (10cm, 30cm, 50cm)
Camera	Image feed, capture simulation, photo gallery	Real-time RTSP/WebRTC low-latency streaming
AI Assistant	Full interactive chat, Voice modal simulation, NIM API	Real-time voice TTS/STT native audio streaming
Disease Scan	NVIDIA NIM Multimodal leaf vision diagnosis	Edge AI inference model running directly on ESP32
Language	English, Tamil, Hindi complete support	Regional dialect support (Telugu, Kannada, Marathi)
Export	Printable HTML and CSV report generation	Scheduled automated weekly email/WhatsApp reports
20. Recommended Development Order
Step 1: Foundation & Project Scaffolding
Initialize React + TypeScript + Vite project in workspace root.
Install and configure Tailwind CSS with custom design tokens, fonts (Bricolage Grotesque, Figtree, Noto Sans Tamil/Devanagari), and animations.
Set up React Router, i18n translation system (EN, TA, HI), and state stores.
Step 2: Core Components & Layout Shell
Implement custom SVG components: Soil Gauge, Sparklines, System Diagram, Swatches, and Status Chips.
Build Shell layouts: Desktop Sidebar, Mobile Topbar, Mobile Bottom Dock, Language Picker, and Demo FAB Panel.
Step 3: Landing, Role Selector & Authentication Views
Build high-impact Landing Page with responsive Patchwork Map.
Implement Farmer Login, Admin Login, Password Reset, and 1-Click Demo Fill buttons.
Build the Multi-Field Selection Grid (/farmer/select-field).
Step 4: Farmer Experience Pages
Dashboard: Motor Card with animated ripple state, Live IoT Diagram, Metric Stat Cards, AI Insight snippets.
Irrigation: Motor countdown timer, automated schedule picker, power failure recovery timeline, rain protection threshold slider.
Sensors Hub: Real-time gauge, DHT22 cards, flow sensor meters, ESP32 telemetry diagnostics.
Water Consumption: Dynamic bar charts, hourly/weekly views, printable PDF/HTML report preview.
Camera Hub: ESP32-CAM gallery, capture animation, save bookmarks.
AI Advisory & Scanner: Chat assistant with quick suggestion chips, speech simulation, leaf image scanner with laser animation.
Crops & Profit: Top 3 crop recommendations with suitability matching, yield, cost, and revenue breakdown.
Notifications & Support: Filtered notifications drawer, technician ticket request form, and thread chat.
Settings: Profile editor, field rename modal, language toggle.
Step 5: Admin Experience Pages
Overview: Fleet metrics (online ESP32s, active motors, open requests), fleet breakdown bar.
Farmers Management: Farmer database, add farmer dialog, field count inspect.
Fields Provisioning: Field creation, ESP32 linking, owner assignment.
Device Management: ESP32 hardware inventory, signal RSSI meter, battery health, remote reboot action.
Fleet Monitoring: Real-time grid of all fields with search and status filters.
Support Request Queue: Ticket inbox, technician assignment modal, two-way admin response thread.
Step 6: Backend & Services Layer
Firebase Authentication and Firestore client configuration.
Cloud Functions for secure NVIDIA NIM LLM/Vision proxying.
Firestore Security Rules and deployment configurations (firebase.json).
Recommended Folder Structure

Agrisense AI/
├── index.html
├── package.json
├── tsconfig.json
├── vite.config.ts
├── tailwind.config.js
├── postcss.config.js
├── firebase.json
├── firestore.rules
├── functions/                     # Firebase Cloud Functions
│   ├── src/
│   │   ├── index.ts
│   │   ├── nvidiaProxy.ts         # Secure server-side NVIDIA NIM API calls
│   │   ├── motorController.ts     # Command validation
│   │   └── reportGenerator.ts     # Server PDF synthesis
│   ├── package.json
│   └── tsconfig.json
└── src/
    ├── main.tsx
    ├── App.tsx
    ├── index.css                  # Core CSS variables, typography & Tailwind directives
    ├── types/
    │   ├── field.ts
    │   ├── user.ts
    │   ├── telemetry.ts
    │   ├── ticket.ts
    │   └── ai.ts
    ├── i18n/
    │   ├── index.ts
    │   ├── en.json
    │   ├── ta.json
    │   └── hi.json
    ├── context/
    │   ├── AuthContext.tsx
    │   ├── FieldContext.tsx
    │   └── LanguageContext.tsx
    ├── services/
    │   ├── firebase.ts
    │   ├── fieldService.ts
    │   ├── aiService.ts
    │   └── mockData.ts            # High-fidelity mock state for local demo mode
    ├── components/
    │   ├── common/
    │   │   ├── Button.tsx
    │   │   ├── Chip.tsx
    │   │   ├── Modal.tsx
    │   │   ├── Toggle.tsx
    │   │   ├── Icons.tsx
    │   │   └── SoilGauge.tsx
    │   ├── layout/
    │   │   ├── Sidebar.tsx
    │   │   ├── Topbar.tsx
    │   │   ├── BottomNav.tsx
    │   │   ├── DemoPanel.tsx
    │   │   └── Shell.tsx
    │   ├── dashboard/
    │   │   ├── MotorCard.tsx
    │   │   ├── LiveDiagram.tsx
    │   │   ├── StatCard.tsx
    │   │   └── BarChart.tsx
    │   ├── irrigation/
    │   │   ├── MotorPanel.tsx
    │   │   ├── SchedulePanel.tsx
    │   │   ├── PowerRecoveryPanel.tsx
    │   │   └── RainProtectionPanel.tsx
    │   └── ai/
    │       ├── ChatAssistant.tsx
    │       ├── LeafScanner.tsx
    │       └── VoiceModal.tsx
    ├── pages/
    │   ├── LandingPage.tsx
    │   ├── LoginPage.tsx
    │   ├── farmer/
    │   │   ├── FieldPickerPage.tsx
    │   │   ├── DashboardPage.tsx
    │   │   ├── FieldsPage.tsx
    │   │   ├── IrrigationPage.tsx
    │   │   ├── SensorsPage.tsx
    │   │   ├── WaterUsagePage.tsx
    │   │   ├── CameraPage.tsx
    │   │   ├── AIAssistantPage.tsx
    │   │   ├── CropRecomPage.tsx
    │   │   ├── NotificationsPage.tsx
    │   │   ├── SupportPage.tsx
    │   │   └── SettingsPage.tsx
    │   └── admin/
    │       ├── AdminOverviewPage.tsx
    │       ├── FarmersPage.tsx
    │       ├── AdminFieldsPage.tsx
    │       ├── DevicesPage.tsx
    │       ├── MonitoringPage.tsx
    │       └── RequestsPage.tsx
    └── utils/
        ├── formatters.ts
        ├── svgHelpers.ts
        └── math.ts
Verification Plan
Automated Tests
Unit tests for arithmetic helpers (water consumption calculation, soil zone thresholds, schedule duration clamp).
Component testing for SoilGauge, MotorCard, and SystemDiagram using Vitest / React Testing Library.
Build verification: npm run build to validate strict TypeScript typing and zero bundle warnings.
Manual Verification Checklist
Visual Fidelity Verification: Compare side-by-side with agrisense-ai.html for exact color harmony, font rendering, card corner radii, and padding.
Mobile Responsiveness: Test at 375px (iPhone), 768px (iPad/Tablet), and 1440px (Desktop) to ensure bottom navigation, mobile drawer sheets, and responsive grids adapt smoothly.
Multi-field Switching: Switch between "Main Road", "Village Side", "East Farm", and "Lake Road", verifying all telemetry, charts, and motor controls update immediately to the selected field.
Field Renaming: Rename "Main Road" to "Main Road Paddy Field", verifying the display name changes everywhere while internal ID FIELD-001 remains untouched.
Role Isolation: Log in as Farmer and verify Admin routes are strictly blocked. Log in as Admin and verify complete fleet visibility.
Multilingual Verification: Switch between English, Tamil, and Hindi, verifying full UI text conversion without layout breaks.
Simulations / Demo Panel: Toggle simulated power outage, rain detection, controller offline state, and speed acceleration to test recovery and safeguard UI states.College of Engineering and Technology, Department of EE – VLSI**, for **Smart India Hackathon 2026 Problem Statement PSH4**.

The system uses ESP32-based IoT hardware to monitor soil moisture, temperature, humidity, water availability, and other environmental parameters. It automatically manages irrigation according to crop requirements while integrating weather intelligence and AI-based decision support.

The platform extends beyond conventional irrigation automation by providing crop intelligence, crop health monitoring, water analytics, farm history, yield intelligence, and next-crop recommendations.

---

# 🏆 43. Final Vision

```text
             AGRISENSE AI

        SMART AGRICULTURE
               │
      ┌────────┼────────┐
      │        │        │
     IoT      AI     WEATHER
      │        │        │
      └────────┼────────┘
               │
        FARM INTELLIGENCE
               │
      ┌────────┼────────┐
      │        │        │
   WATER     CROP     FARM
 MANAGEMENT HEALTH  MANAGEMENT
      │        │        │
      └────────┼────────┘
               │
       BETTER FARM DECISIONS
               │
               ▼
       SUSTAINABLE FARMING
```

---

# 👨‍💻 Team

## HardHackers

### RMK College of Engineering and Technology

### Department of EE – VLSI(design & technology)

**Team Members**

1. **Vijayaragavaa V**
2. **Luckshana M S**
3. **PUNUGOTI GEETHIKA**
4. **AAKASH DEVIN M S**
5. **PAVANJE KARAN K**
6. **SREE RANJAN R**

---

# 🏁 SIH 2026

### Problem Statement

**PSH4 – Smart Agricultural Irrigation and Crop Monitoring System**

### Project

# 🌱 AgriSense AI

### Team

# ⚡ HardHackers

### Institution

# 🏫 RMK College of Engineering and Technology

### Department

# 🔬 EE – VLSI(design & technology)

---

## 🌱 AgriSense AI

> **From Smart Irrigation to Intelligent Farming.**
