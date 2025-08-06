project:
  name: 🎓 CertiStore Pro – Certificate Management Platform
  description: >
    CertiStore Pro is a modern, elegant certificate management tool built for IT professionals. 
    With secure authentication, animated visuals, and smart skill tracking, it helps users upload, 
    view, and analyze their professional certificates — all in one place.

  repository: https://github.com/amankumarjha71391/certistore-pro
  license: MIT
  author: Aman Kumar Jha
  year: 2025

overview:
  title: CertiStore Pro
  summary: >
    CertiStore Pro simplifies certification tracking by enabling secure uploads, skill extraction,
    and animated visualization with user-friendly UI and Supabase backend integration.

features:
  - 🔐 User Authentication via Supabase (email/password)
  - 📤 Upload & Manage Certificates (PDF/Image)
  - 🗃 Certificate Gallery with Edit/Delete
  - 📊 Skill Visualizer using Recharts
  - 🧊 Glassmorphism UI on Vanta.NET background
  - 📱 Fully Mobile-Responsive UI with Hamburger Menu
  - 🔁 Password Reset & Update Flow
  - 🔒 Protected Routes for Authenticated Users
  - ↪️ Auto Redirects on Login/Logout
  - 🎯 Session Listener for Real-Time State Sync

tech_stack:
  frontend:
    - React (with Vite)
    - Tailwind CSS
    - Recharts
    - Vanta.js (NET animation)
  backend:
    - Supabase (Auth, DB, Storage)

setup:
  prerequisites:
    - Node.js (>=18.x)
    - Supabase project (with anon/public key)
  installation:
    - git clone https://github.com/amankumarjha71391/certistore-pro
    - cd certistore-pro
    - npm install
  env_config:
    - Create `.env` in root with:
      - VITE_SUPABASE_URL=https://your-project.supabase.co
      - VITE_SUPABASE_ANON_KEY=your-anon-key
  start_server: npm run dev
  dev_url: http://localhost:5173

routes:
  - path: /
    type: protected
    description: Certificate upload page
  - path: /gallery
    type: protected
    description: View/edit uploaded certificates
  - path: /skills
    type: protected
    description: Visualize recurring skills
  - path: /auth
    type: public
    description: Login / Signup / Forgot Password
  - path: /reset-password
    type: public
    description: Set new password from email link
  - path: /login
    redirect: /auth

deployment:
  platforms:
    - Netlify
  env_notes: >
    Add the `.env` keys (Supabase URL and Anon Key) using each platform’s environment variables UI.

developer_notes:
  - Supabase stores files in `certificates` bucket.
  - Metadata is stored in `certificates` table with title, company, skills, file_url, and user_id.
  - Skill Visualizer aggregates uploaded skill tags.
  - ProtectedRoute is a reusable component for guarding authenticated routes.
  - Hamburger menu toggles using local state and is responsive on small screens.


license:
  type: MIT
  author: Aman Kumar Jha
  year: 2025
