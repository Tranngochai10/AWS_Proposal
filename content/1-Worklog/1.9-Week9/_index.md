---
title: "Week 9 Worklog"
date: 2025-09-09
weight: 9
chapter: false
pre: " <b> 1.9. </b> "
---

### Week 9 Objectives:

* Complete Employee Login page and integrate with backend API
* Start developing Manager Dashboard page
* Design layout and navigation for Manager page
* Build basic components for Manager interface

### Tasks to be carried out this week:
| Day | Task                                                                                                                                    | Start Date | Completion Date | Reference Material                        |
| --- | --------------------------------------------------------------------------------------------------------------------------------------- | ---------- | --------------- | ----------------------------------------- |
| 1   | - Integrate Employee Login with backend API <br> - Handle authentication response and redirect logic                                          | 29/09/2025 | 29/09/2025      |                                          |
| 2   | - Design layout for Manager Dashboard <br> - Build navigation menu with modules: Employees, Attendance, Leave, Reports            | 30/09/2025 | 30/09/2025      |                                          |
| 3   | - Create sidebar navigation component <br> - Implement role-based menu visibility (only show menu items Manager has permission for)                    | 01/10/2025 | 01/10/2025      |                                          |
| 4   | - Build Manager Dashboard overview <br> - Create widgets: Team statistics, Pending approvals, Recent activities                     | 02/10/2025 | 02/10/2025      |                                          |
| 5   | - Implement header component with user profile and notifications <br> - Build breadcrumb navigation                                    | 03/10/2025 | 03/10/2025      |                                          |
| 6   | - Testing Manager page layout <br> - Responsive design and mobile optimization                                                           | 04/10/2025 | 04/10/2025      |                                          |

### Week 9 Achievements:

* Completed Employee Login integration with backend:
  * API integration for authentication endpoints
  * Token management and refresh token logic
  * Error handling for API failure cases
  * Success redirect based on user role
  * Protected routes implementation

* Designed and built Manager Dashboard layout:
  * Sidebar navigation with collapsible menu
  * Main content area with responsive grid
  * Header with user profile dropdown
  * Footer with company information
  * Mobile-friendly hamburger menu

* Completed navigation system:
  * Role-based menu items (only show modules Manager has permission for)
  * Active route highlighting
  * Nested menu support for sub-modules
  * Quick access shortcuts
  * Search functionality in menu

* Built Dashboard overview components:
  * **Team Statistics Widget:** Display employee count, attendance rate, on leave
  * **Pending Approvals Widget:** List of requests needing approval (leave requests, overtime)
  * **Recent Activities Widget:** Timeline of recent activities
  * **Quick Actions:** Buttons for frequently used actions

* Implemented header and user interface:
  * User profile dropdown with avatar
  * Notifications bell with badge count
  * Settings and logout options
  * Breadcrumb navigation for deep navigation
  * Search bar in header

* Testing and optimization:
  * Responsive design testing on various devices
  * Performance optimization (lazy loading, code splitting)
  * Cross-browser compatibility
  * Accessibility improvements
