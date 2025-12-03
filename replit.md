# Overview

This is a Brazilian Portuguese dark-themed sales landing page application built with React, TypeScript, and Express. The application features a high-conversion sales funnel design with aggressive marketing copy, focused on maximizing conversions through psychological triggers like urgency, scarcity, and social proof. The landing page is designed to be 100% responsive across desktop and mobile devices.

# User Preferences

Preferred communication style: Simple, everyday language.

# System Architecture

## Frontend Architecture

**Framework**: React 18 with TypeScript and Vite for build tooling

**Routing**: Wouter for client-side routing (lightweight alternative to React Router)

**UI Component Library**: Shadcn/ui with Radix UI primitives for accessible, customizable components

**Styling**: 
- Tailwind CSS for utility-first styling
- Custom dark theme with specific brand colors:
  - Background: Pure black (#000000)
  - Accent: Vibrant yellow (#FFD300)
  - CTA: Neon green (#00FF66)
- Responsive design using Tailwind breakpoints

**State Management**: TanStack Query (React Query) for server state and data fetching

**Design System**:
- High-contrast dark aesthetic optimized for conversions
- Aggressive copywriting style with emotional triggers
- Pulsing CTA buttons with custom animations
- Mobile-first responsive approach

## Backend Architecture

**Server Framework**: Express.js with TypeScript

**Development Server**: Vite middleware in development mode for HMR (Hot Module Reload)

**Production Build**: 
- Client bundled with Vite
- Server bundled with esbuild for optimized cold starts
- Static file serving from dist/public

**API Structure**: RESTful endpoints prefixed with `/api` (currently minimal implementation)

**Storage Interface**: Abstract storage interface (IStorage) with in-memory implementation for users
- Designed to be swapped for database implementation
- Currently using Map-based MemStorage

## Data Storage

**Database Setup**: 
- Drizzle ORM configured for PostgreSQL
- Neon serverless PostgreSQL driver
- Schema defined in `shared/schema.ts`
- Migrations managed through Drizzle Kit

**Current Schema**:
- Users table with UUID primary keys
- Username/password authentication structure
- Schema validation using Zod via drizzle-zod

**Note**: Database is configured but not actively used; application currently uses in-memory storage

## Design Patterns

**Monorepo Structure**:
- `/client` - React frontend application
- `/server` - Express backend
- `/shared` - Shared TypeScript types and schemas
- Path aliases configured for clean imports (@/, @shared/, @assets/)

**Component Organization**:
- Reusable UI components in `/client/src/components/ui`
- Landing page specific components in `/client/src/components/landing`
- Example components for development in `/client/src/components/examples`

**Type Safety**:
- Strict TypeScript configuration
- Shared types between frontend and backend
- Zod schemas for runtime validation

## External Dependencies

**UI & Styling**:
- Radix UI - Accessible component primitives
- Tailwind CSS - Utility-first CSS framework
- class-variance-authority - Component variant management
- Embla Carousel - Touch-friendly carousel component

**Data & State**:
- TanStack Query - Server state management
- React Hook Form - Form handling
- Zod - Schema validation
- Drizzle ORM - Type-safe database queries

**Backend Services**:
- Neon (@neondatabase/serverless) - Serverless PostgreSQL database
- Express - Web server framework
- Express Session - Session management (configured for PostgreSQL via connect-pg-simple)

**Build & Development**:
- Vite - Frontend build tool and dev server
- esbuild - Server-side bundling
- tsx - TypeScript execution for development
- Replit plugins - Development tooling for Replit environment

**Assets**:
- Static images stored in `/attached_assets/generated_images/`
- Image imports through Vite alias (@assets/)
- Includes product mockups, avatars, and badge graphics

**Portuguese Language**: All content, copy, and UI text is in Brazilian Portuguese (pt-BR)