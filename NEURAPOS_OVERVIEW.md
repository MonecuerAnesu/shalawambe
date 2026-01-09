# NeuraPOS Enterprise Subscription POS Platform

Cloud-Controlled · Subscription-Based · Enterprise Buyout Option

## 1. Real-World Target Market (Who Buys This)

This system is designed for operational businesses, not hobby users.

### Primary Markets

- Retail shops & minimarkets
- Supermarkets & wholesalers
- Electronics & hardware stores
- Clothing & fashion outlets
- Pharmacies (non-regulated first, regulated extensions later)
- Fuel stations (POS + inventory focused)
- Multi-branch franchises

### Secondary / Expansion Markets

- Restaurants & cafés (table/KDS add-on)
- Distribution companies
- Churches & institutions with internal stores
- NGOs and enterprises needing offline-first sales tracking

The system supports single-store businesses up to national chains.

## 2. Commercial Model (How You Make Money)

### A. Subscription SaaS (Default)

Businesses subscribe monthly or annually.

You control:

- Number of stores/branches
- Number of POS devices
- Number of staff users
- Feature access (inventory, reports, exports, APIs)
- Billing enforcement

If subscription expires:

- POS switches to read-only + emergency sell mode
- Data is never deleted
- Full access resumes instantly on payment

### B. Enterprise Full System – $5,000

For enterprises that do not want shared SaaS:

They receive:

- A dedicated system instance
- Isolated database
- Private storage
- Custom domain
- Priority support
- SLA contract

You still:

- Own the code
- Control updates
- Control licensing
- Control access keys

This is not source code ownership. It is licensed enterprise software.

## 3. How the System Works in Real Life (Flow)

### Store Level (Daily Operations)

- Cashier logs into POS terminal
- Terminal is already registered to a store + branch
- Products are scanned or searched
- Discounts and taxes apply automatically
- Payment accepted (cash/card/mobile)
- Receipt printed or sent digitally
- Sale syncs to cloud (or queues if offline)

### Manager Level

- Reviews daily sales
- Approves refunds
- Manages inventory
- Closes cash shifts
- Views staff performance

### Owner / Head Office

- Views all branches in one dashboard
- Sees real-time revenue
- Manages pricing centrally
- Controls staff permissions
- Handles billing & subscriptions

### You (Platform Owner)

- See all tenants
- Suspend/restore businesses
- Control plans and limits
- Push updates globally
- Monitor fraud and abuse
- Sell enterprise licenses

## 4. Application Pages (Every Screen That Exists)

### A. POS Application (Tablet / Desktop)

- Login Screen
  - Email/username + password
  - Device verification
  - Role check (cashier/manager)
- Sales Screen
  - Product grid + barcode input
  - Search with instant results
  - Quantity controls
  - Discount button
  - Tax breakdown
  - Cart summary
  - Checkout button
- Payment Screen
  - Cash
  - Card
  - Mobile money
  - Split payments
  - Change calculation
- Receipt Screen
  - Print
  - Email
  - SMS
  - QR invoice
- Returns & Refunds
  - Sale lookup
  - Reason selection
  - Manager approval (PIN/role)
  - Audit logging
- Shift Management
  - Open shift
  - Cash float
  - Close shift
  - Cash variance report
- Offline Status
  - Clear indicator
  - Sync queue counter
  - Conflict resolution handled automatically

### B. Admin Web Dashboard (Business Side)

- Dashboard
  - Revenue overview
  - Sales trends
  - Best sellers
  - Branch comparison
- Products
  - Products & variants
  - Barcodes
  - Pricing rules
  - Categories
  - Bulk import/export
- Inventory
  - Stock levels
  - Transfers
  - Stock adjustments
  - Low-stock alerts
  - Supplier tracking
- Sales & Reports
  - Daily / monthly sales
  - Profit & margin
  - Tax/VAT reports
  - Cash vs digital breakdown
  - Export to CSV/PDF
- Customers (Optional)
  - Purchase history
  - Loyalty points
  - Contact details
- Staff & Roles
  - Users
  - Role templates
  - Permission matrix
  - Activity logs
- Branches & Devices
  - Branch creation
  - POS device approval
  - Device revocation
  - Register limits
- Settings
  - Business details
  - Tax rules
  - Receipt branding
  - Notification rules

### C. Billing & Subscription Pages

- Plan Overview
  - Current plan
  - Limits
  - Usage meters
- Upgrade / Downgrade
  - Prorated changes
  - Instant effect
- Invoices
  - Payment history
  - Download invoices
  - Tax receipts
- Payment Methods
  - Cards
  - Bank
  - Manual enterprise invoicing

### D. Super Admin (You Only)

- Tenant Management
  - View all businesses
  - Suspend/restore
  - Impersonate admin (audit logged)
- Plans & Pricing
  - Create plans
  - Set feature flags
  - Adjust limits
- Enterprise Instances
  - Provision new dedicated systems
  - Assign domains
  - Manage SLA status
- System Monitoring
  - Error rates
  - Usage metrics
  - Fraud detection
- Update Control
  - Staged rollouts
  - Emergency patches

## 5. Authentication & Security (How Access Works)

### Authentication

- Central identity service
- Passwords hashed (bcrypt/argon2)
- Optional MFA for admins
- Token-based sessions (JWT + refresh tokens)

### Authorization

- Role-Based Access Control (RBAC)
- Permissions enforced server-side
- UI only reflects allowed actions

### Device Security

- POS devices must be approved
- Device IDs bound to branches
- Lost device = instant revoke

### Audit & Compliance

Every action logged:

- Who
- What
- When
- From which device

Logs are append-only.

## 6. Database Design (Real Tables That Exist)

### Core Business Tables

- tenants
- subscriptions
- plans
- branches
- devices
- users
- roles
- permissions

### Sales & Operations

- products
- product_variants
- categories
- inventory_items
- stock_movements
- sales
- sale_items
- payments
- refunds
- receipts

### Financial

- tax_rates
- discounts
- cash_shifts
- invoices
- transactions

### Security & Control

- audit_logs
- login_attempts
- device_sessions
- api_keys

### Enterprise Isolation

- Dedicated databases OR tenant-scoped tables with enforced isolation
- No cross-tenant data access possible

## 7. Offline-First Reality

- POS works without internet
- Sales stored locally
- Automatic sync when online
- Conflict resolution handled by timestamps + device priority
- Business never stops selling

## 8. GitHub & Distribution Strategy (How You Sell It)

### Public GitHub (Marketing + Trust)

- Landing repository
- Architecture overview
- API documentation
- SDKs
- Issue tracking
- Roadmap (controlled)

### Private GitHub (Core System)

- Backend source
- POS app source
- Admin dashboard source
- CI/CD pipelines
- Only licensed deployments

### Enterprise Delivery

- Provisioned environment
- Deployment automation
- License keys
- Access credentials
- Documentation

## 9. Hosting & Control Model

- Cloud-hosted by default
- Regional deployments possible
- Enterprise dedicated environments
- Central update pipeline
- Backup & disaster recovery

## 10. Why Businesses Trust This System

- Fast
- Offline-capable
- Secure
- Scales from 1 store to 1,000+
- Clear pricing
- Enterprise-ready
- Vendor-controlled (no chaos)

## 11. Platform Name & Data Stack

- POS name: NeuraPOS
- POS device database: SQLite (offline cache + queued transactions)
- Cloud backend database: PostgreSQL (main source of truth)
- Supporting services: Redis (caching) + ClickHouse (analytics)
