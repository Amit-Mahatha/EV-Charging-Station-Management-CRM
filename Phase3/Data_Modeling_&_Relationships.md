# Phase 3: Data Modeling & Booking Flow (EV Charging Station CRM)

## Goal

Build the data structure and booking automation for the EV Charging Station Management CRM project.

---

## 1. Objects

### Standard Object

* **Contact**: Represents the customer.

### Custom Objects

* **ChargingStation\_\_c**
* **Charger\_\_c**
* **Booking\_\_c**
* **Maintenance\_\_c**

### Fields

**ChargingStation\_\_c**

* Name
* Location
* Status (Active/Inactive)

**Charger\_\_c**

* Model
* Serial Number
* Daily Rate / Hourly Rate
* Status (Available/In Use/Maintenance)
* Lookup → ChargingStation\_\_c

**Booking\_\_c**

* Start DateTime
* End DateTime
* Total Amount
* Status (Confirmed/Cancelled)
* Lookup → Charger\_\_c
* Lookup → Contact

**Maintenance\_\_c**

* Date
* Description
* Technician
* Cost
* Lookup → ChargingStation\_\_c

---

## 2. Relationships

* **Charger ↔ Booking** → Lookup (bookings don’t own chargers)
* **Booking ↔ Contact** → Lookup
* **Maintenance ↔ ChargingStation** → Lookup

*Junction objects are not required for Phase 3.*

---

## 3. Page Layouts

* ChargingStation page shows related chargers and booking history.
* Booking page shows related chargers and customer.
* Maintenance page shows related ChargingStation.

## 4. Compact Layouts (Mobile)

* ChargingStation: Name, Location, Status
* Charger: Model, Serial Number, Status
* Booking: Start DateTime, End DateTime, Status

---

## 5. Schema Builder

* Visual representation of objects and relationships.
* Make sure **Maintenance\_\_c** is created and linked to ChargingStation\_\_c via Lookup.
* Enable objects in Schema Builder filter list if not visible.

---

## 6. Booking Flow (Screen Flow)

### Navigation Steps

1. **Setup → Flows → New Flow → Screen Flow → Create**
2. Open Toolbox → Elements tab.
3. **Step 1 – Select Station**

   * Screen element → Dropdown from `ChargingStation__c` where Status = Active.
4. **Step 2 – Select Date & Time**

   * Screen element → Start DateTime, End DateTime fields.
   * Decision element → End >= Start.
5. **Step 3 – Get Available Chargers**

   * Get Records → `Charger__c` → filter by selected station and availability.
6. **Step 4 – Select Charger**

   * Screen element → Dropdown from Get Records results.
   * Optional Decision → no chargers available → Error screen.
7. **Step 5 – Select Customer**

   * Screen element → Lookup Contact.
8. **Step 6 – Confirm Booking**

   * Screen element → Display summary + Confirm/Cancel buttons.
9. **Step 7 – Create Booking Record**

   * Create Records → Booking\_\_c → map all fields.
10. **Step 8 – Send Confirmation Email**

    * Action → Send Email to Contact using template.
11. **Step 9 – Success Screen**

    * Screen element → Display success message.
12. **Save & Activate**

    * Flow Label: `EV Booking Flow` → Activate.

---

## 7. Record-Triggered Flow (Background Automation)

* Trigger: Booking\_\_c → created or updated → after save.
* Get Records → Check overlapping bookings.
* Decision → If overlap exists → fault path; else continue.
* Update Records → Update Charger/Station totals if needed.
* Optional → Send confirmation email.
* Save & Activate → Flow Label: `Booking Automation Flow`

---

## ✅ Phase 3 Deliverables

1. Custom objects with fields and relationships (ChargingStation, Charger, Booking, Maintenance).
2. Page layouts and compact layouts.
3. Schema Builder updated with all objects.
4. Screen Flow for booking wizard.
5. Record-Triggered Flow for validation and automation.

