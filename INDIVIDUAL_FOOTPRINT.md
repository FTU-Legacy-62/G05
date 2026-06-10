# Individual Footprint

## Member 1: Nguyen Anh Thu - 2312380036

### Role in the Project

Team Leader and Database Coordinator. I monitored team progress, coordinated integration, designed and reviewed the database structure and ERD, and helped prepare project documentation and final delivery materials.

### Personal Signature in the Product

My clearest contribution is the shared data foundation connecting users, rooms, portfolios, holdings, transactions, and NAV history. This structure allows the backend and frontend to use consistent concepts and relationships across all major features.

### Actual Work Completed

- Analyzed the overall business workflow and data requirements.
- Designed and refined the ERD, keys, constraints, and table relationships.
- Compared `CREATE_TABLE.TXT` with backend entities and repositories.
- Reviewed MySQL table relationships and data integrity.
- Coordinated task allocation, progress monitoring, integration issues, and final delivery.
- Updated project documentation and setup information.

### Files, Features, Data, Logic, Interface, Documents, or Demo Parts Contributed

- [`CREATE_TABLE.TXT`](CREATE_TABLE.TXT)
- [`Cấu trúc dữ liệu.txt`](Cấu%20trúc%20dữ%20liệu.txt)
- [`entity`](porttrack-backend/src/main/java/com/musketeers/porttrack/entity)
- [`repository`](porttrack-backend/src/main/java/com/musketeers/porttrack/repository)
- [`application.properties`](porttrack-backend/src/main/resources/application.properties)
- [Project README](README.md) and submission documentation.

### Evidence of Contribution

- Database schema, data-structure notes, entity classes, and repository classes in the repository.
- [Group task allocation and progress records](https://docs.google.com/spreadsheets/d/1mbhvXPXtda0L6wJDsmI9R6S2SAAV-78kTig2aXuPI5w/edit?gid=1809229340#gid=1809229340).
- Repository history: https://github.com/FTU-Legacy-62/G05/commits

### Connection to the Final Product

The database is the foundation for authentication, rooms, trading, portfolio calculations, transaction history, and ranking. Team coordination also helped ensure that separately developed components were integrated into one demonstrable product.

### Personal Learning

I learned how to translate business requirements into a relational data model, verify consistency between schema and code, organize technical work, and use AI and online resources as learning aids while still checking the underlying logic.

### Difficulties and Solutions

The main challenge was limited initial programming experience combined with the need to understand the full system. I addressed this by breaking the product into smaller workflows, studying the relevant code and data structures, asking targeted questions, and coordinating with members responsible for each module.

### Message for Future Students

Establish the data model and end-to-end workflow early. Use AI as a learning and productivity tool, but verify every suggestion against the product requirements and source code.

## Member 2: To Ha Vy - 2313380039

### Role in the Project

Backend contributor responsible for authentication, JWT security, room management, and market-data input support. I also helped connect data preparation with the trading and portfolio modules.

### Personal Signature in the Product

My contribution is visible in the platform's protected entry flow and room structure. Users can register, log in securely, create or join rooms, and receive a room-specific portfolio before using the trading features.

### Actual Work Completed

- Supported stock-market data research, input preparation, and validation.
- Developed or supported registration and login APIs.
- Implemented JWT-based authentication and protected API access.
- Implemented room creation, private-room password checks, room-code joining, and room listings.
- Connected successful room participation with portfolio creation.
- Coordinated market-data requirements with trading, validation, testing, and frontend work.

### Files, Features, Data, Logic, Interface, Documents, or Demo Parts Contributed

- [`AuthController.java`](porttrack-backend/src/main/java/com/musketeers/porttrack/controller/AuthController.java)
- [`AuthService.java`](porttrack-backend/src/main/java/com/musketeers/porttrack/service/AuthService.java)
- [`AuthServiceImpl.java`](porttrack-backend/src/main/java/com/musketeers/porttrack/service/impl/AuthServiceImpl.java)
- [`security`](porttrack-backend/src/main/java/com/musketeers/porttrack/security)
- [`RoomController.java`](porttrack-backend/src/main/java/com/musketeers/porttrack/controller/RoomController.java)
- [`RoomServiceImpl.java`](porttrack-backend/src/main/java/com/musketeers/porttrack/service/impl/RoomServiceImpl.java)
- Authentication and room request/response DTOs.

### Evidence of Contribution

- The authentication, security, room-service, and DTO files listed above.
- Demonstrable flows: registration, login, JWT-protected access, room creation, and room joining.

### Connection to the Final Product

Authentication controls access to the entire platform. Room management creates the educational context in which virtual capital, schedules, participants, portfolios, transactions, and evaluation results are organized.

### Personal Learning

I learned how financial data must be selected, validated, and connected to product logic. I also gained practical understanding of backend authentication, JWT tokens, password hashing, protected APIs, and room-based workflows.

### Difficulties and Solutions

The main difficulties were selecting relevant fields from external financial data and understanding the complete JWT flow. I handled these by focusing on the fields required by the simulation and breaking authentication into login, token generation, storage, transmission, and backend validation stages.

### Message for Future Students

Understand the complete workflow before implementing individual endpoints. When using an external market API, validate relevance and quality rather than assuming that every returned field is useful.

## Member 3: Pham Quoc Thai - 2313380033

### Role in the Project

Backend developer responsible for trading logic, portfolio management, transaction history, financial calculations, and stock-price retrieval.

### Personal Signature in the Product

I built the core business logic that turns a BUY or SELL request into consistent changes in cash, holdings, average cost, fees, taxes, settlement availability, transaction records, and portfolio performance.

### Actual Work Completed

- Developed BUY and SELL APIs.
- Validated cash, stock ownership, settled quantity, quantity input, and market status.
- Implemented the 0.15% trading fee, 0.1% sell tax, and T+2 sell restriction.
- Updated cash balances, holdings, quantities, and average cost.
- Recorded transaction history.
- Calculated portfolio value, profit/loss, return, order totals, and summaries.
- Implemented stock quote retrieval, caching, price scaling, and market-hours checks.
- Supported frontend integration and API testing.

### Files, Features, Data, Logic, Interface, Documents, or Demo Parts Contributed

- [`TradeController.java`](porttrack-backend/src/main/java/com/musketeers/porttrack/controller/TradeController.java)
- [`TradeServiceImpl.java`](porttrack-backend/src/main/java/com/musketeers/porttrack/service/impl/TradeServiceImpl.java)
- [`PortfolioController.java`](porttrack-backend/src/main/java/com/musketeers/porttrack/controller/PortfolioController.java)
- [`PortfolioViewServiceImpl.java`](porttrack-backend/src/main/java/com/musketeers/porttrack/service/impl/PortfolioViewServiceImpl.java)
- [`StockController.java`](porttrack-backend/src/main/java/com/musketeers/porttrack/controller/StockController.java)
- [`StockPriceServiceImpl.java`](porttrack-backend/src/main/java/com/musketeers/porttrack/service/impl/StockPriceServiceImpl.java)
- [`TradeRequest.java`](porttrack-backend/src/main/java/com/musketeers/porttrack/dto/request/TradeRequest.java)
- Portfolio, portfolio-item, transaction, and related repository classes.

### Evidence of Contribution

- The controller, service, entity, DTO, and repository files listed above.
- [Detailed backend code notes](https://docs.google.com/spreadsheets/d/1GUS4Kxu9n38IXAwiywzaj5YdHf-_jhvi6FisKWOPbh4/edit?usp=sharing).
- Demonstrable BUY, SELL, insufficient-cash, insufficient-settled-shares, and market-closed scenarios.

### Connection to the Final Product

This contribution is the core of the simulation. Without accurate trading and portfolio logic, the dashboard, profit/loss figures, transaction history, and lecturer rankings would not be meaningful.

### Personal Learning

I gained practical experience with layered backend architecture, REST APIs, transaction processing, portfolio systems, financial calculations, external service integration, debugging, and frontend-backend coordination.

### Difficulties and Solutions

The main challenge was updating several dependent values consistently after each transaction and covering edge cases. I redesigned the transaction flow, tested normal and invalid scenarios, and compared calculated results with expected outputs.

### Message for Future Students

Understand the relationship between transactions, holdings, settlement, and financial calculations before adding features. Test edge cases carefully and keep business logic separate from controllers.

## Member 4: Pham Linh Nhan - 2312380024

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

## Member 5: Dang Ngoc Linh - 2312380018

### Role in the Project

Frontend developer and UI integrator responsible for the student room experience, including room layout, trading, portfolio, summary, and transaction history.

### Personal Signature in the Product

I transformed backend trading and portfolio data into the interfaces students use most frequently. My work connects user actions to API requests and converts financial results into understandable dashboards and tables.

### Actual Work Completed

- Centralized room, quote, trade, portfolio, summary, transaction, and owner API calls in `roomService.ts`.
- Built the shared student room layout and navigation.
- Built the Trade Hub for quote lookup and BUY/SELL submission.
- Built the portfolio dashboard and holdings table.
- Built transaction search and BUY/SELL filtering.
- Built the summary page for returns, profit/loss, order counts, and recent transactions.
- Supported UI/UX design, report design, integration review, and usability improvements.

### Files, Features, Data, Logic, Interface, Documents, or Demo Parts Contributed

- [`roomService.ts`](porttrack-frontend/src/services/roomService.ts)
- [`RoomLayout.tsx`](porttrack-frontend/src/pages/RoomPage/RoomLayout.tsx)
- [`RoomHomePage.tsx`](porttrack-frontend/src/pages/RoomPage/RoomHomePage.tsx)
- [`RoomTradePage.tsx`](porttrack-frontend/src/pages/RoomPage/RoomTradePage.tsx)
- [`PortfolioPage.tsx`](porttrack-frontend/src/pages/RoomPage/PortfolioPage.tsx)
- [`TransactionHistoryPage.tsx`](porttrack-frontend/src/pages/RoomPage/TransactionHistoryPage.tsx)
- [`SummaryPage.tsx`](porttrack-frontend/src/pages/RoomPage/SummaryPage.tsx)
- [`Header.tsx`](porttrack-frontend/src/components/layout/Header.tsx)

### Evidence of Contribution

- The service and page files listed above.
- [Group work allocation and meeting notes](https://docs.google.com/spreadsheets/d/1mbhvXPXtda0L6wJDsmI9R6S2SAAV-78kTig2aXuPI5w/edit?gid=1809229340#gid=1809229340).
- [Initial UI/UX design](https://drive.google.com/file/d/16oBTgKzHmsGL29Y3BfRh0GvL2ue3dN8l/view?usp=drive_link).
- [Midterm report design](https://drive.google.com/file/d/1pdWYNDJbcB7mr1BHPefRXDaLORZxTyGa/view?usp=drive_link).
- Demonstrable student room, trading, portfolio, summary, and history flows.

### Connection to the Final Product

This work is the bridge between backend data and student interaction:

`Student -> Room UI -> roomService -> Backend API -> Database -> Response -> UI`

It allows students to execute the complete simulation workflow and understand complex financial data through a consistent interface.

### Personal Learning

I learned React component design, TypeScript interfaces, routing, shared state, API communication, financial-data presentation, and the importance of coordination between frontend and backend teams.

### Difficulties and Solutions

The main challenge was maintaining consistent room data across several pages while presenting each dataset clearly. I centralized API access in `roomService`, reused room context through the shared layout, reviewed feature logic with teammates, and tested the interface against product requirements.

### Message for Future Students

Plan the interface around the user's workflow, not only visual appearance. Future versions should connect price information with company fundamentals and market context so students can make more informed decisions.
