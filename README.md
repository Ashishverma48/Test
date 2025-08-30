# AccuMatLab  

**AccuMatLab** is a purpose-built **Laboratory Information Management System (LIMS)** built on the **Frappe Framework / ERPNext**.  
It is designed for **testing & inspection laboratories** to streamline operations, ensure **ISO/NABL compliance**, and deliver **professional, standards-based test reports**.  

## 📦 Requirements  

![Frappe](https://img.shields.io/badge/Frappe-v15-blue) 
![ERPNext](https://img.shields.io/badge/ERPNext-v15-orange) 
![HRMS](https://img.shields.io/badge/HRMS-v15-red) 
![India Compliance](https://img.shields.io/badge/India%20Compliance-v15-red)  

AccuMatLab requires the following apps to be installed:  

- **Frappe Framework v15**  
- **ERPNext**  
- **HRMS**  
- **India Compliance**  


---

## 🚀 Key Features  

- 📊 **End-to-End Workflow**: From Sales Orders → Lab Orders → Sample Registration → Test Execution → Review/Approval → Reporting  
- ✅ **ISO/NABL Compliance**: Built-in workflows, audit trails, and role-based approvals  
- ⚡ **Automation**: Auto-calculations, acceptance vs. specification checks, and report generation with QR verification  
- 🧾 **Customizable Reports**: NABL-ready templates with customer logo and test details  
- 🔍 **Real-Time Tracking**: AML Track for logging every stage of test execution  
- 🔒 **Role-Based Permissions**: Lab Tech, Reviewer (L2), Approver (L3/QA)  

---
---

## 🏗️ Installation  

### Get the app

```bash
bench get-app --branch version-15 https://github.com/ircengg/accumatlab.git
```
### Install the app

```bash
bench --site yoursite install-app accumatlab
```
### Setup Requirements

```bash
bench setup requirements
bench migrate
bench restart
```

## 🔄 Workflow Overview  

### Masters Setup  
Define Material Groups, Test Groups & Names, Test Specs (limits), Test Protocols (standards), Test Space Table (properties, units, precision), and AML Task Configuration.  

### Order Creation  
Sales Order → AML Order .  

### Sample Creation  
AML Order → Capture Grade, Material of Construction, Sample Description & Details, Dimensions, Attachments, and Required Tests.  
Once Sample is created, AML Task is automatically generated.  

### Test Creation  
AML Tests are created and linked with Protocol & Spec.  

### Execution  
Technicians perform tests and record raw values.  
Progress is tracked in AML Task.  

### Validation & Review  
Automatic calculations + acceptance check vs. Test Spec.  

### Report Generation  
System generates a NABL- or Non-NABL compliant report with QR verification link.  

---

## 🧩 Additional Setup Requirements  

Before using AccuMatLab, complete the following setup steps:  

- [x] Create **3 Employees**  
- [x] Create **Shift Type** and link it to Employees (set default Shift Type)  
- [x] Create **Holiday List** and assign it to Company  
- [x] Create **3 Users** with roles: `AML Manager`, `AML Incharge`, `AML Technician` (link with Employees & set permissions)  
- [x] Configure **Authorized Signatory** in AML Test Group  
- [x] Create **Test Services Items**  
- [x] Create **Customer & Address** (link Address to Customer)  
- [x] Fill **User in AML Task Configuration** and Authorized Signatory in AML Test Group  
- [x] Create **AML Orders** → Independent AML Task auto-created  
- [x] Create **AML Sample** → Independent AML Task auto-created  
- [x] Create **AML Test** (Test Group must be selected in Test Name)  
- [x] Update Task → Task auto-created  
- [x] Create **AML Test Report**  
- [x] Submit & Check Print (NABL/Non-NABL compliant)  

## 🛠️ Troubleshooting  

### App not showing in Desk  
```bash
bench --site yoursite list-apps
```
If missing, re-install app.

### App errors after update  
```bash
bench migrate
bench restart
```
### UI/Report not loading properly  
```bash
bench build
bench restart
```
### Bench restart issues
```bash
bench stop && bench start
# OR
sudo supervisorctl restart all

```
## 📧 Contact  

**SPA Innovision Pvt Ltd**  
📩 spainnovision@gmail.com  

---

## 📜 License  

MIT License  


