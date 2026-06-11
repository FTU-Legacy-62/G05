# Individual footprint 

## Member: Pham Linh Nhan - 2312380024

### Role in the Project

Frontend developer responsible for authentication interfaces, onboarding, dashboard, room creation/joining, application routing, and lecturer room-monitoring pages.

### Personal Signature in the Product

I built the main entry and management flow. Every user interacts with this work when moving from the landing page to registration/login, the dashboard, room participation, or lecturer monitoring.

### Actual Work Completed

- Developed the landing, login, and registration pages.
- Integrated authentication APIs, token storage, validation, and redirects.
- Built the dashboard for owned and joined rooms.
- Integrated create-room and join-room modals.
- Configured protected routes and role-based navigation.
- Developed or integrated lecturer pages for dashboard metrics, players, transactions, and leaderboard.
- Tested authentication, room management, monitoring, navigation, and error states.

### Files, Features, Data, Logic, Interface, Documents, or Demo Parts Contributed

- [`App.tsx`](porttrack-frontend/src/App.tsx)
- [`api.ts`](porttrack-frontend/src/services/api.ts)
- [`authService.ts`](porttrack-frontend/src/services/authService.ts)
- [`auth.ts`](porttrack-frontend/src/utils/auth.ts)
- [`LandingPage`](porttrack-frontend/src/pages/LandingPage)
- [`LoginPage`](porttrack-frontend/src/pages/LoginPage)
- [`RegisterPage`](porttrack-frontend/src/pages/RegisterPage)
- [`DashboardPage`](porttrack-frontend/src/pages/DashboardPage)
- [`dashboard components`](porttrack-frontend/src/components/dashboard)
- [`auth components`](porttrack-frontend/src/components/auth)
- [`OwnerRoomPage`](porttrack-frontend/src/pages/OwnerRoomPage)

### Evidence of Contribution

- The pages, components, services, and utilities listed above.
- Demonstrable registration, login, token persistence, create-room, join-room, protected-route, and lecturer-monitoring flows.

### Connection to the Final Product

These features form the entry and management layer of PortTrack. Authentication provides secure access, the dashboard connects users to rooms, and the lecturer pages turn the simulator into a classroom monitoring and evaluation tool.

### Personal Learning

I learned React, TypeScript, React Router, API integration, session management, protected routes, dashboard design, data tables, error handling, and team integration practices.

### Difficulties and Solutions

The frontend and backend data contracts changed during development, and authentication state had to remain correct after reloads and token expiration. I addressed this through regular backend communication, centralized API/session utilities, repeated integration testing, and role-aware routing.

### Message for Future Students

Agree on API contracts and coding conventions early. Understand the project structure, commit frequently, document changes, and test complete user flows before merging.
