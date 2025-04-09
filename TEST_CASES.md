## Test Case Development

### Functional Test Cases

## Test Cases for Hotel Management System

| Test Case ID | Requirement ID | Description                     | Steps                                                                 | Expected Result                                   | Actual Result                                                                 | Status (Pass/Fail) |
|--------------|----------------|---------------------------------|-----------------------------------------------------------------------|--------------------------------------------------|------------------------------------------------------------------------------|--------------------|
| TC-001       | FR-001         | Guest books a room              | 1. Select dates<br>2. Choose room type<br>3. Enter guest details<br>4. Confirm payment | Confirmation email sent<br>Room status: Reserved | Email sent in 5s<br>Room status updated successfully                          | **Pass**           |
| TC-002       | FR-003         | Staff processes check-in         | 1. Scan booking ID<br>2. Verify payment status<br>3. Assign room key  | Room status: Occupied<br>Housekeeping notified   | Room status updated<br>Housekeeping alert triggered                           | **Pass**           |
| TC-003       | FR-005         | Guest modifies reservation       | 1. Log in to account<br>2. Edit booking dates<br>3. Resubmit payment  | Updated confirmation sent<br>Inventory adjusted  | Confirmation resent<br>Inventory updated correctly                           | **Pass**           |
| TC-004       | FR-007         | System prevents overbooking      | 1. Attempt to book already reserved dates                            | "No availability" error displayed                | Error displayed<br>Booking attempt blocked                                      | **Pass**           |
| TC-005       | FR-009         | Guest requests room service      | 1. Select service type<br>2. Submit request                          | Request logged<br>Staff alert triggered          | Request logged<br>Alert sent to staff                                          | **Pass**           |
| TC-006       | FR-012         | Generate financial report        | 1. Select date range<br>2. Filter by room type<br>3. Export as PDF    | Report generated with accurate revenue data      | Report generated<br>Revenue figures matched historical data                   | **Pass**           |
| TC-007       | FR-014         | Third-party booking sync          | 1. Create booking on external platform<br>2. Refresh system          | Booking appears in system ≤3s                   | Booking synced in 2s                                                         | **Pass**           |
| TC-008       | FR-017         | Process payment failure           | 1. Enter invalid card details<br>2. Submit payment                   | "Payment failed" error<br>Reservation not created | Error displayed<br>Reservation not created                                      | **Pass**           |


### Non-Functional Test Scenarios

**Performance Test (NFR-001):**  
- **Objective:** Verify system response under peak load  
- **Steps:**  
  1. Simulate 1,000 concurrent users booking rooms  
  2. Monitor API response times  
- **Success Criteria:**  
  - 95% of responses ≤2 seconds  
  - Error rate <1%  
- **Actual Result:**  
  - 98% responses ≤2s<br>0.2% error rate  
- **Status:** **Pass**  

**Security Test (NFR-002):**  
- **Objective:** Validate PCI-DSS compliance  
- **Steps:**  
  1. Audit payment gateway integration  
  2. Scan for vulnerabilities  
- **Success Criteria:**  
  - No credit card data stored in logs  
  - All transactions use TLS 1.3 encryption  
- **Actual Result:**  
  - No sensitive data found in logs<br>TLS 1.3 enforced  
- **Status:** **Pass** 


### Traceability Matrix

| Test Case | Covered Stakeholder Concerns             | Success Metric Addressed          |
|-----------|------------------------------------------|------------------------------------|
| TC-001    | Guest booking experience                 | 90% satisfaction rate              |
| TC-004    | Overbooking prevention                   | <5% booking complaints             |
| TC-007    | Third-party platform integration         | 100% sync accuracy                 |
| NFR-001   | System reliability (IT Support)          | 99.9% uptime                       |
| NFR-002   | Payment security (Payment Gateway)       | 99.5% transaction success rate     |


 
