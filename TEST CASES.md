## Test Case Development

### Functional Test Cases

| Test Case ID | Requirement ID | Description                     | Steps                                                                 | Expected Result                                   |
|--------------|----------------|---------------------------------|-----------------------------------------------------------------------|--------------------------------------------------|
| TC-001       | FR-001         | Guest books room successfully  | 1. Select dates<br>2. Choose room type<br>3. Enter details<br>4. Pay  | Confirmation email sent<br>Room status: Reserved |
| TC-002       | FR-003         | Staff processes check-in        | 1. Scan booking ID<br>2. Verify payment<br>3. Issue key               | Room status: Occupied<br>Housekeeping alerted    |
| TC-003       | FR-005         | Guest modifies reservation      | 1. Login<br>2. Edit dates<br>3. Confirm changes                      | Updated confirmation<br>Inventory adjusted       |
| TC-004       | FR-007         | System prevents overbooking     | 1. Attempt booking for sold-out dates                                | "No availability" warning displayed              |
| TC-005       | FR-009         | Process room service request    | 1. Guest selects service<br>2. Submit request                        | Notification sent to staff<br>Request timestamped|
| TC-006       | FR-012         | Generate occupancy report       | 1. Select date range<br>2. Choose report type<br>3. Export            | PDF/Excel file generated with accurate data      |
| TC-007       | FR-014         | Sync with third-party platform  | 1. Make booking on external site<br>2. Refresh system                | Booking appears in hotel system ≤5s              |
| TC-008       | FR-017         | Process payment failure         | 1. Enter invalid card<br>2. Submit payment                           | Error message<br>Reservation remains unconfirmed |

### Non-Functional Test Scenarios

**Performance Test (NFR-001):**  
- *Objective:* Verify system response under peak load  
- *Test:* Simulate 1,000 concurrent users booking rooms  
- *Success Criteria:*  
  - API response time ≤2s (p95)  
  - Error rate <0.5%  
- *Tools:* JMeter/LoadRunner

**Security Test (NFR-002):**  
- *Objective:* Validate PCI-DSS compliance  
- *Test:* Audit payment processing system  
- *Success Criteria:*  
  - No credit card data stored locally  
  - All transactions use TLS 1.2+  
  - Pass OWASP ZAP scan  
- *Tools:* Nessus, OWASP ZAP

### Traceability Matrix

| Test Case | Covered Stakeholder Concerns             | Success Metric Addressed          |
|-----------|------------------------------------------|------------------------------------|
| TC-001    | Guest booking experience                 | 90% satisfaction rate              |
| TC-004    | Overbooking prevention                   | <5% booking complaints             |
| TC-007    | Third-party platform integration         | 100% sync accuracy                 |
| NFR-001   | System reliability (IT Support)          | 99.9% uptime                       |
| NFR-002   | Payment security (Payment Gateway)       | 99.5% transaction success rate     |


