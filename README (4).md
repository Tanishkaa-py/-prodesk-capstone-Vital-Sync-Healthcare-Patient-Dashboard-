<div align="center">

# 🏥 VitalSync
### Healthcare Patient Dashboard — Capstone Project

![Next.js](https://img.shields.io/badge/Next.js_14-000000?style=for-the-badge&logo=nextdotjs&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=for-the-badge&logo=typescript&logoColor=white)
![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-06B6D4?style=for-the-badge&logo=tailwindcss&logoColor=white)
![MongoDB](https://img.shields.io/badge/MongoDB-47A248?style=for-the-badge&logo=mongodb&logoColor=white)
![NextAuth.js](https://img.shields.io/badge/NextAuth.js-000000?style=for-the-badge&logo=next.js&logoColor=white)

**Track:** Fullstack | **Intern:** [Your Name] | **Cohort:** ProDesk Internship Week 13–17

</div>

---

## 📋 Project Description

VitalSync is a full-stack, commercial-grade **Healthcare Patient Dashboard** that modernizes the hospital management experience for both doctors and patients. Built as a Capstone project over 5 weeks, it simulates a real-world hospital interface with multi-role authentication, appointment scheduling, medical history tracking, and real-time availability management.

The application is designed to be **production-ready in architecture** — meaning every decision (database schema, API routes, auth strategy, component structure) mirrors how professional engineering teams build healthcare software.

> **Problem it solves:** Traditional hospital portals are clunky, slow, and role-agnostic. VitalSync delivers a clean, role-specific experience — doctors see their schedule and patient queue; patients see their health timeline and upcoming appointments.

---

## 🎯 Track

**Fullstack** — This project covers the complete development stack:
- Frontend: UI, routing, component design, state management
- Backend: REST API routes, database modeling, authentication, middleware
- DevOps: Deployment on Vercel with MongoDB Atlas in production

---

## 🛠️ Tech Stack

| Layer | Technology | Purpose |
|---|---|---|
| **Framework** | Next.js 14 (App Router) | Full-stack React framework with SSR |
| **Language** | TypeScript | Type safety across frontend + backend |
| **Styling** | Tailwind CSS | Utility-first component styling |
| **Database** | MongoDB + Mongoose | Document-based NoSQL database |
| **Auth** | NextAuth.js v5 | Role-based authentication (Doctor / Patient) |
| **State** | Zustand | Lightweight client-side state management |
| **API** | Next.js Route Handlers | REST API endpoints within the framework |
| **File Storage** | Cloudinary | Profile images and document uploads |
| **Deployment** | Vercel + MongoDB Atlas | Production hosting |
| **UI Components** | shadcn/ui | Accessible, composable component library |
| **Charts** | Recharts | Health metric visualizations |
| **Date Handling** | date-fns | Appointment scheduling logic |

---

## ✨ Core Features

### 🔐 Authentication & Role System
- Secure login and registration with NextAuth.js (JWT strategy)
- Two distinct roles: **Doctor** and **Patient**
- Role-based route protection via Next.js middleware
- Profile setup flow after first login (specialty for doctors, DOB/blood type for patients)
- Session persistence with secure HTTP-only cookies

### 🏠 Role-Specific Dashboards
- **Patient Dashboard:** Upcoming appointments, recent prescriptions, active doctors, quick health stats (blood type, allergies, last visit)
- **Doctor Dashboard:** Today's schedule, patient queue, availability toggle, total appointments summary, recent patient activity

### 📅 Appointment Booking System
- Patients can browse available doctors filtered by specialty
- Real-time availability checker — shows only open time slots
- Double-booking prevention enforced at the API level
- Appointment status tracking: `Pending → Confirmed → Completed / Cancelled`
- Doctors can confirm or cancel appointments from their dashboard

### 📜 Medical History Timeline
- Chronological timeline of all past visits for each patient
- Each entry stores: date, doctor name, diagnosis, notes, and attached prescriptions
- Doctors can add new history entries after a consultation
- Patients can view (read-only) their complete history

### 💊 Prescriptions Viewer
- Structured prescription cards: medication name, dosage, frequency, duration, prescribed by
- Patients see all active and past prescriptions
- Doctors can create new prescriptions linked to a patient and appointment
- Status labels: `Active`, `Completed`, `Discontinued`

### 🟢 Real-Time Doctor Availability
- Doctors toggle their availability status (Available / Busy / Off Duty)
- Patients see only available doctors during booking
- Doctor profile shows weekly schedule slots they have set up

### 🔍 Search & Filter
- Patients can search doctors by name or specialty
- Doctors can search their patient list
- Filter appointments by status, date range

---

## 🗂️ Project Structure

```
prodesk-capstone-VitalSync/
├── app/
│   ├── (auth)/
│   │   ├── login/page.tsx
│   │   └── register/page.tsx
│   ├── (dashboard)/
│   │   ├── patient/
│   │   │   ├── page.tsx              # Patient dashboard
│   │   │   ├── appointments/page.tsx
│   │   │   ├── history/page.tsx
│   │   │   └── prescriptions/page.tsx
│   │   └── doctor/
│   │       ├── page.tsx              # Doctor dashboard
│   │       ├── schedule/page.tsx
│   │       └── patients/page.tsx
│   └── api/
│       ├── auth/[...nextauth]/route.ts
│       ├── appointments/route.ts
│       ├── doctors/route.ts
│       ├── prescriptions/route.ts
│       └── history/route.ts
├── components/
│   ├── ui/                           # shadcn/ui base components
│   ├── dashboard/                    # Dashboard-specific components
│   ├── appointments/                 # Booking flow components
│   └── shared/                      # Navbar, Sidebar, Cards
├── lib/
│   ├── db.ts                         # MongoDB connection
│   ├── auth.ts                       # NextAuth config
│   └── utils.ts
├── models/
│   ├── User.ts
│   ├── Appointment.ts
│   ├── MedicalRecord.ts
│   ├── Prescription.ts
│   └── DoctorProfile.ts
├── middleware.ts                     # Route protection by role
└── types/
    └── index.ts                      # Shared TypeScript types
```

---

## 🖼️ UI Wireframes

> **Figma Design File:** [🔗 Add your Figma link here after designing]

Screens designed:
1. Login / Role Selection Page
2. Patient Dashboard (main view)
3. Doctor Dashboard (main view)
4. Appointment Booking Flow

---

## 🗃️ Database Architecture (ERD)

> **ERD Diagram:** See `/docs/erd-diagram.png` below

![ERD Diagram](./docs/erd-diagram.png)

**Collections:**
- `users` — Stores all users with a `role` field (doctor | patient)
- `doctorprofiles` — Extended profile data for doctors (specialty, availability, schedule)
- `appointments` — All booked appointments linking patient ↔ doctor
- `medicalrecords` — Patient visit history entries
- `prescriptions` — Medication prescriptions linked to patient + doctor

---

## 📅 5-Week Development Plan

| Week | Focus | Deliverables |
|---|---|---|
| **Week 13** | Planning & Architecture | README/PRD, Figma Wireframes, ERD Diagram |
| **Week 14** | Scaffolding & Auth | Repo setup, Next.js + MongoDB connection, NextAuth with roles, middleware |
| **Week 15** | Core Features | Appointment booking API, Patient & Doctor dashboards, Medical history |
| **Week 16** | UI Polish & Remaining Features | Prescriptions viewer, Availability toggle, Search & Filter, Responsive design |
| **Week 17** | Testing, Deployment & Docs | Bug fixes, Vercel deployment, MongoDB Atlas setup, Final README |

---

## 🚀 Getting Started (Local Development)

```bash
# 1. Clone the repository
git clone https://github.com/[your-username]/prodesk-capstone-VitalSync.git
cd prodesk-capstone-VitalSync

# 2. Install dependencies
npm install

# 3. Set up environment variables
cp .env.example .env.local
# Fill in: MONGODB_URI, NEXTAUTH_SECRET, NEXTAUTH_URL, CLOUDINARY keys

# 4. Run the development server
npm run dev

# Open http://localhost:3000
```

### Environment Variables

```env
MONGODB_URI=mongodb+srv://...
NEXTAUTH_SECRET=your-secret-key
NEXTAUTH_URL=http://localhost:3000
CLOUDINARY_CLOUD_NAME=...
CLOUDINARY_API_KEY=...
CLOUDINARY_API_SECRET=...
```

---

## 📌 API Endpoints

| Method | Endpoint | Description | Auth Required |
|---|---|---|---|
| POST | `/api/auth/register` | Register new user | No |
| GET | `/api/doctors` | List all available doctors | Patient |
| GET | `/api/doctors/:id` | Get doctor profile + slots | Patient |
| POST | `/api/appointments` | Book appointment | Patient |
| GET | `/api/appointments` | Get my appointments | Both |
| PATCH | `/api/appointments/:id` | Confirm / Cancel appointment | Doctor |
| GET | `/api/history/:patientId` | Get medical history | Both |
| POST | `/api/history` | Add new history entry | Doctor |
| GET | `/api/prescriptions/:patientId` | Get prescriptions | Both |
| POST | `/api/prescriptions` | Create prescription | Doctor |
| PATCH | `/api/doctors/availability` | Toggle availability | Doctor |

---

## 🎓 Evaluation Criteria

This project is evaluated on:
- ✅ Clean, scalable code architecture
- ✅ Proper role-based authentication & route protection
- ✅ All core features fully functional
- ✅ Modern, responsive UI design
- ✅ Well-structured API with error handling
- ✅ Deployed and accessible production URL

---

<div align="center">

**Built with ❤️ as part of the ProDesk Internship Capstone — Week 13 to 17**

</div>
