# AGENTS.md - AI Developer Guidelines

## Project: Startup ERP

A modular ERP system for startups. Build incrementally, ship working features, iterate.

## Architecture Decisions

- **Monorepo:** Use Turborepo for managing apps + packages
- **Type-safe:** TypeScript everywhere, strict mode
- **API:** tRPC preferred (type-safe end-to-end), REST fallback acceptable
- **ORM:** Prisma (PostgreSQL)
- **UI:** shadcn/ui components + Tailwind CSS
- **Auth:** NextAuth.js with credentials + OAuth providers

## Development Workflow

1. Create feature branch from `main`
2. Implement feature with tests
3. Open PR with clear description
4. Merge after review

## Code Standards

- ESLint + Prettier enforced
- Conventional commits (`feat:`, `fix:`, `docs:`, etc.)
- No `any` types without explicit justification
- Components in PascalCase, utilities in camelCase
- API routes handle errors gracefully with proper status codes

## Priority Order

Build in this sequence:
1. **Foundation** - Monorepo setup, DB schema, auth
2. **Inventory** - Core module, most dependencies
3. **Sales** - Customer-facing, revenue critical
4. **Purchasing** - Vendor management, stock replenishment
5. **Accounting** - Financial tracking, reporting
6. **HR** - Employee management, payroll

## Database Schema Principles

- Use UUIDs for primary keys
- Soft deletes (`deletedAt` timestamp) for important entities
- Audit fields on all tables (`createdAt`, `updatedAt`, `createdBy`)
- Multi-tenant ready (add `organizationId` to all business entities)

## Testing

- Unit tests for business logic
- Integration tests for API routes
- E2E tests for critical user flows (auth, checkout, etc.)

## Questions?

If unclear on requirements, ask before implementing. Prefer simple solutions that work over complex solutions that might work.
