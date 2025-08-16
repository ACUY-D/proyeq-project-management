# ProyeQ - Modern Project Management Application

ProyeQ is a modern project management application that combines the best features and user experiences from market leaders like Asana, Monday.com, ClickUp, Jira, and TeamGantt.

## Features

- User Authentication (Email, Google, Microsoft)
- Personalized Dashboard with Customizable Widgets
- Project List/Table View with Customizable Columns
- Gantt Chart View with Advanced Dependency Management
- Kanban Board View with Workflow Visualization
- Workload/Resource Management View
- Real-time Collaboration Features
- Notification System

## Technology Stack

- **Frontend**: React, TypeScript, TailwindCSS
- **Backend**: Supabase (Database, Authentication, Real-time)
- **Deployment**: Vercel/Netlify (Frontend), Supabase (Backend)
- **State Management**: Redux Toolkit/Zustand
- **Build Tool**: Vite

## Development Phases

Following the BMAD METHOD, development is divided into phases:

1. **Phase 1**: Project Setup and Authentication ✅
2. **Phase 2**: Dashboard Implementation
3. **Phase 3**: Project List/Table View
4. **Phase 4**: Gantt View Implementation
5. **Phase 5**: Kanban View Implementation
6. **Phase 6**: Workload View Implementation
7. **Phase 7**: Collaboration Features
8. **Phase 8**: Testing and Optimization

## Getting Started

### Prerequisites

- Node.js (v16 or higher)
- npm or yarn
- Supabase account

### Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/ACUY-D/proyeq-project-management.git
   cd proyeq-project-management
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Set up environment variables:
   Create a `.env` file in the root directory with your Supabase credentials:
   ```env
   VITE_SUPABASE_URL=your_supabase_url
   VITE_SUPABASE_ANON_KEY=your_supabase_anon_key
   ```

4. Run the development server:
   ```bash
   npm run dev
   ```

## Project Structure

```
src/
├── components/     # Reusable UI components
├── contexts/       # React contexts (AuthContext)
├── hooks/          # Custom React hooks
├── pages/          # Page components
├── services/       # API services and Supabase client
├── utils/          # Utility functions
├── assets/         # Static assets
├── App.tsx         # Main App component
└── main.tsx        # Entry point
```

## Documentation

- [Project Brief](PROJECT-BRIEF.md)
- [Product Requirements Document (PRD)](PRD.md)
- [Architecture](ARCHITECTURE.md)
- [Development Plan](docs/development-plan.md)

## Contributing

This project follows the BMAD METHOD for development. Please read the development plan before contributing.

1. Fork the repository
2. Create a feature branch
3. Commit your changes
4. Push to the branch
5. Open a pull request

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.