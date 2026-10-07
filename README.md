# Service Request & Support Ticket Management Portal

**Project ID:** WEB-W2-002  
**Domain:** Web Development | Business Applications | CRUD | Dashboard  
**Technology:** HTML5, CSS3, JavaScript, LocalStorage  
**Level:** Beginner → Intermediate

## 1. Project Overview
A responsive internal service portal where employees raise service requests and support staff manage tickets through a centralized dashboard. Tickets are stored in browser LocalStorage so data remains available after refresh.

## 2. Features
- Employee request form with validation
- Automatic ticket IDs such as `SR-2026-0001`
- Default `Open` status
- Admin/support dashboard with KPI cards and charts
- Ticket search and multi-filtering
- Ticket details and CRUD-style management
- Status flow: Open → Assigned → In Progress → Resolved → Closed
- Priority and assignment updates
- Comments and resolution notes
- Basic SLA calculation: Critical 4h, High 8h, Medium 24h, Low 48h
- Employee dashboard with ticket lookup and close-resolved action
- LocalStorage persistence
- Responsive desktop/tablet/mobile layout
- Empty states and inline confirmation/validation messages

## 3. Folder Structure
```text
service-request-portal/
├── index.html
├── dashboard.html
├── tickets.html
├── ticket-details.html
├── employee.html
├── css/
│   └── style.css
├── js/
│   ├── app.js
│   ├── tickets.js
│   └── dashboard.js
├── assets/
│   └── images/
├── screenshots/
│   ├── 01-employee-request.png
│   ├── 02-dashboard.png
│   ├── 03-ticket-management.png
│   ├── 04-ticket-details.png
│   └── 05-employee-dashboard.png
└── README.md
```

## 4. How to Run
### Method A — VS Code + Live Server (recommended)
1. Extract the ZIP folder.
2. Open `service-request-portal` in Visual Studio Code.
3. Install the **Live Server** extension if needed.
4. Right-click `index.html` → **Open with Live Server**.
5. Open the shown local address in Chrome.
6. Use **Load Demo Data** on the dashboard to populate sample tickets.

### Method B — Python local server
Open Command Prompt/Terminal inside the project folder and run:
```bash
python -m http.server 5500
```
Then open:
`http://localhost:5500/index.html`

### Method C — Direct browser
You can double-click `index.html`. Most features work directly, but Live Server/Python server is recommended for a cleaner demonstration.

## 5. Project Navigation
- `index.html` — Employee: Raise Request
- `employee.html` — Employee Dashboard / My Requests
- `dashboard.html` — Admin/Support Dashboard
- `tickets.html` — Search, filter and manage all tickets
- `ticket-details.html?id=SR-2026-0001` — Detailed ticket view

## 6. How to Demonstrate the Project
1. Open Raise Request.
2. Enter valid employee information and submit.
3. Confirm the generated Ticket ID.
4. Open Dashboard and confirm KPI counters.
5. Open All Tickets and search the generated ID.
6. Filter by status/priority/category/date.
7. Open the ticket details page.
8. Change status to Assigned or In Progress, assign a support person, add a comment, and save.
9. Mark the ticket Resolved and add resolution notes.
10. Open Employee Dashboard and enter the same Employee ID.
11. Confirm the ticket appears and close it after resolution.
12. Refresh the browser and verify that LocalStorage preserved the ticket.

## 7. Validation
The form validates required fields, email format, employee ID format, subject length, description length, category and priority selection. Validation messages appear inside the page instead of relying only on browser alerts.

## 8. LocalStorage
Storage key: `serviceDeskTickets`

Example ticket object:
```json
{
  "ticketId": "SR-2026-0001",
  "employee": "Rahul Sharma",
  "employeeId": "EMP1024",
  "department": "IT",
  "category": "Software Access",
  "priority": "High",
  "subject": "VPN Access Request",
  "status": "Open",
  "createdAt": "2026-08-19T09:00:00.000Z",
  "assignedTo": "Support Team"
}
```

## 9. SLA Rules
| Priority | Target |
|---|---:|
| Critical | 4 Hours |
| High | 8 Hours |
| Medium | 24 Hours |
| Low | 48 Hours |

The application calculates the expected deadline from `createdAt` and displays `Within SLA` or `Breached`.

## 10. Submission Checklist
- [ ] Complete source code
- [ ] Working CRUD/ticket management
- [ ] LocalStorage
- [ ] Dashboard and charts
- [ ] Search and filters
- [ ] SLA monitoring
- [ ] Form validation
- [ ] Responsive design
- [ ] README
- [ ] Screenshots
- [ ] Short project report

## 11. Notes for Internship Submission
The attachment field stores the selected file name only. It does not upload files to a server because this is a frontend + LocalStorage project. A production system would use a backend database, authentication, server-side validation, secure file storage and role-based access control.
