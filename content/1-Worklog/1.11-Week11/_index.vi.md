---
title: "Worklog Tuần 11"
date: 2025-09-09
weight: 11
chapter: false
pre: " <b> 1.11. </b> "
---

### Mục tiêu tuần 11:

* Phát triển module Quản lý Nghỉ phép và Phê duyệt trong Manager page
* Xây dựng Leave Request management
* Implement Approval workflow
* Tạo Attendance tracking và reports cho Manager

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc                                                                                                                                    | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                            |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------------- |
| 1   | - Xây dựng Leave Request List với filters <br> - Implement status badges: Pending, Approved, Rejected, Cancelled                        | 13/10/2025   | 13/10/2025      |                                          |
| 2   | - Tạo Leave Request Detail modal/page <br> - Hiển thị thông tin: employee, dates, reason, attachments, approval workflow                 | 14/10/2025   | 14/10/2025      |                                          |
| 3   | - Implement Approval actions: Approve, Reject, Request more info <br> - Xây dựng approval comments và notifications                      | 15/10/2025   | 15/10/2025      |                                          |
| 4   | - Xây dựng Attendance Overview cho team <br> - Calendar view để xem attendance của nhân viên                                             | 16/10/2025   | 16/10/2025      |                                          |
| 5   | - Tạo Attendance Reports: daily, weekly, monthly <br> - Export reports ra Excel/PDF                                                        | 17/10/2025   | 17/10/2025      |                                          |
| 6   | - Testing Leave và Attendance modules <br> - Fix bugs và cải thiện UX                                                                   | 18/10/2025   | 18/10/2025      |                                          |

### Kết quả đạt được tuần 11:

* Hoàn thành Leave Request Management:
  * **Leave Request List:**
    * Table view với columns: Employee, Leave Type, Dates, Duration, Status, Submitted Date
    * Status badges với color coding (Pending=yellow, Approved=green, Rejected=red)
    * Quick filters: My Team, Pending Approval, This Month, This Year
    * Sort by date, employee, status
    * Bulk approve/reject functionality
  * **Leave Request Detail:**
    * Employee information card
    * Leave details: type, start/end date, duration, reason
    * Attachments viewer (medical certificates, documents)
    * Approval workflow visualization (current step, approvers)
    * Comments/notes section
    * Action buttons: Approve, Reject, Request Info, View History

* Implement Approval Workflow:
  * **Approval Actions:**
    * Approve với optional comments
    * Reject với required reason
    * Request more information
    * Delegate approval (nếu có quyền)
  * **Workflow Visualization:**
    * Step-by-step approval process
    * Current approver highlighting
    * Timeline view của approval history
    * Email notifications cho mỗi step
  * **Comments System:**
    * Threaded comments
    * @mention support
    * File attachments trong comments
    * Comment history với timestamps

* Xây dựng Attendance Overview:
  * **Team Calendar View:**
    * Monthly calendar với color coding
    * Legend: Present, Absent, On Leave, Holiday
    * Click vào date để xem detail
    * Filter by employee hoặc department
  * **Attendance Statistics:**
    * Present rate, Absent rate, Late arrivals
    * Overtime hours summary
    * Top performers và attendance issues
  * **Quick Actions:**
    * Mark attendance manually (nếu có quyền)
    * Add notes cho attendance records
    * Export attendance data

* Tạo Attendance Reports:
  * **Report Types:**
    * Daily report: attendance của ngày
    * Weekly report: tổng hợp tuần
    * Monthly report: báo cáo tháng với charts
    * Custom date range report
  * **Report Features:**
    * Filter by department, employee, date range
    * Group by department hoặc employee
    * Charts và graphs (bar, line, pie)
    * Summary statistics
  * **Export Functionality:**
    * Export to Excel với formatting
    * Export to PDF với charts
    * Email report functionality
    * Schedule automated reports

* Implement Notifications:
  * Real-time notifications cho new leave requests
  * Email notifications cho approvals/rejections
  * In-app notification center
  * Notification preferences settings

* Testing và optimization:
  * Unit tests cho approval workflow
  * Integration tests cho leave management
  * Performance testing với large datasets
  * User acceptance testing với Manager users
