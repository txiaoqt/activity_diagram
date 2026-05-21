# LYDO Connect Site Map

This sitemap shows the UI/page hierarchy of the LYDO Connect application. It was based on the actual React routes and admin portal modules in:

- `src/App.tsx`
- `src/components/Navbar.tsx`
- `src/admin/AdminPortal.tsx`
- `src/admin/components/Sidebar.tsx`

## App Structure Overview

- The app can run as a combined public/admin app, a user-only app, or an admin-only app.
- Public user pages use normal browser routes such as `/programs`, `/events`, and `/profile`.
- Admin pages are modules inside the protected `/admin` portal. They behave like admin tabs, not separate browser route paths.
- The Terms and Privacy agreement is a modal gate shown after login for non-admin users. It is not a separate page route.

## User Interface / Public Portal Hierarchy

```text
User Interface / Public Portal
+-- Home / Landing Page (/)
|   +-- Explore Programs -> /programs
|   +-- View Events -> /events
|   +-- View Transparency Portal -> /transparency/reports
|   +-- Sign In / Open Portal -> /signin
|
+-- Authentication and Account Access
|   +-- Login / Sign In Page (/signin)
|   +-- Sign Up / Account Registration Page (/signup)
|   +-- Terms of Service Page (/terms)
|   +-- Privacy Policy Page (/privacy)
|   +-- Policy Agreement Modal (post-login gate, no route)
|
+-- Programs
|   +-- Programs List Page (/programs)
|   +-- Program Details / Registration Page (/programs/:programId)
|
+-- Events
|   +-- Events List Page (/events)
|   +-- Event Details / Registration Page (/events/:eventId)
|
+-- Organizations
|   +-- Organizations Page (/organizations)
|   +-- Organization Info / Source Reference View (same-page interaction)
|
+-- User Profile
|   +-- Profile / Participation History Page (/profile)
|       +-- Event Details link -> /events/:eventId
|       +-- Program Details link -> /programs/:programId
|
+-- Transparency and Citizen Services
|   +-- Citizen Desk Page (/feedback)
|   |   +-- Alias route -> /transparency/citizen-desk
|   +-- Disclosure Registry / Transparency Reports Page (/transparency/reports)
|   +-- Transparency Board Page (/transparency/board)
|   +-- Financial Disclosure Page (/transparency/financial-disclosure)
|   +-- Barangay Map Page (/transparency/barangay-map)
|
+-- Information Pages
|   +-- About / Platform Overview Page (/about)
|   +-- Advocacy Page (/advocacy, uses About page component)
|
+-- Fallback
    +-- Not Found Page (*)
```

## Public Navigation Hierarchy

```text
Main Public Navbar
+-- Home -> /
+-- Programs -> /programs
+-- Events -> /events
+-- Organizations -> /organizations
+-- Transparency dropdown
|   +-- Citizen Desk -> /feedback
|   +-- Disclosure Registry -> /transparency/reports
|   +-- Transparency Board -> /transparency/board
|   +-- Financial Disclosure -> /transparency/financial-disclosure
|   +-- Barangay Map -> /transparency/barangay-map
+-- Auth area
    +-- If signed out
    |   +-- Sign In -> /signin
    |   +-- Get Started -> /signup
    +-- If signed in
        +-- Profile -> /profile
        +-- Sign Out
```

## Admin Interface Hierarchy

```text
Admin Interface
+-- Admin Login / Sign In
|   +-- Admin-only route -> /admin/signin
|   +-- Combined app sign-in -> /signin, then redirects admin users to /admin
|
+-- Admin Portal Shell (/admin)
    +-- Sidebar Navigation
    +-- Top Navigation
    +-- Overview
    |   +-- Dashboard (tab: dashboard)
    |
    +-- Youth Records
    |   +-- Programs Management (tab: programs)
    |   +-- Events Management (tab: events)
    |   +-- Registrations Monitoring (tab: registrations)
    |   +-- Organizations Management (tab: organizations)
    |   +-- Barangay Map Data (tab: barangays)
    |
    +-- Transparency
    |   +-- Transparency Documents (tab: documents)
    |   +-- Transparency Board Management (tab: transparency-board)
    |   +-- Financial DSS (tab: financial-dss)
    |   +-- Citizen Desk Management (tab: citizen-desk)
    |
    +-- Administration
        +-- Audit Logs (tab: audit-logs)
        +-- Users Management (tab: users)
        +-- Roles and Permissions (tab: roles)
```

## Admin Module Notes

| Admin Group | Pages / Modules |
| --- | --- |
| Overview | Dashboard |
| Youth Records | Programs, Events, Registrations, Organizations, Barangay Map Data |
| Transparency | Transparency Docs, Transparency Board, Financial DSS, Citizen Desk |
| Administration | Audit Logs, Users, Roles and Permissions |

## Route and Hierarchy Notes

- `/feedback` and `/transparency/citizen-desk` open the same Citizen Desk page component.
- `/advocacy` opens the same page component as `/about`.
- `/events/:eventId` and `/programs/:programId` share the same detail/registration component.
- Admin module changes are handled by internal tab state inside `/admin`, not by separate route URLs.
- Create, edit, view, filter, export, sync, and status-update screens inside admin modules are internal module workflows rather than top-level pages.
