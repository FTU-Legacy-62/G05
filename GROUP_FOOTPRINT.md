# Product Name

PortTrack

## Group Code

G05

## Repository

https://github.com/FTU-Legacy-62/G05

## Demo

https://port-track-xi.vercel.app/

## Problem Statement

Portfolio Management courses often require students to apply theoretical concepts through investment simulations. However, traditional spreadsheet-based or loosely managed simulations may not reflect market conditions consistently and provide limited transparency into each student's decision-making process.

Lecturers also need a centralized way to create simulations, supervise trading activity, review portfolios, and evaluate performance. Without such a platform, monitoring transactions and comparing outcomes can be time-consuming and inconsistent.

PortTrack addresses this problem by providing a web-based stock investment simulation. Students trade with virtual capital in an environment that uses external market quote data, while lecturers monitor the process and evaluate results through recorded transactions and portfolio metrics.

## Target Users

### Lecturers

Lecturers need to create and configure simulation rooms, invite students, monitor portfolios and transactions, collect submission links, compare results, and review a room leaderboard.

### Students

Students need a safe environment in which to join a class simulation, search stock symbols, place virtual orders, manage a portfolio, and review their own performance.

The platform is intended for classroom exercises, course projects, and educational investment simulations.

## Current Product Capabilities

1. **Account and access management:** users can register and log in as a `LECTURER` or `STUDENT`. Protected pages and APIs require a valid JWT.
2. **Simulation room management:** lecturers can create public or private rooms and configure the room name, password, initial balance, schedule, and status.
3. **Room participation:** students join using a unique room code. A portfolio with the room's initial virtual balance is created for each participant.
4. **Virtual trading:** students can retrieve stock quotes and submit BUY or SELL orders during supported market sessions.
5. **Trading rules:** the system validates cash, settled share quantity, market status, a 0.15% trading fee, a 0.1% sell tax, and T+2 settlement.
6. **Portfolio management:** the system updates cash, holdings, average cost, market value, NAV, profit/loss, and return.
7. **Historical records:** students can review their transaction history and portfolio summary.
8. **Lecturer monitoring:** room owners can review participants, submissions, all room transactions, aggregate metrics, and a lecturer-only leaderboard.

## Inputs

### User Inputs

- Username, password, and role during registration.
- Room name, type, password, initial balance, schedule, and status.
- Room code and private-room password when joining.
- Stock symbol, BUY/SELL action, and quantity.
- Student submission URL.

### External Market Data

- Recent stock price, open price, volume, trading date, and market status.
- The current implementation retrieves Vietnamese market data through the service configured by `ENTRADE_API_URL`.

### Stored Data

- Users, rooms, portfolios, portfolio items, transactions, and NAV history stored in MySQL.

## Processing Logic

### Authentication and Authorization

- Account and private-room passwords are hashed with BCrypt.
- Successful login returns a JWT used to authenticate later requests.
- Student trading pages and lecturer management pages are protected by role-based rules.

### Joining a Room

- The system checks the room code, room status, and password for private rooms.
- A user can have only one portfolio in each room.
- A successful join creates a portfolio with cash equal to the room's initial balance.

### BUY Orders

1. Normalize and validate the stock symbol and quantity.
2. Retrieve the latest quote and confirm that the market is open.
3. Calculate trade value and a 0.15% trading fee.
4. Reject the order if available cash is insufficient.
5. Deduct cash, add shares, and recalculate average cost including the fee.
6. Record the transaction.

### SELL Orders

1. Confirm that the user owns the requested stock.
2. Exclude shares purchased within the previous two days from the sellable quantity.
3. Reject the order if the settled quantity is insufficient.
4. Calculate a 0.15% trading fee and a 0.1% sell tax.
5. Add the net proceeds to cash and reduce or remove the holding.
6. Record the transaction.

### Portfolio and Ranking Calculations

- Holdings value is calculated from quantity and current market price.
- Total portfolio value, or NAV, equals cash plus holdings value.
- Profit/loss and return are calculated relative to the room's initial balance and holding cost.
- Room-level results are aggregated for lecturer dashboards and rankings.
- Database transactions and version fields help prevent inconsistent concurrent updates.

## User Flow

### Lecturer Flow

1. Open PortTrack and register or log in as a lecturer.
2. Create a simulation room and configure its settings.
3. Share the room code with students.
4. Monitor participation and trading activity.
5. Review player portfolios, submission links, transactions, and rankings.
6. Use the recorded results to evaluate performance.

### Student Flow

1. Register or log in as a student.
2. Join a room using its code and password if required.
3. Review the room schedule, available cash, and trading guidance.
4. Search a stock symbol and enter a BUY or SELL order.
5. The system validates and processes the order.
6. Review personal holdings, NAV, profit/loss, summary, and transaction history.
7. Submit or update the required assignment URL.

Students do not have access to other participants' leaderboard results; those results are reserved for the lecturer.

## Outputs

### Student Outputs

- Cash balance and available buying power.
- Holdings, average cost, market price, and market value.
- Total portfolio value, profit/loss, and return percentage.
- BUY/SELL execution results and validation messages.
- Transaction history and personal portfolio summary.
- Submission URL status.

### Lecturer Outputs

- Room configuration and aggregate dashboard metrics.
- Participant list and individual portfolio performance.
- Room-wide transaction history.
- Submission links.
- Lecturer-only leaderboard and comparative results.

## Key Design Decisions

### Use External Market Data

The team considered predefined simulation prices but chose external market quote data to make the activity more realistic. The service is isolated behind a backend interface so the source can be changed without redesigning the frontend.

### Separate Frontend and Backend Responsibilities

React and TypeScript provide the user interface, while Spring Boot enforces authentication, trading rules, financial calculations, and persistence. Critical validation is performed on the backend rather than relying on the interface.

### Separate Lecturer and Student Experiences

Students focus on trading and reviewing their own portfolios. Lecturers use separate management pages for room configuration, monitoring, transactions, submissions, and rankings.

### Prioritize Core Educational Features

The team prioritized room management, virtual trading, portfolio tracking, transaction records, and lecturer evaluation. Intraday charts, technical indicators, benchmark analysis, and advanced risk tools were postponed to keep the product stable and demonstrable.

### Protect Deployment Secrets

Database credentials, JWT secrets, allowed frontend origins, and external service URLs are supplied through environment variables. The database schema is managed with `CREATE_TABLE.TXT`.

## Project Strengths

- A complete classroom flow from room creation and participation to trading and evaluation.
- Clear separation between student and lecturer tasks.
- A consistent interface that keeps cash, NAV, holdings, and performance visible.
- Backend enforcement of cash, settlement, fee, tax, market-hours, and role rules.
- Centralized frontend service functions for room, trading, portfolio, and monitoring APIs.
- Lecturer dashboards that consolidate participants, transactions, submissions, and rankings.
- Security controls including BCrypt, JWT authentication, protected routes, and environment-based secrets.
- An online demo and documented local/deployment setup.

## Current Limitations

- No technical analysis, company fundamentals, valuation ratios, or market news.
- No benchmark comparison, diversification analysis, risk metrics, or performance attribution.
- No real-time intraday chart or advanced market visualization.
- Market quotes depend on the availability and quality of an external data service.
- The current market-hours logic does not model every exchange holiday or order type.
- The system needs broader automated testing for trading rules and end-to-end user flows.
- Additional optimization would be required for large numbers of concurrent rooms and users.
- PortTrack is an educational simulation and does not cover every rule of a real brokerage platform.

## Lessons Learned

### Technical Lessons

- Translating educational requirements into clear inputs, processing rules, and outputs.
- Designing a relational model for users, rooms, portfolios, holdings, transactions, and NAV.
- Building and integrating React, Spring Boot, MySQL, security, and external market data.
- Implementing financial rules involving fees, taxes, average cost, T+2 settlement, and return.
- Testing integration points between frontend interfaces, backend APIs, and stored data.

### Team and Product Lessons

- Assigning work based on each member's strengths.
- Defining shared data structures and API expectations early.
- Tracking progress and integration issues across frontend, backend, and database work.
- Prioritizing a stable core product over too many unfinished features.
- Preparing evidence and documentation while development is still in progress.

## Recommendations for Future Development

### Add Fundamental and Market Information

Integrate company profiles, summarized financial statements, valuation indicators such as P/E, ROE, and EPS, dividend information, and relevant market news.

### Personalize Learning Support

Analyze trading behavior and provide educational feedback on excessive trading, concentration risk, weak diversification, or FOMO-like behavior.

### Expand Portfolio Analytics

Add benchmark comparisons, risk metrics, diversification analysis, and performance attribution.

### Improve Reliability and Testing

Add automated tests for trading rules, market schedules, permissions, concurrency, and complete lecturer/student workflows. A fallback data strategy should also be considered for external service outages.

### Explore a Path Beyond Simulation

Future teams may research educational partnerships or optional brokerage integrations. Any transition toward real investing would require strong security, compliance, risk disclosures, and explicit user safeguards.
