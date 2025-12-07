# Personal Portfolio Website for KS

## Overview

This is a personal portfolio website for KS, designed as a minimalist single-page application with a focus on floral aesthetics and visual elegance. The site serves as a digital business card showcasing KS's interests in flowers and floristry. Built with React and TypeScript on the frontend, Express on the backend, and designed with a mobile-first responsive approach using Tailwind CSS and shadcn/ui components.

## User Preferences

Preferred communication style: Simple, everyday language.

## System Architecture

### Frontend Architecture

**Framework & Build System**
- React 18+ with TypeScript for type-safe component development
- Vite as the build tool and development server, configured with Hot Module Replacement (HMR)
- Single-page application (SPA) architecture using Wouter for client-side routing

**UI Component System**
- shadcn/ui component library in "new-york" style with Radix UI primitives
- Tailwind CSS for utility-first styling with custom design tokens
- Component path aliases configured for clean imports (@/components, @/lib, @/hooks)

**Design System**
- Typography: Playfair Display (serif) for headings, Inter/Work Sans (sans-serif) for body text, loaded via Google Fonts
- Color scheme: Neutral base with pink/rose primary accent (HSL 340 75% 45%), supporting light and dark modes
- Spacing system: Consistent Tailwind units (4, 8, 12, 16, 24) for margins and padding
- Layout: Max-width containers (max-w-4xl), full-width hero sections, centered content alignment
- Visual effects: Hover and active elevation states, soft gradients, organic shapes balanced with clean typography

**State Management**
- TanStack Query (React Query) for server state management and data fetching
- Custom query client with disabled refetching by default (refetchOnWindowFocus: false, staleTime: Infinity)
- Toast notifications using Radix UI Toast primitives

**Routing**
- Wouter for lightweight client-side routing
- Current routes: Home page ("/") and 404 Not Found fallback

### Backend Architecture

**Server Framework**
- Express.js as the HTTP server framework
- Node.js with ESM module system (type: "module")
- Development server runs with tsx for TypeScript execution

**API Design**
- RESTful API structure with routes prefixed under /api
- JSON request/response format with Express JSON middleware
- Raw body capture for webhook handling (stored in req.rawBody)
- Request logging middleware tracking method, path, status, duration, and JSON responses

**Build Process**
- Separate build steps for client (Vite) and server (esbuild)
- Server bundled with esbuild to reduce syscall overhead and improve cold start times
- Allowlist-based bundling: specific dependencies are bundled while others remain external
- Production server runs compiled code from dist/ directory

**Static File Serving**
- Client build output served from dist/public
- Fallback to index.html for client-side routing (SPA pattern)
- Strict file system access controls in development mode

**Storage Layer**
- In-memory storage implementation (MemStorage class) for development
- Interface-based design (IStorage) allowing easy swapping to database implementations
- Basic user CRUD operations defined (getUser, getUserByUsername, createUser)
- UUID-based ID generation for user records

### Data Storage Solutions

**Current Implementation**
- In-memory storage using JavaScript Maps for development/prototyping
- User schema defined with Drizzle ORM conventions

**Database Configuration**
- Drizzle ORM configured for PostgreSQL dialect
- Schema location: shared/schema.ts
- Migrations output: migrations/
- Database connection via DATABASE_URL environment variable
- Neon Serverless driver for PostgreSQL connectivity

**Schema Design**
- Users table with id (UUID primary key), username (unique text), password (text)
- Zod validation schemas generated from Drizzle schemas for runtime validation
- Shared schema between client and server via @shared/* path alias

### External Dependencies

**Database & ORM**
- @neondatabase/serverless: Serverless PostgreSQL driver for Neon database
- drizzle-orm: TypeScript ORM for type-safe database queries
- drizzle-zod: Integration layer generating Zod schemas from Drizzle schemas
- connect-pg-simple: PostgreSQL session store (configured but not actively used with current in-memory storage)

**UI Component Libraries**
- @radix-ui/*: Comprehensive collection of unstyled, accessible UI primitives (accordion, dialog, dropdown, popover, select, tabs, toast, tooltip, etc.)
- embla-carousel-react: Carousel/slider functionality
- cmdk: Command palette component
- lucide-react: Icon library
- recharts: Charting library (via chart.tsx component wrapper)

**Form Management**
- react-hook-form: Form state management and validation
- @hookform/resolvers: Validation resolver integration with Zod

**Styling & CSS**
- tailwindcss: Utility-first CSS framework
- autoprefixer: PostCSS plugin for vendor prefixing
- class-variance-authority: Type-safe variant styling
- clsx & tailwind-merge: Utility for conditional className merging

**Date/Time**
- date-fns: Modern date utility library for formatting and manipulation

**Development Tools**
- @replit/vite-plugin-runtime-error-modal: Runtime error overlay for development
- @replit/vite-plugin-cartographer: Replit-specific development tooling
- @replit/vite-plugin-dev-banner: Development environment banner

**Asset Management**
- Stock images stored in attached_assets/stock_images/ directory
- Vite alias @assets configured for asset imports
- Current images: colorful garden flowers, pink roses, white tulips, purple orchid

**Package Management**
- npm with package-lock.json (lockfile version 3)
- Scripts: dev (development), build (production build), start (production server), check (TypeScript checking), db:push (Drizzle schema push)