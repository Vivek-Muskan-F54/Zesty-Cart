# ZeastyCart

ZeastyCart is a full-stack food ordering application with three roles: user, shop owner, and delivery boy. It provides real-time updates (Socket.IO), geolocation tracking (Leaflet), authentication (JWT + Firebase for Google Sign-In), image uploads (Cloudinary), and email notifications (Nodemailer).

## Features
- User: browse shops, view menus, add to cart, checkout, track orders
- Owner: create/edit shop, add/edit items, manage orders
- Delivery boy: receive delivery assignments, update location in real-time
- Real-time events via Socket.IO (new orders, status updates, delivery location)
- OTP-based password reset and delivery OTPs (email)
- Map-based address selection and tracking

## Tech Stack
- Backend: Node.js, Express, MongoDB, Mongoose, Socket.IO
- Frontend: React, Vite, Redux Toolkit, React Router, Tailwind CSS, Leaflet
- Integrations: Cloudinary (image hosting), Nodemailer (email), Firebase (Google Auth), Razorpay (payments)

## Repo Structure (key folders)
- backend/
  - controllers/, models/, routes/, utils/, middlewares/
  - socket.js, index.js
- frontend/
  - src/
    - pages/, components/, redux/, hooks/, assets/
  - vite + Tailwind setup

## Environment Variables

Backend (.env)
- PORT (e.g. 8000)
- MONGODB_URL (mongodb://localhost:27017/your-db)
- JWT_SECRET
- EMAIL (SMTP/email account)
- PASS (SMTP password / app password)
- CLOUDINARY_CLOUD_NAME
- CLOUDINARY_API_KEY
- CLOUDINARY_API_SECRET

Frontend (.env)
- VITE_FIREBASE_APIKEY
- VITE_GEOAPIKEY (optional, for geocoding services)

Example backend .env (already in repo):
PORT=8000
MONGODB_URL="mongodb://localhost:27017/vingo"
JWT_SECRET="your_jwt_secret"
EMAIL="youremail@example.com"
PASS="your_email_password"
CLOUDINARY_CLOUD_NAME="..."
CLOUDINARY_API_KEY="..."
CLOUDINARY_API_SECRET="..."

## Local Setup

1. Clone the repo
   git clone <repo-url>
2. Backend
   cd backend
   npm install
   # start
   npm run dev   # if available
   # or
   node index.js
3. Frontend
   cd ../frontend
   npm install
   npm run dev

Frontend dev server usually runs at http://localhost:5173 and backend at http://localhost:8000. Ensure frontend's serverUrl (src/App.jsx) points to backend if modified.

## Notes
- Ensure MongoDB is running locally or configure MONGODB_URL to a hosted DB.
- Configure Cloudinary and email credentials before creating shops or uploading images.
- Socket features rely on a running backend and connected clients.

## Contributing
PRs welcome. Open an issue for bugs or feature requests.

## License
MIT