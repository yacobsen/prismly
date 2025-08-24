# Overview

This is a modern web application called "Prismly" - an expert consultation platform that connects clients with verified professionals across various fields like finance, career development, real estate, and self-improvement. The platform enables users to browse expert profiles, book consultations, and manage their appointments through a polished, responsive interface.

The application is built as a full-stack TypeScript solution with a React frontend and Express.js backend, featuring real-time payments through Stripe integration, user authentication via Replit's OIDC system, and a PostgreSQL database for persistent data storage.

# User Preferences

Preferred communication style: Simple, everyday language.

# System Architecture

## Frontend Architecture
The client-side application is built with React 18 and TypeScript, utilizing Vite as the build tool and development server. The UI is constructed with shadcn/ui components built on top of Radix UI primitives, providing accessible and customizable interface elements. Styling is handled through Tailwind CSS with a custom dark theme and color system.

State management relies on TanStack Query (React Query) for server state synchronization and caching, while local component state is managed with React hooks. The routing system uses Wouter for lightweight client-side navigation.

## Backend Architecture
The server runs on Express.js with TypeScript, following a RESTful API design pattern. The application uses a layered architecture with clear separation between route handlers, business logic in the storage layer, and database operations.

Authentication is handled through Replit's OpenID Connect (OIDC) system with Passport.js, providing secure user sessions stored in PostgreSQL. The server implements comprehensive error handling and request/response logging middleware.

## Data Storage Solution
PostgreSQL serves as the primary database, accessed through Drizzle ORM for type-safe database operations. The database schema includes tables for users, expert profiles, consultations, reviews, availability, and session storage.

The schema supports a two-tier user system (clients and experts) with expert profile approval workflows. Database migrations are managed through Drizzle Kit, ensuring schema versioning and deployment consistency.

## Payment Processing
Stripe integration handles all payment operations, including payment intent creation, processing, and webhook handling for payment status updates. The system calculates consultation fees based on hourly rates and duration, with a 15% platform fee structure.

## External Dependencies
- **Neon Database**: PostgreSQL hosting service for production database
- **Stripe**: Payment processing and subscription management
- **Replit Auth**: OpenID Connect authentication provider
- **shadcn/ui**: Component library built on Radix UI
- **TanStack Query**: Server state management and caching
- **Drizzle ORM**: Type-safe database toolkit
- **Tailwind CSS**: Utility-first CSS framework
- **Vite**: Frontend build tool and development server

The application architecture prioritizes type safety, developer experience, and maintainability while providing a modern, responsive user interface for both clients and experts.