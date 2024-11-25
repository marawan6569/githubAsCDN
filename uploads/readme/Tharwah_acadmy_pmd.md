# Project Management Dashboard for Tharwah Academy

### Description:
This project is a web application that helps the Tharwah Academy manage their projects, programs, and participants. It provides a dashboard for the admin to view statistics, costs, and revenue. The admin can also add, edit, and delete projects, programs, and participants.

### Models:
<details>

  - User:
    - name
    - email
    - password
    - role
    > Roles: admin, site_manager, project_manager, trainer, program_supervisor, user 
    
---
- Client:
  - name
  - client_type
  - industry
  - contact_name
  - contact_email
  - contact_phone
  - address
  - country
  - city
  > Client Types: B2C, B2B, B2G

---
- Project:
  - name
  - client (FK to Client)
  - manager (FK to User)
  - start date
  - end date
  - status
  - AVG trainers rate
  - AVG Materials rate
  - AVG programs rate
  - planned cost
  - planned revenue

  - calculated fields:
      - duration (auto: end date - start date)
      - programs count (auto)
      - total training days count (auto)
      - Total hours (auto)
      - total finished hours (auto)
      - finished programs (auto)
      - total trainees count (auto)
      - Total trained trainees (auto)
      - actual cost (auto)
      - actual  revenue (auto)
      - actual revenue percentage (auto)
  > Status: planned, active, finished, canceled
---
Program:
  - name
  - description
  - project (FK to Project)
  - trainer (M2M) or static name
  - training days count
  - hours per day
  - trainees count
  - status
  - type(onsite/remote)
  - supervisor (FK to User)
  - selling_price

  - calculated fields:
      - total hours (auto)
      - planned cost (auto)
      - actual cost (auto)
      - revenue (auto)
      - revenue percentage (auto)
    > Status: planned, active, finished, canceled
   
    > Type: onsite, remote
---

CostItem:
  - name
  - description

---

Cost:
  - program
  - cost_item (FK to CostItem)
  - planned_cost
  - actual_cost
  - date
---

</details>

---

### Pages (frontend):
<details>

- dashboard:
  - [x] Projects Overview
  - [x] Statistics
  - [x] costs & revenue chart
  - [x] recently started projects
  - [x] delete project
  - list programs (popup when user clicks on a programs from menu)
  - list participants (popup when user clicks on a participants from menu)
---    
- project:
  - [x] projects list
  - project overview
  - add/edit project
  - programs
    - costs
      - add/remove cost item
---
- user management:
  - users list
  - add/edit user
  - user roles
  - remove user
  - reset password
---

</details>