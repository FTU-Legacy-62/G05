# Individual Footprint

## Member: Nguyen Anh Thu - 2312380036

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

