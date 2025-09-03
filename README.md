# NDT Job Order – Frappe Automation Suite

## Overview
This repository contains the **Job Order design** for managing NDT (Non-Destructive Testing) jobs in Frappe. The Job Order includes all essential sections required for execution, tracking, and reporting while minimizing manual work.

The key focus areas are:  
- Selecting multiple test methods per job.  
- Managing assets and consumables.  
- Assigning manpower/resources.  
- Generating tasks automatically per test method.  
- Logging timesheets for tracking execution.  
- Generating test reports automatically.

---

## Features

### 1. Test Methods
- Multi-select: UT, PT, PAUT, RT, MT, VT, etc.  
- Multiple tests can be chosen for a single Job Order.  

### 2. Assets
- Machines and tools required per test (e.g., UT machine, PAUT system, MPI yoke).  
- Calibration status auto-checked.  

### 3. Consumables
- Materials like dye penetrant, film, couplant, wipes, etc.  
- Stock automatically reserved from inventory.  

### 4. Resources / Manpower
- Assign NDT Level II, III, Helpers, Welders.  
- Auto-check certifications and availability.  

### 5. Tasks
- Auto-generate steps per selected test method.  
- Link tasks with manpower and estimated time.  

### 6. Timesheets
- Employees log time per task .  
- Track planned vs actual time.  
- Auto-calculate overtime.  

### 7. Reports
- Each test method generates its own report (PT, PAUT, UT, etc.).  
- Auto-fill customer, asset, operator, procedure, and acceptance criteria.  
- Technicians only fill measurement/defect details.  
- Auto-sign workflow: Technician → Level II → Level III → Customer.  

---

## Job Order DocType Layout

**Basic Info**  
- Job Order ID  
- Customer  
- Site / Location  
- Start Date & End Date  
- Test Methods (MultiSelect)

**Child Tables**:  

| Section | Fields |
|---------|--------|
| **Assets** | Asset Name, Quantity, Calibration Status, Remarks |
| **Consumables** | Item Name, Quantity, Stock Reserved |
| **Resources ** | Employee, Role, Level |
| **Tasks** | Task Name, Test Method, Manpower, Estimated Time |
| **Timesheets** | Task, Employee, Hours Logged, Overtime |
| **Reports** | Test Method, Status, Signed By |

---

## Automation Highlights

- Auto-create tasks per selected test method.  
- Auto-reserve stock for consumables.  
- Auto-check manpower availability and certifications.  
- Auto-generate reports and link to Job Order.  
- Track planned vs actual time and costs.  

---

## Goal

Create a **simplified, fully functional Work Order** in Frappe that covers execution and reporting for NDT jobs with **minimal manual effort**, while giving supervisors real-time control.

---

## Optional: Diagram (Text-based)
```
Job Order
├── Basic Info
│ ├── Job Order ID
│ ├── Customer
│ ├── Site / Location
│ ├── Start / End Date
│ └── Test Methods (Multi-select)
├── Assets (Child Table)
├── Consumables (Child Table)
├── Resources / Manpower (Child Table)
├── Tasks (Child Table)
├── Timesheets (Child Table)
└── Reports (Child Table)
```
## License

This project is licensed under the **MIT License** – see the [LICENSE](./LICENSE) file for details.  

---

## Company

**SPA InnoVision Pvt. Ltd.**  
📍 Location: India  
🌐 Website: [https://spainnovision.com/]  
📧 Email: spainnovision@gmail.com  

---
