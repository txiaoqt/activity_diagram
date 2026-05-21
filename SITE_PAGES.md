# LYDO Connect Site Pages

This page inventory was scanned from the actual frontend route and admin portal files:

- `src/App.tsx`
- `src/components/Navbar.tsx`
- `src/admin/AdminPortal.tsx`
- `src/admin/components/Sidebar.tsx`

## User Interface / Public Portal Pages

| Page | Route | Notes |
| --- | --- | --- |
| Home / Landing Page | `/` | Main public homepage. |
| Programs Page | `/programs` | Lists available youth programs. |
| Program Details / Registration Page | `/programs/:programId` | Program record page; shares the detail/registration component. |
| Events Page | `/events` | Lists youth events. |
| Event Details / Registration Page | `/events/:eventId` | Event record page with detail and registration flow. |
| Organizations Page | `/organizations` | Displays youth organizations and source references. |
| About / Platform Overview Page | `/about` | Platform and LYDO information page. |
| Advocacy Page | `/advocacy` | Route alias that uses the About page component. |
| Login / Sign In Page | `/signin` | User login page. |
| Sign Up / Account Registration Page | `/signup` | User account registration page. |
| Profile / Participation History Page | `/profile` | Authenticated user profile, memberships, and registrations. |
| Terms of Service Page | `/terms` | Legal policy page for Terms of Service. |
| Privacy Policy Page | `/privacy` | Legal policy page for Privacy Policy. |
| Disclosure Registry / Transparency Reports Page | `/transparency/reports` | Public transparency document registry. |
| Transparency Board Page | `/transparency/board` | Public board and compliance status view. |
| Financial Disclosure Page | `/transparency/financial-disclosure` | Public financial transparency view. |
| Barangay Map Page | `/transparency/barangay-map` | Public barangay map and governance data view. |
| Citizen Desk Page | `/transparency/citizen-desk` | Public citizen service request and tracking page. |
| Feedback / Citizen Desk Shortcut | `/feedback` | Route alias that uses the Citizen Desk page component. |
| Not Found Page | `*` | Fallback page for unknown public routes. |

## Admin Interface Pages

Admin interface pages are handled as modules/tabs inside the Admin Portal. The main admin route is `/admin`; the active module changes inside the admin layout instead of using separate browser URLs.

| Admin Page / Module | Route Context | Notes |
| --- | --- | --- |
| Admin Login / Sign In Page | `/admin/signin` | Admin-only deployment sign-in route. In combined mode, admins sign in through `/signin` and are redirected to `/admin`. |
| Admin Portal Shell | `/admin` | Main protected admin layout with sidebar and top navigation. |
| Dashboard | `/admin` tab: `dashboard` | Admin overview, metrics, shortcuts, and recent activity. |
| Programs Management | `/admin` tab: `programs` | Create, edit, publish, archive, and manage programs. |
| Events Management | `/admin` tab: `events` | Create, edit, publish, archive, and manage events. |
| Registrations Monitoring | `/admin` tab: `registrations` | Monitor program/event registrations, CSV export, external sheet preview, and sync actions. |
| Organizations Management | `/admin` tab: `organizations` | Manage organization records and source references. |
| Barangay Map Data | `/admin` tab: `barangays` | Manage barangay map records and related data. |
| Transparency Documents | `/admin` tab: `documents` | Manage disclosure documents and public file links/uploads. |
| Transparency Board Management | `/admin` tab: `transparency-board` | Manage quarterly board and monthly compliance records. |
| Financial DSS | `/admin` tab: `financial-dss` | Manage barangay financial data and youth governance metrics. |
| Citizen Desk Management | `/admin` tab: `citizen-desk` | Review, assign, prioritize, and update citizen tickets. |
| Audit Logs | `/admin` tab: `audit-logs` | Review system audit entries and changed values. |
| Users Management | `/admin` tab: `users` | Manage user profiles and account-related records. |
| Roles & Permissions | `/admin` tab: `roles` | Manage roles and access permissions. |

## Route Notes

- `/feedback` and `/transparency/citizen-desk` open the same Citizen Desk page component.
- `/advocacy` opens the same page component as `/about`.
- `/events/:eventId` and `/programs/:programId` share the same detail/registration component.
- The Terms and Privacy agreement shown after login is a modal gate, not a separate route.
- Admin modules are not separate URL paths; they are tabs within the protected `/admin` interface.
