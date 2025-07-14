# AI Query Comparison Platform

## Overview

AiiInOne is a mobile-optimized web application that aggregates responses from three AI platforms (Gemini, Cohere, and Llama) to provide users with combined AI answers. The main page shows a synthesized response from all three bots, with an option to view individual "Bot Analysis" responses. The application is built with a modern tech stack featuring a React frontend with TypeScript, an Express.js backend, and in-memory storage for fast development.

## User Preferences

Preferred communication style: Simple, everyday language.

## Recent Changes (January 2025)

- ✓ Implemented mobile-optimized responsive design with better mobile layouts
- ✓ Added proper API key configuration with Gemini API integration
- ✓ Created combined AI response synthesis functionality
- ✓ Built "Bot Analysis" view showing individual responses from each platform
- ✓ Optimized component layouts for mobile-first experience
- ✓ Fixed TypeScript errors and improved type safety
- ✓ Added proper error handling and loading states
- ✓ Changed app name from "AiiInOne" to "AllInOne" throughout the application
- ✓ Implemented beautiful gradient backgrounds and glass-effect UI design
- ✓ Added modern CSS animations (float, pulse-glow) for enhanced user experience
- ✓ Applied glassmorphism design with backdrop blur effects
- ✓ Enhanced buttons with gradient backgrounds and hover animations
- ✓ Updated all components to use modern-card styling with hover effects
- ✓ Replaced API Configuration section with streamlined API key prompt
- ✓ Created full-screen API key setup that requires all three keys upfront
- ✓ Simplified user flow - keys are collected at startup instead of optional configuration
- ✓ Migrated from database API key storage to environment variables (Replit Secrets)
- ✓ Automated API key setup - no manual copy-paste required for users
- ✓ Enhanced Llama API debugging with provider detection and multi-endpoint support

## System Architecture

### Frontend Architecture
- **Framework**: React with TypeScript
- **Build Tool**: Vite for development and build processes
- **Styling**: Tailwind CSS with shadcn/ui component library
- **State Management**: TanStack Query (React Query) for server state management
- **Routing**: Wouter for lightweight client-side routing
- **Form Handling**: React Hook Form with Zod validation

### Backend Architecture
- **Framework**: Express.js with TypeScript
- **Database**: PostgreSQL with Drizzle ORM for type-safe database operations
- **Session Management**: Session-based authentication (using connect-pg-simple)
- **API Structure**: RESTful endpoints for API key management and query processing
- **AI Integration**: Direct integration with Google Gemini API, with placeholder support for Cohere and Llama

### Database Schema
- **users**: User authentication and profile data
- **api_keys**: Encrypted storage of user API keys for AI services
- **queries**: Query history with individual and combined AI responses

## Key Components

### Frontend Components
- **QueryInput**: Main interface for submitting questions with character limits
- **ResponseDisplay**: Shows AI responses in combined or individual view modes
- **LoadingState**: Animated loading indicators during query processing
- **ApiKeySetup**: Secure API key configuration interface

### Backend Services
- **AIService**: Handles communication with AI platforms
- **Storage**: Abstracted data layer with in-memory implementation (ready for PostgreSQL)
- **Route Handlers**: Express middleware for API endpoints

### Database Layer
- **Drizzle ORM**: Type-safe database operations with PostgreSQL
- **Migration System**: Database schema versioning and updates
- **Connection**: Neon Database serverless PostgreSQL connection

## Data Flow

1. **API Key Setup**: Users configure their AI service API keys through a secure interface
2. **Query Submission**: Users submit questions through the main interface
3. **Parallel Processing**: Backend simultaneously queries multiple AI services
4. **Response Aggregation**: Individual responses are combined into a unified result
5. **Storage**: Query and response data is persisted to PostgreSQL
6. **Display**: Results are presented in both individual and combined view modes

## External Dependencies

### AI Services
- **Google Gemini**: Primary AI service integration using official SDK
- **Cohere**: Placeholder integration (API key collection implemented)
- **Llama**: Placeholder integration (API key collection implemented)

### Third-Party Libraries
- **UI Components**: Extensive shadcn/ui component library based on Radix UI
- **Database**: Neon Database for serverless PostgreSQL
- **Authentication**: Session-based with PostgreSQL session store
- **Validation**: Zod for runtime type validation

## Deployment Strategy

### Development
- **Hot Reload**: Vite development server with HMR
- **Database**: Environment-based DATABASE_URL configuration
- **Scripts**: Separate dev, build, and production scripts

### Production
- **Build Process**: Vite builds frontend to dist/public, esbuild bundles backend
- **Database Migrations**: Drizzle Kit for schema management
- **Environment Variables**: DATABASE_URL and AI API keys via environment

### Configuration
- **TypeScript**: Strict mode with path aliases for clean imports
- **ESLint/Prettier**: Code quality and formatting standards
- **PostCSS**: Tailwind CSS processing pipeline

The application is designed to be scalable and maintainable, with clear separation of concerns between frontend and backend, type safety throughout, and a flexible architecture that can easily accommodate additional AI services or features.