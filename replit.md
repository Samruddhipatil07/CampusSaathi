# CampusSaathi - Academic Resource Sharing Platform

## Overview

CampusSaathi is a full-stack academic resource sharing platform built for educational institutions. It enables students to share notes, download previous year papers, participate in discussions, and connect with peers. The platform also provides administrative tools for content moderation and user management.

## System Architecture

### Frontend Architecture
- **Framework**: React 18 with TypeScript
- **Build Tool**: Vite with custom configuration
- **Styling**: Tailwind CSS with shadcn/ui component library
- **State Management**: TanStack Query (React Query) for server state
- **Routing**: Wouter for client-side routing
- **Form Handling**: React Hook Form with Zod validation
- **UI Components**: Radix UI primitives with custom styling

### Backend Architecture
- **Runtime**: Node.js with Express.js
- **Language**: TypeScript with ES modules
- **Database**: PostgreSQL with Drizzle ORM
- **Authentication**: Replit OpenID Connect (OIDC)
- **Session Management**: Express sessions with PostgreSQL store
- **Real-time Communication**: WebSocket integration
- **File Handling**: Multer for file uploads

### Database Design
- **ORM**: Drizzle with PostgreSQL dialect
- **Schema Location**: `shared/schema.ts` for type sharing
- **Migration Management**: Drizzle Kit for schema migrations
- **Connection**: Neon Database serverless connection

## Key Components

### Authentication System
- **Provider**: Replit OIDC integration
- **Session Storage**: PostgreSQL-backed sessions
- **User Management**: Automatic user creation/update on login
- **Role-Based Access**: Student and admin roles

### File Management
- **Upload System**: Multer-based file handling with validation
- **Content Approval**: Admin review workflow for uploaded content
- **File Types**: PDF, Word documents, PowerPoint presentations
- **Storage**: Local file system with configurable limits
- **Download Tracking**: Analytics for file access patterns

### Content Organization
- **Categories**: Notes, papers, assignments, materials
- **Metadata**: Subject, semester, department tagging
- **Status Management**: Pending, approved, rejected workflow
- **Search & Filter**: Category and metadata-based filtering

### Communication Features
- **Real-time Chat**: WebSocket-based messaging system
- **Forum System**: Discussion threads with replies
- **Announcements**: Admin-to-student communication
- **Email Integration**: SendGrid for notifications

## Data Flow

1. **User Authentication**: OIDC flow with Replit → Session creation → User profile management
2. **File Upload**: Client upload → Server validation → Admin approval queue → Public availability
3. **Content Discovery**: Database queries → Filtering/search → Content cards → Download tracking
4. **Real-time Communication**: WebSocket connections → Message broadcasting → Chat interface
5. **Admin Operations**: Content moderation → User management → System analytics

## External Dependencies

### Core Dependencies
- **@neondatabase/serverless**: PostgreSQL database connection
- **@sendgrid/mail**: Email service integration
- **@radix-ui/***: UI component primitives
- **@tanstack/react-query**: Server state management
- **drizzle-orm**: Database ORM and query builder

### Authentication & Security
- **openid-client**: OIDC authentication handling
- **passport**: Authentication middleware
- **express-session**: Session management
- **connect-pg-simple**: PostgreSQL session store

### File & Media Processing
- **multer**: File upload handling
- **memoizee**: Function result caching

### Development Tools
- **vite**: Frontend build tool
- **tsx**: TypeScript execution
- **esbuild**: Production bundling
- **@replit/vite-plugin-***: Replit-specific tooling

## Deployment Strategy

### Development Environment
- **Server**: `npm run dev` - Development server with hot reload
- **Database**: Drizzle push for schema updates
- **Vite Integration**: Middleware mode for development

### Production Build
- **Frontend**: Vite build to `dist/public`
- **Backend**: ESBuild bundling to `dist/index.js`
- **Database**: Migration-based schema management
- **Environment**: NODE_ENV-based configuration

### Configuration Requirements
- **DATABASE_URL**: PostgreSQL connection string
- **SESSION_SECRET**: Session encryption key
- **REPL_ID**: Replit environment identifier
- **ISSUER_URL**: OIDC provider URL
- **REPLIT_DOMAINS**: Allowed domains for OIDC

## Changelog

```
Changelog:
- July 06, 2025. Initial setup
```

## User Preferences

```
Preferred communication style: Simple, everyday language.
```