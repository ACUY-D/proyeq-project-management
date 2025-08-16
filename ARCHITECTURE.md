# ProyeQ System Architecture

## 1. Overview

ProyeQ is a modern web application for project management with real-time collaboration features. The architecture follows a client-server model with a React-based frontend and Supabase backend.

## 2. Technology Stack

### 2.1 Frontend
- **Framework**: React 18 with TypeScript
- **State Management**: Redux Toolkit or Zustand
- **UI Library**: TailwindCSS with custom components
- **Routing**: React Router v6
- **Real-time**: Supabase Real-time Client
- **Charts**: D3.js or Chart.js for data visualization
- **Gantt Charts**: Custom implementation or gantt-lib
- **Drag and Drop**: react-beautiful-dnd or similar
- **Build Tool**: Vite
- **Testing**: Jest and React Testing Library

### 2.2 Backend
- **Platform**: Supabase (PostgreSQL, Authentication, Storage, Functions)
- **Database**: PostgreSQL with custom schema
- **Authentication**: Supabase Auth with email/password and OAuth providers
- **Real-time**: Supabase Real-time API
- **Storage**: Supabase Storage for file uploads
- **Serverless Functions**: Supabase Functions for custom business logic

### 2.3 DevOps
- **Version Control**: Git with GitHub
- **CI/CD**: GitHub Actions
- **Deployment**: Vercel or Netlify for frontend, Supabase for backend
- **Monitoring**: Supabase monitoring and analytics tools

## 3. System Components

### 3.1 Frontend Modules

#### 3.1.1 Authentication Module
- Login/Registration pages
- Social authentication (Google, Microsoft)
- Password recovery flow
- Session management

#### 3.1.2 Dashboard Module
- Customizable widget system
- Drag-and-drop layout
- Personal widgets (My Tasks, Recent Projects, etc.)

#### 3.1.3 Project Management Module
- List/Table view with customizable columns
- Gantt chart view
- Kanban board view
- Workload/resource view

#### 3.1.4 Collaboration Module
- Notifications system
- Real-time updates
- Commenting system

#### 3.1.5 User Management Module
- Profile settings
- Team management
- Role-based permissions

### 3.2 Backend Services

#### 3.2.1 Authentication Service
- User registration and management
- Session handling
- OAuth integration

#### 3.2.2 Project Service
- Project creation and management
- Task management
- View-specific data handling

#### 3.2.3 Collaboration Service
- Real-time updates
- Notification system
- Activity tracking

#### 3.2.4 Resource Management Service
- Workload calculation
- Capacity management
- Assignment tracking

## 4. Database Design

### 4.1 Core Tables

#### 4.1.1 Users
- id (UUID)
- email (string)
- name (string)
- avatar (string/URL)
- created_at (timestamp)
- updated_at (timestamp)

#### 4.1.2 Projects
- id (UUID)
- name (string)
- description (text)
- owner_id (UUID - FK to Users)
- created_at (timestamp)
- updated_at (timestamp)

#### 4.1.3 Tasks
- id (UUID)
- project_id (UUID - FK to Projects)
- name (string)
- description (text)
- assignee_id (UUID - FK to Users)
- status (string)
- priority (string)
- start_date (date)
- due_date (date)
- estimated_hours (number)
- actual_hours (number)
- created_at (timestamp)
- updated_at (timestamp)

#### 4.1.4 Task Dependencies
- id (UUID)
- predecessor_id (UUID - FK to Tasks)
- successor_id (UUID - FK to Tasks)
- dependency_type (string - FS, SS, FF, SF)
- created_at (timestamp)

#### 4.1.5 Workload
- id (UUID)
- user_id (UUID - FK to Users)
- date (date)
- capacity (number)
- assigned_hours (number)
- created_at (timestamp)

### 4.2 Relationships
- Users can own multiple Projects
- Projects contain multiple Tasks
- Tasks can have multiple dependencies
- Users can be assigned to multiple Tasks
- Users have daily Workload records

## 5. API Design

### 5.1 RESTful Endpoints
- `/api/projects` - Project management
- `/api/tasks` - Task management
- `/api/users` - User management
- `/api/workload` - Workload management
- `/api/notifications` - Notification system

### 5.2 Real-time Channels
- `project:{id}` - Project-specific updates
- `task:{id}` - Task-specific updates
- `user:{id}` - User-specific notifications

## 6. Security Considerations

### 6.1 Authentication
- JWT-based authentication
- Role-based access control (RBAC)
- OAuth 2.0 for social logins

### 6.2 Data Protection
- HTTPS encryption for all communications
- Data encryption at rest (handled by Supabase)
- Input validation and sanitization
- Protection against common web vulnerabilities (XSS, CSRF, SQL injection)

## 7. Scalability Considerations

### 7.1 Horizontal Scaling
- Stateless frontend components
- Database read replicas for reporting
- CDN for static assets

### 7.2 Performance Optimization
- Database indexing
- Query optimization
- Caching strategies
- Pagination for large datasets

## 8. Deployment Architecture

### 8.1 Development Environment
- Local development with Supabase CLI
- Storybook for component development
- Jest for unit testing

### 8.2 Production Environment
- Frontend hosted on Vercel/Netlify
- Supabase for backend services
- Monitoring and logging with Supabase tools
- Automated CI/CD with GitHub Actions

## 9. Monitoring and Analytics

### 9.1 Application Monitoring
- Frontend performance metrics
- Error tracking and reporting
- User behavior analytics

### 9.2 Business Metrics
- User engagement tracking
- Feature adoption rates
- Performance benchmarks