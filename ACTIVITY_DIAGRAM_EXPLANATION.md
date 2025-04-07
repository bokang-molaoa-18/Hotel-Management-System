# Activity Diagram Explanation: Hotel Management System  

## **Introduction**  
Activity diagrams are used to model the step-by-step workflows of various processes within the hotel management system. Below are explanations for several key workflows, including check-in, room cleaning, payment processing, and more.

---

## **1. Check-In Process**  
### **Actors Involved**  
- **Guest**  
- **Receptionist**  
- **System** (Hotel Management Software)  

### **Workflow Steps**  
1. **Guest Arrival**:  
   - Guest arrives at the hotel and approaches the reception desk.  
2. **Booking Verification**:  
   - Receptionist retrieves booking details using the guest’s name/ID.  
3. **ID Validation**:  
   - Guest provides government-issued ID for verification.  
4. **Room Assignment**:  
   - **If ID is valid**:  
     - System assigns an available room and updates the database.  
     - Receptionist confirms room number and amenities.  
5. **Key Handover**:  
   - Guest receives a physical/digital room key.  
6. **Process Completion**:  
   - Guest proceeds to the room.  

### **Stakeholder Alignment**  
This workflow addresses the following stakeholder concerns:  
- **Guests**: Streamlines check-in to reduce wait times (from **User Story-001**).  
- **Reception Staff**: Automated room assignment minimizes manual errors (Requirement **NFR-003**).  
- **Management**: Real-time system updates ensure accurate occupancy tracking (Requirement **FR-002**).  

### **Functional Requirement (FR) Mapping**  
| **Step**               | **Functional Requirement** |  
|-------------------------|-----------------------------|  
| ID Validation           | FR-004 (Guest Authentication) |  
| Room Assignment         | FR-005 (Room Availability Management) |  
| Key Handover            | FR-007 (Security Compliance) |  

---

## **2. Room Cleaning Workflow**  
### **Actors Involved**  
- **Housekeeping Staff**  
- **System** (Hotel Management Software)  

### **Workflow Steps**  
1. **Room Status Update**:  
   - System marks room as available for cleaning after guest check-out.  
2. **Cleaning Assignment**:  
   - Housekeeping staff receive notification of rooms to clean.  
3. **Cleaning Process**:  
   - Staff clean and inspect the room.  
4. **Inspection**:  
   - Quality check to ensure cleanliness standards are met.  
5. **Room Availability Update**:  
   - System updates room status to "Available" for new bookings.  

### **Stakeholder Alignment**  
This workflow ensures efficient room turnover and maintains high cleanliness standards, aligning with **User Story-006** (Housekeeping Efficiency).  

### **FR Mapping**  
| **Step**               | **Functional Requirement** |  
|-------------------------|-----------------------------|  
| Room Status Update       | FR-006 (Room Status Management) |  
| Inspection               | FR-008 (Quality Assurance) |  

---

## **3. Payment Processing Workflow**  
### **Actors Involved**  
- **Guest**  
- **Receptionist**  
- **System** (Hotel Management Software)  

### **Workflow Steps**  
1. **Invoice Generation**:  
   - System generates invoice based on guest’s stay details.  
2. **Guest Review**:  
   - Guest reviews charges for accuracy.  
3. **Payment Processing**:  
   - Guest pays using preferred method (e.g., credit card, cash).  
4. **Payment Confirmation**:  
   - System updates payment status and sends receipt to guest.  

### **Stakeholder Alignment**  
This workflow ensures secure and efficient payment processing, addressing **User Story-004** (Payment Gateway Integration).  

### **FR Mapping**  
| **Step**               | **Functional Requirement** |  
|-------------------------|-----------------------------|  
| Invoice Generation     | FR-009 (Billing Management) |  
| Payment Processing      | FR-010 (Payment Security) |  

---

## **4. Maintenance Handling Workflow**  
### **Actors Involved**  
- **Guest**  
- **Maintenance Staff**  
- **System** (Hotel Management Software)  

### **Workflow Steps**  
1. **Issue Reporting**:  
   - Guest reports maintenance issue via phone or system portal.  
2. **Issue Assignment**:  
   - System assigns issue to maintenance staff.  
3. **Repair Process**:  
   - Staff address the issue.  
4. **Resolution Confirmation**:  
   - System updates issue status to "Resolved" after confirmation from guest.  

### **Stakeholder Alignment**  
This workflow ensures prompt resolution of maintenance issues, enhancing guest satisfaction (from **User Story-007**).  

### **FR Mapping**  
| **Step**               | **Functional Requirement** |  
|-------------------------|-----------------------------|  
| Issue Reporting          | FR-011 (Guest Feedback) |  
| Resolution Confirmation  | FR-012 (Maintenance Tracking) |  

---

## **5. Reservation Cancellation Workflow**  
### **Actors Involved**  
- **Guest**  
- **Receptionist**  
- **System** (Hotel Management Software)  

### **Workflow Steps**  
1. **Cancellation Request**:  
   - Guest requests cancellation via phone or email.  
2. **Cancellation Verification**:  
   - Receptionist verifies cancellation request details.  
3. **Refund Processing**:  
   - System processes refund according to hotel policy.  
4. **Cancellation Confirmation**:  
   - System updates booking status to "Cancelled" and notifies guest.  

### **Stakeholder Alignment**  
This workflow ensures fair and timely refunds, aligning with **User Story-008** (Cancellation Policy).  

### **FR Mapping**  
| **Step**               | **Functional Requirement** |  
|-------------------------|-----------------------------|  
| Cancellation Request    | FR-013 (Cancellation Policy) |  
| Refund Processing       | FR-014 (Refund Management) |  

---

## **6. Invoice Generation Workflow**  
### **Actors Involved**  
- **System** (Hotel Management Software)  
- **Accounting Staff**  

### **Workflow Steps**  
1. **Invoice Creation**:  
   - System generates invoice based on guest’s stay and services used.  
2. **Invoice Review**:  
   - Accounting staff review invoice for accuracy.  
3. **Invoice Dispatch**:  
   - System sends invoice to guest via email or postal mail.  

### **Stakeholder Alignment**  
This workflow ensures accurate and timely billing, addressing **User Story-009** (Invoice Accuracy).  

### **FR Mapping**  
| **Step**               | **Functional Requirement** |  
|-------------------------|-----------------------------|  
| Invoice Creation        | FR-015 (Invoice Generation) |  
| Invoice Review          | FR-016 (Invoice Accuracy) |  

---

## **7. Staff Shift Management Workflow**  
### **Actors Involved**  
- **Staff**  
- **Manager**  
- **System** (Hotel Management Software)  

### **Workflow Steps**  
1. **Shift Scheduling**:  
   - Manager schedules staff shifts using the system.  
2. **Shift Assignment**:  
   - System notifies staff of their assigned shifts.  
3. **Shift Swap Request**:  
   - Staff can request shift swaps via the system.  
4. **Swap Approval**:  
   - Manager approves or rejects shift swap requests.  

### **Stakeholder Alignment**  
This workflow streamlines staff scheduling and communication, enhancing operational efficiency (from **User Story-010**).  

### **FR Mapping**  
| **Step**               | **Functional Requirement** |  
|-------------------------|-----------------------------|  
| Shift Scheduling        | FR-017 (Staff Scheduling) |  
| Shift Swap Request      | FR-018 (Staff Flexibility) |  

---

## **8. Guest Check-Out Workflow**  
### **Actors Involved**  
- **Guest**  
- **Receptionist**  
- **System** (Hotel Management Software)  

### **Workflow Steps**  
1. **Check-Out Request**:  
   - Guest requests check-out at the reception desk.  
2. **Room Inspection**:  
   - Receptionist inspects the room for damages.  
3. **Invoice Settlement**:  
   - Guest settles any outstanding charges.  
4. **Check-Out Confirmation**:  
   - System updates guest status to "Checked Out" and releases room for new bookings.  

### **Stakeholder Alignment**  
This workflow ensures efficient check-out processes and accurate billing, aligning with **User Story-011** (Check-Out Efficiency).  

### **FR Mapping**  
| **Step**               | **Functional Requirement** |  
|-------------------------|-----------------------------|  
| Room Inspection         | FR-019 (Room Condition Tracking) |  
| Invoice Settlement      | FR-020 (Payment Completion) |  

---

