# Phase 2: Org Setup & Configuration – EV Charging Station Management CRM

## 🎯 Goal
Prepare Salesforce Developer Org with company info, roles, profiles, users, security settings, and app navigation for the EV Charging CRM project.

---

## 1) Salesforce Developer Org Setup
- Signed up for **Salesforce Developer Edition Org**.  
- Enabled **My Domain** for Lightning Web Components and custom branding.  

---

## 2) Company Profile
- Company Name: **EV Charging Station Management CRM**  
- Time Zone: **Asia/Kolkata (GMT+05:30)**  
- Currency: **INR**  
- Fiscal Year: **Standard (Jan–Dec), Based on Ending Month**  

---

## 3) Business Hours & Holidays
- Created **Station Hours** (08:00 AM – 09:00 PM, Monday–Saturday).  
- Marked as **Active** and set as **Default Business Hours**.  
- Added **Holiday records** (e.g., Independence Day).  
- Linked holidays to Station Hours.  

---

## 4) Roles (Role Hierarchy)
- Defined a hierarchy to manage visibility:
  - **Admin**
    - **Station Manager**
      - **Customer Agent**
      - **Maintenance Staff** (role created but no user yet due to 3-user limit).  

---

## 5) Users
- Created 3 users:  
  - **System Admin** (full access).  
  - **Station Manager**.  
  - **Customer Agent**.  
- Did not create Maintenance Staff user (license limitation).  

---

## 6) Profiles
- Cloned and customized profiles:  
  - **Station Manager Profile** → Full CRUD on custom objects.  
  - **Customer Agent Profile** → Read on Stations/Chargers, Create/Edit on Bookings.  
  - **Maintenance Staff Profile** → Created but not assigned to a user.  

---

## 7) Permission Sets
- Created **Reports Access** permission set for extra reporting privileges without modifying profiles.

---

## 8) Org-Wide Defaults (OWD)
- Charging Station: **Public Read Only**.  
- Charger: **Public Read Only**.  
- Booking: **Private**.  
- Maintenance: **Controlled by Parent (Station)**.  

---

## 9) Sharing Rules
- Created rule: **Share_Booking_with_Managers**.  
  - Owned by Role: Customer Agent.  
  - Shared with Role: Station Manager.  
  - Access: **Read/Write**.  

---

## 10) Login Access Policies
- **Customer Agent Profile**: Login Hours restricted to **08:00–22:00**.  
- Configured **Login IP Ranges** (optional, for office network).  
- **Admin Profile**: No restrictions.  

---

## 11) Utility Items
- Added to Utility Bar:
  - **Notes** (quick notes about customers or bookings).  
  - **Recent Items** (fast access).  
  - **History** (navigation back).  

---

## 12) Navigation Items (Lightning App)
- Created **EV Charging CRM Lightning App**.  
- Added navigation items (tabs):
  - **Home**  
  - **Charging Stations** (custom object tab)  
  - **Chargers** (custom object tab)  
  - **Bookings** (custom object tab)  
  - **Maintenance** (custom object tab)  
  - **Contacts** (standard object)  

---

## ✅ Current Status
- Completed Phase 2.  
- Created all roles, 3 users, profiles, permission sets, OWD, sharing rules, login restrictions, and Lightning App with navigation items.  


---

