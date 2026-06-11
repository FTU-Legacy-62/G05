# Individual footprint

## Member: Pham Quoc Thai - 2313380033

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