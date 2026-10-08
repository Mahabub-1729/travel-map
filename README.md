# Group Tour Booking

A Bangladesh group-tour bus booking starter built with Next.js + PostgreSQL + Prisma.

## Features
- 45-seat bus booking
- Seat availability checking
- Temporary 10-minute booking hold
- bKash server-side payment adapter
- Paid booking confirmation
- Printable ticket / Save as PDF from browser
- QR code on ticket
- Bangladesh district/tourist-place section
- Basic admin dashboard
- Ready for expansion to authentication, SMS, email, refunds and reports

## Setup

1. Install Node.js 20.19+ (or current supported Node release).
2. Create a PostgreSQL database.
3. Copy `.env.example` to `.env` and fill `DATABASE_URL`.
4. Install packages:
   `npm install`
5. Create database tables:
   `npx prisma db push`
6. Seed sample trips:
   `npx tsx prisma/seed.ts`
7. Start:
   `npm run dev`
8. Open:
   `http://localhost:3000`

## bKash
Create/obtain a merchant integration from bKash and put credentials in `.env`.
Never put APP_SECRET, password or tokens in client-side code.
Use sandbox first, then production credentials/base URL supplied for your merchant account.

## Production hardening still required
- Admin authentication and role-based access
- Database transaction/locking for high-concurrency seat booking
- bKash webhook/reconciliation
- Payment amount verification against the booking
- Rate limiting and CAPTCHA
- SMS/email ticket delivery
- Cancellation/refund policy and refund workflow
- Privacy policy/terms
- Secure logging and monitoring
- Proper 64-district GeoJSON map with clickable polygons
- Tourist place database with photos/routes
- HTTPS and production environment variables
