# Product Name

PortTrack

## Group Code

G05

## Team Members

| Nguyen Anh Thu | 2312380036 | Team Leader and Database Coordinator |

| To Ha Vy | 2313380039 | Backend: Authentication, Security, Room Management, and Market Data Support |

| Pham Quoc Thai | 2313380033 | Backend: Trading, Portfolio Management, and Stock Price Integration |

| Pham Linh Nhan | 2312380024 | Frontend: Authentication, Dashboard, Owner Monitoring, and Navigation |

| Dang Ngoc Linh | 2312380018 | Frontend: Student Room, Trading, Portfolio, Summary, and Transaction History |


## Short Product Description

PortTrack is a web-based stock investment simulation platform designed for educational use. Lecturers create simulation rooms and allocate virtual capital, while students use that capital to buy and sell stocks using market price data without risking real money. The platform automatically updates cash balances, holdings, portfolio value, profit and loss, and transaction history. Lecturers can monitor participants, review all transactions, compare performance, and access a room leaderboard.

## Problem the Product Solves

Portfolio Management courses require practical investment activities, but trading with real money is risky and unsuitable for most classroom exercises. Spreadsheet-based simulations also make it difficult for lecturers to monitor decisions, verify transactions, and evaluate performance consistently.

PortTrack provides a centralized and transparent simulation environment. Students can practice portfolio management under realistic trading rules, while lecturers can supervise the entire process and evaluate results using recorded data.

## Target Users

- Lecturers teaching Portfolio Management or related finance courses.
- Students learning stock investment and portfolio management.
- Classes, course projects, and educational investment simulations.

## Main Features

- Account registration, login, JWT authentication, and role-based access.
- Public or private simulation rooms with configurable capital and duration.
- Room participation through a unique room code.
- Virtual BUY and SELL orders using current market quote data.
- Market-session validation and T+2 settlement for newly purchased shares.
- A 0.15% trading fee and a 0.1% tax on sell orders.
- Cash balance, holdings, NAV, profit/loss, and return calculations.
- Portfolio summary and transaction history for students.
- Participant monitoring, room-wide transaction review, submissions, and a lecturer-only leaderboard.

## How to Run the Product

1. Open [PortTrack Demo](https://port-track-xi.vercel.app/).
2. Register as either a lecturer or a student, then log in.
3. As a lecturer, create a room and share its room code.
4. As a student, join the room using the code and password if required.
5. During Vietnamese market hours, search for a stock symbol and submit a BUY or SELL order.
6. Review the portfolio, summary, and transaction history.
7. As a lecturer, open the room management pages to review players, transactions, submissions, and rankings.


## Demo Links

- Demo: https://port-track-xi.vercel.app/
- Repository: https://github.com/FTU-Legacy-62/G05
- Demo account: reviewers can register a new account; no real credentials are published.

## Data Notes

- Account, room, portfolio, submission, and transaction records are user-generated simulation data.
- Investment capital is virtual; PortTrack does not place orders through a brokerage.
- The deployed backend retrieves Vietnamese stock quote data from an external service configured through `ENTRADE_API_URL`.
- Application data is stored in a MySQL-compatible database.
- Database passwords, JWT secrets, and other deployment credentials are supplied through environment variables and are not committed to the repository.

## Additional Notes

- [GROUP_FOOTPRINT.md](GROUP_FOOTPRINT.md) explains the product logic, user flow, design decisions, limitations, and team learning.
- [INDIVIDUAL_FOOTPRINT.md](INDIVIDUAL_FOOTPRINT.md) records each member's contribution and supporting evidence.
- PortTrack is an educational simulation, not an investment advisory or real trading platform.
