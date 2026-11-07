 Virtual Fit  -  wear it before you buy it

A full-stack virtual try-on fashion platform. Upload one front-facing full-body
The garment is chosen from a database of garments and sizes and then the garment is scaled to fit the user's pose. The garment is then rendered before and after scaling and the results are returned in around 50ms.

 Stack

- Frontend: Next.js 16 (App Router), React 19, Tailwind CSS 4, Lucide icons
- The backend of the application will be created using Next.js route handlers to provide a clean REST API with a uniform JSON envelope for each API endpoint.
- Database: PostgreSQL + Drizzle ORM (users, sessions, categories, products,
The following is a list of the various features that are provided to users of the website, categorized by the type of feature that they are: 

per-size stock, uploads, try-on jobs, cart, wishlist, orders
- AI/CV: sharp preprocessing (auto-orient, EXIF strip, re-encode) → heuristic
  pose detector returning a MediaPipe-compatible landmark contract → geometric
  garment warp. A real diffusion try-on model plugs in via the `TryOnModel`
The following example describes an interface that can be used to communicate with a Tryon provider over HTTP without making any changes to the code of the caller application.
- Auth/Security: bcrypt(12) hashed passwords, opaque session tokens
  (sha256 server-side), role-based admin, rate limiting, magic-byte upload
  validation, files stored outside the web root with traversal-safe reads

 Features

- Auth (register/login/logout), duplicate-email and expired-session handling
- Catalog with categories, search, per-size stock; graceful out-of-stock 409s
- Secure photo uploads (JPEG/PNG/WebP sniffing, 8MB cap, private owner-only serving)
- Try-On Studio: drag-drop/camera upload → garment rail → generate →
  compare slider, landmarks toggle, render history, error recovery hints
  (no person / multiple people / low-res / non-frontal all handled explicitly)
- Cart, wishlist, transactional checkout with conditional stock reservation
- Admin console: create products, edit stock inline, view orders, manage roles
- Self-bootstrapping DB (schema + demo seed on first boot), 27 passing
unit/integration tests (Vitest)

 Demo accounts

- Admin: admin@virtualfit.dev / admin12345
- User: demo@virtualfit.dev / demo12345

Docs: see docs/ARCHITECTURE.md for the full API reference, schema, swap-in
This document will serve as a guide for the development of a real try-on model, security model and roadmap.
