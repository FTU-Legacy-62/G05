# Individual footprint

## Member: Dang Ngoc Linh - 2312380018

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