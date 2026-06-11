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

Challenge 1 -Understanding how data is shared across multiple Room pages (RoomLayout + Outlet Context)

Challenge

One of the biggest challenges was understanding how different pages inside the Room module could share the same data without repeatedly calling the backend. As a non-technical student, I initially thought that each page, such as My Portfolio, Trade Hub, and Summary, should independently load its own room information.

I also found concepts such as useParams(), Outlet, and Outlet Context difficult to understand. In particular, I could not understand why roomId was extracted only once in RoomLayout but could still be used by all the child pages.

Solution

After studying the project structure, I realized that RoomLayout acts as a parent container for all pages inside a room. It first extracts roomId from the URL, retrieves dashboard information and cash balance from the backend, stores them in React State, and then passes these values through Outlet Context.

Therefore, when users switch between Dashboard, My Portfolio, Trade Hub, Transaction History, and Summary, the Header and Sidebar remain unchanged while only the content inside <Outlet /> is replaced. This approach avoids duplicate API calls and provides a smoother navigation experience.

Challenge 2 - Understanding asynchronous API calls and React State (Portfolio & Summary Pages)

Challenge

Another major challenge was understanding why the Portfolio and Summary pages could not display data immediately after the page was opened. Initially, I expected that once I called roomService.getPortfolio(roomId) or roomService.getSummary(roomId), the data would already be available for rendering.

However, I encountered situations where the page attempted to access values such as portfolio.holdings before the API had finished returning data, making it difficult for me to understand why the interface could become empty or produce errors.

As a beginner, concepts such as useEffect, useState, asynchronous functions (async/await), and the component lifecycle were unfamiliar.

Solution

To solve this problem, I learned to separate the loading process into different stages. The API is first called inside useEffect(), the returned data is stored using useState(), and the interface is rendered only after the data becomes available.

I also implemented loading states, error messages, and a cancelled flag to prevent state updates when users leave the page before the API request finishes. This made the Portfolio and Summary pages more stable and prevented unexpected rendering issues.

Challenge 3 - Implementing the Trade Hub Workflow and Input Validation

Challenge

The Trade Hub page was one of the most challenging modules because it involves multiple sequential steps rather than simply displaying information. As someone without a technical background, I initially assumed that users could directly press Confirm Order after entering a stock symbol and quantity. However, I later realized that the trading process depends on several conditions and backend validations.

I found it difficult to understand the relationship between searching for a stock, retrieving its latest market price, checking whether the market is open, validating the input quantity, and finally submitting the trading request through the API. Understanding how these independent actions should be connected into one complete workflow was particularly challenging.

Solution

To address this issue, I broke the trading process into a clear sequence of operations:

Search Stock → Retrieve Price → Display Quote → Validate Trading Conditions → Submit Order → Receive Backend Response → Update the User Interface

Instead of allowing users to submit requests immediately, the frontend first validates whether a stock has been searched successfully, whether the market session is open, and whether the entered quantity is valid. Only after these conditions are satisfied does the system call executeTrade() to send the request to the backend.

This step-by-step validation improves system reliability, reduces invalid requests, and provides users with clearer feedback when errors occur.

### Message for Future Students

Plan the interface around the user's workflow, not only visual appearance. Future versions should connect price information with company fundamentals and market context so students can make more informed decisions.