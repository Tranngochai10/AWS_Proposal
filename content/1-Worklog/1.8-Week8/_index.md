---
title: "Week 8 Worklog"
date: 2025-09-09
weight: 8
chapter: false
pre: " <b> 1.8. </b> "
---

### Week 8 Objectives:

* Develop Employee Login page - Build UI components
* Implement form validation and error handling
* Integrate SSO authentication (Google, Microsoft)
* Build MFA/2FA processing logic

### Tasks to be carried out this week:
| Day | Task                                                                                                                                    | Start Date | Completion Date | Reference Material                        |
| --- | --------------------------------------------------------------------------------------------------------------------------------------- | ---------- | --------------- | ----------------------------------------- |
| 1   | - Build LoginForm component with fields: email/phone, password <br> - Implement form validation (email format, password strength) | 22/09/2025 | 22/09/2025      |                                          |
| 2   | - Create UI for SSO buttons (Google, Microsoft) <br> - Styling and responsive design for login page                                            | 23/09/2025 | 23/09/2025      |                                          |
| 3   | - Implement error handling and display error messages <br> - Build loading states and disabled states for buttons                      | 24/09/2025 | 24/09/2025      |                                          |
| 4   | - Create MFA/OTP input component <br> - Implement OTP verification logic                                                             | 25/09/2025 | 25/09/2025      |                                          |
| 5   | - Build Forgot password modal/form <br> - Implement "Remember me" checkbox and session management                                       | 26/09/2025 | 26/09/2025      |                                          |
| 6   | - Testing and fix bugs <br> - Optimize UI/UX, improve accessibility                                                                   | 27/09/2025 | 27/09/2025      |                                          |

### Week 8 Achievements:

* Successfully completed LoginForm component with full features:
  * Input fields for email/phone and password
  * Form validation with real-time feedback
  * Password visibility toggle
  * Responsive design for mobile and desktop

* Successfully integrated SSO authentication:
  * Google Sign-In button with OAuth flow
  * Microsoft Sign-In button with Azure AD integration
  * Callback handling and token management
  * Error handling for SSO failure cases

* Completed MFA/OTP component:
  * OTP input with 6 digits
  * Auto-focus and paste support
  * Resend OTP functionality
  * Countdown timer for resend
  * Integration with backend API

* Built Forgot password flow:
  * Modal/form to enter email/phone
  * Reset password link sent via email
  * Success/error messages
  * Complete navigation flow

* Implemented session management:
  * "Remember me" checkbox functionality
  * Token storage (localStorage/sessionStorage)
  * Auto-logout when session expires
  * Device management tracking

* Testing and optimization:
  * Unit tests for components
  * Integration tests for authentication flow
  * Cross-browser compatibility testing
  * Accessibility improvements (ARIA labels, keyboard navigation)
