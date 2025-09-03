# InspectO Job Order

## Overview
This repository contains the **Job Order module** for managing NDT (Non-Destructive Testing) projects inside Frappe/ERPNext.  

The purpose of this module is to simplify how NDT jobs are planned, executed, and reported.  
Instead of handling everything manually, this Job Order automatically manages:  
- Which tests need to be performed (UT, PT, PAUT, RT, MT, VT, etc.).  
- What assets and consumables are required.  
- Which manpower/resources are assigned.  
- What tasks need to be completed step by step.  
- How much time is planned vs. actually spent.  
- How reports are generated and approved.  

In short, it works like a **complete project dashboard for NDT jobs**, where supervisors or manager get real-time control, and technicians can directly log their work.  

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
- Report Status Tracking: Monitor every report (PT, UT, PAUT, etc.) with clear statuses like - Draft, In Progress, In Review, Approved, Rejected, and Submitted to Customer.


---

## Job Order DocType Layout

**Basic Info**  
- Job Order ID  
- Customer  
- Site / Location  
- Start Date & End Date  
- Supervisors  

**Child Tables**:  

| Section | Fields |
|---------|--------|
| **Test Methods** | Test Name |
| **Assets** |Test, Asset Name, Calibration Status, Location,Calibration Due |
| **Consumables** | Test, Item Name, Quantity, UOM, Consumable Expiry Date |
| **Resources ** |Test, Resource, Employee, Role, Resource Type, Price |
| **Tasks** | Task Name, Task Owner, Task Start Date, Task End Date, Task Supervisor, Billable, Status |
| **Documents** | Title, Document |
| **Reports** | Test, Supervisor, Technician, Status, Report, Create, View, Date Of Test |

---

## Support DocTypes

The Job Order depends on a few **supporting DocTypes** to provide data automatically.  

| DocType | Purpose |
|---------|---------|
| **Employee Certification** | Stores employee skills, NDT Level (I/II/III), certification validity, and expiry dates. Used for auto-checking manpower eligibility. |
| **Test Method Master** | Defines available test methods (UT, PT, PAUT, RT, MT, VT, etc.) with standards, codes, and acceptance criteria. <br>➡ Includes child tables for **Assets** (required instruments with calibration details) and **Consumables** (required items with expiry details). These auto-populate into the Job Order. |
| **Task Configuration** | Pre-defined task templates per test method (e.g., PT → Surface Prep → Apply Penetrant → Dwell → Developer → Interpretation). Auto-generates Job Order tasks. |

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
├── Test Methods (Child Table)
├── Assets (Child Table)
├── Consumables (Child Table)
├── Resources  (Child Table)
├── Tasks (Child Table)
├── Documents (Child Table)
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
