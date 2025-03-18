## Use Case Specifications for a Hotel Management System

Detailed use case specifications for a hotel management system, formatted with clear success/error paths and alignment to stakeholder needs:

1. Use Case: Book Room
   
    **Actor**: Guest
   
    **Description**: Allows guests to reserve a room online.
   
    **Preconditions**:
    - System is operational
    - Available rooms exist for selected dates.
     
    **Postconditions**:
    - Reservation created with PENDING_PAYMENT status
    - Room inventory temporarily reduced.
     
    **Basic Flow:**
    - Guest selects check-in/check-out dates.
    - System displays available room types with prices.
    - Guest selects room and enters personal details (name, email).
    - System reserves room with 15-minute hold.
    - Guest completes payment via integrated gateway.
    - System sends confirmation email with booking ID.
     
    **Alternative Flows:**
     - No rooms available: System displays "Sold Out" alert.
     - Payment fails: System releases room hold after 15 minutes.

2. Use Case: Check-In
   
     **Actor:** Hotel Staff
   
     **Description:** Registers arriving guests and assigns rooms.
   
     **Preconditions:**
     - Valid booking exists
     - Room is marked READY
     
     **Postconditions:**
     - Room status = OCCUPIED
     - Housekeeping schedule updated
     
     **Basic Flow:**
      - Staff scans booking ID or guest ID.
      - System displays reservation details and payment status.
      - Staff assigns physical room key.
      - System updates room status and alerts housekeeping.
      
     **Alternative Flows:**
      - Unpaid booking: Redirect guest to payment gateway.
      - Early check-in: Charge extra fee if before 3 PM.

3. Use Case: Check-Out
   
      **Actor:** Hotel Staff
   
      **Description:** Finalizes guest departure and processes payments.
   
      **Preconditions:**
      - Guest has active check-in record

      **Postconditions:**
      - Room status = NEEDS_CLEANING
      - Final bill generated

      **Basic Flow:**
      - Staff selects booking from check-out list.
      - System calculates total charges (room + extras).
      - Guest reviews and approves charges.
      - System processes final payment.
      - Staff returns key deposit (if applicable).
      
      **Alternative Flows:**
      - Disputed charges: Flag for manager review.
      - Lost key: Deduct deposit from final bill.

4. Use Case: Modify Reservation
   
      **Actor:** Guest
   
      **Description:** Allows changes to existing bookings.
   
      **Preconditions:**
      - Reservation is in CONFIRMED state.
      - Modification allowed per policy (e.g., >24h before check-in).

      **Postconditions:**
      - Updated reservation details
      - Adjusted room inventory

      **Basic Flow:**
      - Guest logs into account.
      - Selects "Modify Booking" from dashboard.
      - Edits dates/room type.
      - System recalculates pricing.
      - Guest confirms changes.

      **Alternative Flows:**
      - New dates unavailable: Suggest alternative rooms/dates.
      - Price difference: Charge/refund via payment gateway.

5. Use Case: Request Service
   
      **Actor:** Guest
   
      **Description:** Submits housekeeping or concierge requests.
   
      **Preconditions:**
      - Guest is checked in
      - Mobile app/device is connected

      **Postconditions:**
      - Service ticket logged
      - Staff notified

      **Basic Flow:**
      - Guest selects service type (e.g., "Extra Towels").
      - Enters request details.
      - Submits request via mobile app.
      - System assigns ticket to relevant staff.

      **Alternative Flows:**
      - Offline mode: Queue request until connectivity restored.
      - High-priority request: Escalate to supervisor.

6. Use Case: Generate Reports
   
      Actor: Management
      Description: Produces operational/financial analytics.
      Preconditions:
      - User has REPORT_GENERATOR role
      - Historical data exists

      Postconditions:
      - Report saved to dashboard
      - Audit log updated

      Basic Flow:
      - User selects report type (Occupancy/Revenue).
      - Filters by date range and room category.
      - Clicks "Generate Report".
      - System compiles data into PDF/Excel.

      Alternative Flows:
      - Unauthorized access: Log security event and block action.
      - Large dataset: Offer asynchronous email delivery.

7. Use Case: Sync Bookings
Actor: Third-Party Platform
Description: Updates inventory across external booking channels.
Preconditions:

API connection is active

Valid API credentials

Postconditions:

Inventory synchronized across all platforms

Audit trail recorded

Basic Flow:

External platform sends booking request via API.

System validates room availability.

Creates reservation in central database.

Returns confirmation to third party.

Alternative Flows:

2a. Conflict detected: Return "Overbooking Error" code.

3a. Rate mismatch: Apply price parity rules.

8. Use Case: Process Payment
Actor: Payment Gateway
Description: Handles financial transactions securely.
Preconditions:

PCI-DSS compliance verified

Guest payment details on file

Postconditions:

Transaction recorded in ledger

Reservation status updated

Basic Flow:

System sends encrypted payment request.

Gateway validates card details.

Processes transaction.

Returns success/failure code.

Alternative Flows:

2a. Expired card: Notify guest to update payment method.

3a. Fraud detected: Freeze account for review.

Key Design Notes:
Traceability: Each use case maps to 2-3 stakeholder concerns from Assignment 4 (e.g., Sync Bookings → ThirdPartyPlatform's sync accuracy).

Error Handling: Alternative flows address critical failure points identified in stakeholder pain points (overbooking, payment failures).

Atomicity: Postconditions ensure system state consistency (e.g., inventory always matches reservations).

This specification format provides developers with executable requirements while giving testers clear validation criteria. The alternative flows directly address edge cases reported by stakeholders during requirement gathering.
