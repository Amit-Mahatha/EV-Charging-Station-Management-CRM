# Phase 5: Apex Programming (Developer)

👉 **Goal**: Automate logic with Apex and make the system intelligent.

---

## 1. Apex Class – BookingService
- Create a class `BookingService` for reusable logic:
  - Auto-calculate **Total Cost** = `Daily Rate × No. of Days`.
  - Check if a **Charger is available** before confirming booking.

---

## 2. Apex Trigger – Prevent Overlaps
- Create a Trigger on **Booking (Booking__c)**:
  - On insert/update, prevent overlapping bookings for the same Charger.
  - Confirm booking only if Charger is free.

---

## 3. Trigger Handler Pattern
- Use a `BookingTriggerHandler` class instead of writing logic inside the trigger.
- This makes the trigger **clean** and easy to maintain.

---

## 4. SOQL Queries – Availability Check
- Query Chargers with status = `Available`.
  ```apex
  SELECT Id, Name, Status__c 
  FROM Charger__c 
  WHERE Status__c = 'Available'

