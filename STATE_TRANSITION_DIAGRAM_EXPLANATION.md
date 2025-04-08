# UML_STATE_TRANSITION_DIAGRAMS_EXPLANATION.md

## Overview

This document explains the UML state transition diagrams created for the Hotel Management System.
Each object selected plays a critical role in managing hotel operations.
The diagrams represent the dynamic behavior of these objects,
illustrating how they change states in response to internal or external events.

---

## 1. Booking Object

### Key States:

- Initiated
- Confirmed
- Checked-In
- Checked-Out
- Canceled

### Explanation:

The booking object represents the lifecycle of a room reservation. A booking transitions from "Initiated" to "Confirmed" when the user completes the reservation. It moves to "Checked-In" and eventually "Checked-Out" based on check-in/check-out processes. Users can cancel before checking in.

### Linked to Functional Requirement:

- FR-001: Users must be able to book rooms.
- FR-005: Users must be able to cancel bookings.

---

## 2. Payment Object

### Key States:

- Pending
- Processed
- Failed
- Refunded

### Explanation:

Payment status updates depending on transaction success. Guard conditions validate the card or bank info before marking as "Processed." Failed transactions allow retry. Refunds occur upon booking cancellation.

### Linked to Functional Requirement:

- FR-003: Support secure payment processing.

---

## 3. Guest Account Object

### Key States:

- Registered
- Active
- Suspended
- Deleted

### Explanation:

Guest accounts are created upon registration. Accounts may be suspended for violations and can also be deleted upon request.

### Linked to Functional Requirement:

- FR-002: Guest registration and profile management.

---

## 4. Room Object

### Key States:

- Available
- Reserved
- Occupied
- Under Maintenance

### Explanation:

A room transitions based on booking and check-in statuses. Rooms go under maintenance after checkout if flagged by housekeeping.

### Linked to Functional Requirement:

- FR-004: Room availability management.

---

## 5. Check-In Process Object

### Key States:

- Not Started
- In Progress
- Completed
- Failed

### Explanation:

Represents the process lifecycle from when a guest arrives to when the system confirms check-in.

### Linked to Functional Requirement:

- FR-006: Digital check-in capability.

---

## 6. Reservation Request Object

### Key States:

- Submitted
- Approved
- Declined

### Explanation:

This object tracks requests made by guests. Staff or system reviews determine transitions.

### Linked to Functional Requirement:

- FR-001 and FR-007: Reservation handling with approval logic.

---

## 7. Housekeeping Status Object

### Key States:

- Not Started
- In Progress
- Completed
- Rejected

### Explanation:

Housekeeping staff update room cleanliness statuses through the app. Admin may reject incorrect submissions.

### Linked to Functional Requirement:

- FR-008: Housekeeping workflow tracking.

---

## 8. Staff Account Object

### Key States:

- Created
- Verified
- Active
- Suspended

### Explanation:

Represents lifecycle of a hotel staff account, including verification and role-based access activation.

### Linked to Functional Requirement:

- FR-009: Staff user account management.

---

## Summary

These state transition diagrams contribute to a better understanding of object lifecycle behavior.
They directly support system functional requirements and align with Agile development goals for clear, modular design.
