# Product name
PortTrack

## Group code
G05

## Link repo
Link Repo: https://github.com/FTU-Legacy-62/G05

## Link demo
Demo link: https://port-track-xi.vercel.app/

## Problem statement
Students need a realistic environment to practice investment and portfolio management, while lecturers need a tool to monitor and assess their performance. PortTrack provides a centralized platform that supports both learning and evaluation.

## Target users
- Portfolio Management lecturers
- Students learning investment and portfolio management
The platform is used during investment simulation activities and classroom projects.

## Current product capabilities
PortTrack currently provides the core functionalities required for educational investment simulations.
1. Class and User Management
Lecturers can create simulation rooms and manage participating student groups. Students can register, log in, and join designated rooms.

2. Virtual Trading
Students can search for stock symbols, review market information, and place buy or sell orders using allocated virtual capital.

3. Portfolio Management
The system automatically updates portfolio holdings after each transaction and maintains information such as:
- Cash balance
- Stock holdings
- Net Asset Value (NAV)
- Portfolio performance

4. Transaction Tracking
All transactions are recorded and stored to ensure transparency and allow lecturers to review investment decisions throughout the simulation period.

5. Performance Monitoring
Lecturers can monitor:
- Portfolio values
- Profit and loss performance
- Return percentages
- Group rankings
These features enable efficient supervision and objective evaluation of student performance.

## Input
1. User Inputs
Account registration and login information
Class and room configuration data
Buy and sell orders submitted by students

2. Market Data
Real-time stock market prices and related financial data retrieved from external sources

## Processing Logic
1. Buy Orders
When a buy order is submitted, the system verifies whether the user has sufficient cash balance to complete the transaction.

2. Sell Orders
When a sell order is submitted, the system checks whether the user owns enough shares to execute the transaction.

3. Portfolio Updates
- Once a transaction is validated:
    - Cash balances are updated.
    - Holdings are adjusted.
    - Portfolio values are recalculated.
    - Performance Calculations
- The system continuously calculates key performance indicators, including:
    - Net Asset Value (NAV)
    - Realized Profit/Loss
    - Unrealized Profit/Loss
    - Investment Return
    - Data Recording and Ranking
Every transaction is stored in the transaction history database. Portfolio performance is then aggregated to generate rankings and performance reports for lecturers.


## User Flow
1. A lecturer accesses the platform.
2. The lecturer registers, logs in, and creates a simulation room.
3. Students register, log in, and join the room.
4. Students execute virtual stock transactions.
5. The system validates and processes transactions.
6. Portfolio data and performance metrics are updated automatically.
7. Lecturers monitor results and evaluate student performance through dashboards and rankings.


## Outputs
- Portfolio Metrics
    - Net Asset Value (NAV)
    - Cash balance
    - Portfolio holdings
    - Realized and unrealized profit/loss
    - Investment return
- Historical Records
    - Transaction history
    - Portfolio performance history
- Performance Reports
    - Group rankings
    - Comparative performance summaries
    - Investment evaluation results
    - The information is presented through tables, dashboards, and visual performance indicators.


## Key Design Decisions
- Real-Time Market Data Integration
Initially, the team considered using predefined simulation datasets. However, after successfully integrating real-time market data, we adopted this approach because it provides a more realistic and engaging learning experience.
- Focus on Core Functionality
The team originally planned to implement real-time stock charts and advanced market indicators. However, these features required significant processing resources and data management capabilities.
To ensure system stability and maintain development focus, the team prioritized essential trading and portfolio management features and postponed advanced analytics for future development.


## Project Strengths
The team believes that the strongest aspect of the project is its user interface design and overall usability.
The platform is designed to provide a clear and intuitive user experience, enabling users to quickly understand and navigate its functionalities.
- For students:
Trading-related information is displayed prominently.
Portfolio status and buying power are always visible.
The workflow follows a logical investment process.
- For lecturers:
Performance metrics are centralized.
Rankings and portfolio summaries are easy to access.
Student evaluation can be conducted efficiently.
These design choices significantly improve usability and support the educational objectives of the platform.


## Current Limitations
Despite successfully delivering the core features, several limitations remain.
- Limited Investment Analytics
The platform currently focuses on portfolio management and trading simulation. Advanced analytical tools such as: Technical analysis, Benchmark comparison, Portfolio risk assessment,... have not yet been implemented.
- Limited Market Visualization
Real-time intraday stock charts and advanced market visualizations are not currently available due to data volume and performance constraints.
- Scalability Considerations
Additional optimization may be required to support larger datasets and a greater number of concurrent users in future versions.


## Lessons Learned
This project provided valuable technical and professional learning experiences.
- From a technical perspective, the team gained experience in:
Full-stack web development
Database design and management
API integration
Financial data processing
- From a project management perspective, the team improved its ability to:
Define project requirements
Allocate tasks effectively
Coordinate teamwork
Manage project timelines
Solve implementation challenges collaboratively

The project also strengthened our understanding of how technology can be applied to support financial education and experiential learning.


## Recommendations for Future Development
Future teams may consider extending PortTrack in several ways.
- Integrate Fundamental Analysis Data
Include company profiles, financial statements, valuation ratios (P/E, ROE, EPS), dividend information, and market news to support more informed investment decisions.
- Enhance Learning Support
Develop personalized feedback mechanisms that analyze trading behavior and identify patterns such as excessive trading, concentration risk, or emotional investing tendencies.
- Expand Analytical Features
Introduce benchmark comparisons, risk metrics, portfolio diversification analysis, and performance attribution tools.
- Bridge Simulation and Real Investing
Explore opportunities to connect the platform with brokerage services or educational investment programs, allowing users to transition from simulation to real-world investing.
By focusing on these enhancements, future versions of PortTrack can provide a more comprehensive and impactful learning experience.
