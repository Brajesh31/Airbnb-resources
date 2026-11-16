# Database and Persistence

## 1. Current status

This repository has no database and no persistent application data layer. The page content is embedded in `index.html`, and images are stored as static repository files.

There is no SQL database, document database, object storage integration, ORM, migration tool, connection pool, or database credential.

## 2. What is and is not stored

| Data | Current handling |
|---|---|
| Listing titles and descriptions | Static HTML |
| Sample prices and distance labels | Static HTML |
| Category and listing images | Local repository files |
| User profiles | Not collected or stored |
| Login credentials | Not collected or stored |
| Favorites | Not persisted |
| Search history | Not persisted |
| Booking records | Not collected or stored |
| Payment information | Not collected or stored |
| Availability inventory | Not maintained |

Browser caching may occur as part of normal web delivery, but it is not an application database and is not controlled as user-account persistence by this project.

## 3. Why a database is not needed now

A database would add operational complexity without solving a current requirement. The project is a static visual learning exercise. Static files are sufficient to display the current content.

Do not introduce a database simply to make the repository appear more production-like. A database is justified only when a defined feature needs structured, mutable, shared, or persistent data.

## 4. Requirements before introducing persistence

Before choosing a database, define:
- the exact feature and data ownership;
- entities and relationships;
- minimum required fields;
- read and write paths;
- data validation and integrity rules;
- user and administrator access boundaries;
- retention and deletion rules;
- backup and recovery objectives;
- migration and rollback strategy;
- monitoring and operational ownership;
- privacy notice and legal obligations;
- security and abuse scenarios.

Avoid collecting sensitive data unless it is strictly necessary and properly protected.

## 5. Database design considerations for a hypothetical future system

If the project evolves into a real marketplace, separate concepts such as users, listings, listing media, availability, reservations, and payments. Define stable identifiers, constraints, relationships, and audit requirements. Do not store payment card details directly unless the organization has the necessary compliance capability; use an appropriate payment provider.

This is conceptual guidance only. No schema is currently implemented or approved.

## 6. Data lifecycle

A real data feature needs a complete lifecycle:
1. collection with a stated purpose;
2. validation and normalization;
3. authorized access;
4. retention for a defined period;
5. correction and deletion mechanisms;
6. backups with controlled access;
7. secure disposal when no longer required.

A future system must document how deletion requests interact with backups and legal retention requirements.

## 7. Secrets and connection strings

No database connection string is needed for the current page. If a backend is added, credentials must be stored in the hosting platform's secret manager or another appropriate secure store. Never commit a production connection string or expose it to browser code.

## 8. Related documentation

See [API](api.md), [Architecture](architecture.md), [Privacy](privacy.md), and [Security](security.md). These documents must be updated together if persistent data is introduced.
