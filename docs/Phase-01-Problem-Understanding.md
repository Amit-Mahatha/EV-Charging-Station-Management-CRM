# Phase 1: Problem Understanding & Industry Analysis  

👉 **Goal:** Understand the problem domain (EV charging), identify requirements, and map industry use cases before building the CRM.  

---

## 1. Requirement Gathering  

**Example requirements:**  
- Customers should be able to:  
  - Search for nearby charging stations.  
  - View real-time slot availability.  
  - Book slots and make online payments.  
- Admin/Station Managers should be able to:  
  - Add/manage charging stations.  
  - Track utilization and revenue.  
  - Monitor faulty chargers and raise maintenance tickets.  
- Maintenance Staff should be able to:  
  - Receive notifications of faulty equipment.  
  - Update repair status.  

---

## 2. Stakeholder Analysis  

- **Admin (CRM Owner)** → Manages setup, monitors all stations, generates reports.  
- **Station Manager** → Handles daily operations, manages bookings, and oversees payments.  
- **Customer (EV Owner)** → Searches, books, pays, and charges their vehicle.  
- **Maintenance Staff** → Fixes faulty stations, logs service requests, updates status.  
- **Finance Team** → Reviews billing, revenue, and prepares reports.  

---

## 3. Business Process Mapping  

**Booking flow:**  
Customer searches station → Views available slots → Books a slot → Pays → Slot reserved → Charging complete → Usage & revenue logged → Reports generated.  

**Maintenance flow:**  
Station flagged faulty → Maintenance Staff notified → Repair completed → Status updated → Station available again.  

---

## 4. Industry-Specific Use Case Analysis  

- **Challenges in EV Industry:**  
  - High demand but limited charging infra.  
  - Need for real-time slot visibility.  
  - Multiple charger types (slow/AC, fast/DC).  
  - Maintenance downtime impacts customers.  

- **Our CRM Solution:**  
  - Optimize slot management & avoid double booking.  
  - Integrate payments.  
  - Provide dashboards & reports.  
  - Include maintenance tracking.  

---

## 5. AppExchange Exploration  

- Some EV/IoT apps exist, but they focus mainly on **charger hardware monitoring**.  
- Few CRMs focus on **customer booking + revenue tracking**.  
- **Decision:** Build a **custom Salesforce CRM** for EV Charging.  

---

✅ **Deliverable for Phase 1:**  
- Clear requirements.  
- Stakeholder mapping.  
- Business process flows.  
- Industry-specific challenges and solution plan.  
