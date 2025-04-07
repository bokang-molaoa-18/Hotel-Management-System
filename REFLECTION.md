# Reflection

**Challenges Faced in Balancing Stakeholder Needs**

1. Conflicting Priorities:
   - Guests prioritize ease of use and quick responses, while management focuses on operational efficiency and reporting capabilities.
   - Balancing these needs required prioritizing features that benefit both groups (e.g., real-time updates).

2. Technical Constraints:
   - Integrating third-party booking platforms posed challenges due to varying APIs and data formats.
   - Ensuring seamless integration required additional development time and testing.

3. Security vs Usability:
   - Implementing robust security measures (e.g., encryption) sometimes conflicted with usability goals (e.g., quick access).
   - Compromises were made by streamlining authentication processes while maintaining security standards.
     
4. Scalability Concerns:
   - Designing a scalable architecture that supports peak traffic without over-engineering was challenging.
   - Load testing helped identify bottlenecks early in development.
     
By addressing these challenges iteratively using Agile methodology, we ensured that stakeholder needs were met without compromising on quality or performance.
This document provides a comprehensive overview of stakeholder concerns, functional/non-functional requirements, 
and a reflection on challenges faced during requirements elicitation for the Hotel Management System project.

# Reflection: Challenges in Translating Requirements to Use Cases and Tests

## 1. Ambiguity in Natural Language Requirements  
Stakeholders often describe needs in broad, subjective terms. For example, the requirement that "guests should experience a seamless booking process" required significant interpretation. To operationalize "seamless," we decomposed it into measurable components:  

- Step-by-step flows (e.g., date selection → room choice → payment).  
- Performance metrics (e.g., booking completion time ≤2 minutes).  
- Error handling (e.g., payment failure recovery).  

Resolving ambiguity required multiple iterations with stakeholders to align on what "seamless" truly meant. Without collaboration, the **Book Room** use case might have overlooked critical edge cases like temporary room holds or payment retries.  

## 2. Bridging Technical and Non-Technical Perspectives  
Stakeholders like hotel staff or guests often lack technical expertise, whereas developers need precise specifications. For example, the requirement for **"real-time inventory sync"** with third-party platforms (e.g., Booking.com) seemed straightforward to stakeholders but involved complex technical decisions:  

- **API Design**: Choosing between REST or WebSocket for sync frequency.  
- **Error Handling**: Defining how to resolve booking conflicts (e.g., overbooking).  
- **Data Formats**: Standardizing room descriptions across platforms.  

The **Sync Bookings** use case needed to balance technical details while remaining understandable to non-technical stakeholders.  

## 3. Anticipating Unstated Requirements  
Stakeholders often overlook edge cases or assume system capabilities. The **Check-In** use case, for instance, needed to handle scenarios like:  

- **Early/Late Check-Ins**: Charging fees or adjusting housekeeping schedules.  
- **Unpaid Reservations**: Redirecting guests to payment gateways without causing delays.  

These scenarios were missing from initial requirements but surfaced during use case specification. Similarly, non-functional requirements like **"99.9% uptime"** necessitated stress-testing scenarios (e.g., simulating 1,000 concurrent users), which stakeholders rarely consider during requirement gathering.  

## 4. Ensuring Traceability  
Maintaining alignment between requirements, use cases, and tests proved challenging. For example:  

- The stakeholder metric **"90% guest satisfaction"** translated into test cases validating booking speed (**TC-001**) and error recovery (**TC-008**).  
- The **Third-Party Platform**’s need for **"100% sync accuracy"** required API performance tests (**NFR-001**) and functional tests for booking conflicts (**TC-004**).  

Without a **traceability matrix**, critical requirements risked being untested or misinterpreted.  

## 5. Balancing Detail and Complexity  
Over-specifying use cases can create rigidity, while under-specifying leads to ambiguity. The **Generate Reports** use case illustrates this:  

- **Stakeholder Need**: "Accessible financial insights."  
- **Detailed Specification**: Filters (date ranges, room types), export formats (PDF/Excel), and role-based access controls.  

Balancing core functionality with advanced features (e.g., custom dashboards) required **prioritization and phased implementation**.  

## 6. Validating Non-Functional Requirements  
Non-functional needs like **security ("PCI-DSS compliance")** or **performance ("response time ≤2s")** were difficult to translate into tests. For example:  

- **Security Tests**: Simulating attacks (e.g., SQL injection) on payment endpoints, often overlooked until post-deployment.  
- **Performance Tests**: Infrastructure decisions (e.g., server scaling) impacting response times.  

These tests required collaboration with **IT teams** to define realistic thresholds (e.g., **95% of API responses under 2 seconds**).  

## 7. Managing Evolving Requirements  
Stakeholder reviews often led to evolving requirements. For instance, the **Modify Reservation** use case initially allowed date changes but later required **price recalculation logic and refund workflows**. Each change necessitated updates to use case steps (e.g., **Step 4: "System recalculates pricing"**) and test cases (e.g., **validating partial refunds**).  

Adapting to these changes was essential for maintaining accuracy and completeness.  

By addressing these challenges, we improved **requirement clarity**, enhanced **stakeholder collaboration**, and ensured **more reliable system functionality**.  

# Challenges in Prioritization, Estimation, and Agile Implementation

## Prioritization Difficulties

- Choosing between **functional** and **security-related** tasks was challenging. While encryption is critical, it doesn’t contribute directly to **user experience**, making it harder to balance security with usability.
- Some requirements were **vague**, requiring stakeholder clarification before breaking them into user stories.

## Effort Estimation Issues

- Estimating time for **encryption tasks** was difficult because security implementation depends on **compliance standards** and **testing rigor**.
- **Story dependencies** (e.g., modifying a reservation relies on booking implementation) affected effort estimates, causing **potential delays**.

## Aligning Agile with Stakeholder Needs

- As the **only stakeholder** for this assignment, I had to evaluate **internal resistance** and difficulties in defining **MVP features**.
- Some **must-have stories** required **backend and frontend coordination**, making it harder to deliver independently within a sprint.
- Ensuring **continuous integration and testing** was necessary to validate **security and performance** but added complexity to the sprint.

## Balancing Sprint Scope with Resources

- The team must **balance workload** within the **2-week sprint** to avoid overloading developers.
- Breaking down **user stories into independent, testable features** was challenging, as some functions depended on others.

## Conclusion

Despite these challenges, **Agile methodology** helped in structuring requirements into **manageable, testable features**. The **backlog** provided clarity, and the **sprint plan** ensured alignment with the **MVP**.  

Going forward, refining **estimates** and iterating through **sprint reviews** will improve **planning efficiency**.


# Reflection on Kanban Board Implementation  

## Challenges Faced  
- **Selecting a template**: Kanban Board had useful automation, but lacked a Testing column.  
- **Customizing labels**: Default labels didn't align with my needs, so I created `feature`, `bug`, and `enhancement`.  
- **Work estimation**: Some tasks were harder to estimate, affecting sprint planning.  

## Comparing GitHub, Trello, and Jira  
| Tool  | Strengths  | Weaknesses  |
|-------|-----------|------------|
| **GitHub Projects** | Integrated with GitHub Issues, lightweight automation | Less advanced sprint tracking than Jira |
| **Trello** | Simple, great UI, easy drag-and-drop | Lacks built-in development integration |
| **Jira** | Powerful for Agile teams, detailed reporting | Steep learning curve, complex setup |

## Lessons Learned  
- **Customizing Kanban boards improves workflow visibility**.  
- **Automating tasks in GitHub reduces manual tracking errors**.  
- **Limiting work-in-progress improves task completion speed**.  


# Reflection: Lessons Learned in State and Activity Diagram Modeling

## Challenge 1: Choosing Granularity for States/Actions

Balancing the level of detail in both state and activity diagrams was one of the most difficult aspects of this assignment. On one hand, being too general meant the diagrams didn’t capture critical transitions or actions that affect system behavior. On the other hand, too much detail made the diagrams cluttered and difficult to read—especially when including guard conditions, parallel actions, and swimlanes.

**Example:** In the `Room` object, deciding whether to distinguish between “Under Maintenance,” “Being Cleaned,” and “Temporarily Unavailable” states created complexity. Ultimately, grouping similar operational states under a broader category like “Unavailable” kept things readable and usable for planning.

**Lesson:** The key is to consider your primary audience (developers, stakeholders) and the purpose of the diagram—whether for high-level understanding or detailed design.

---

## Challenge 2: Aligning Diagrams with Agile User Stories

Mapping the dynamic behavior of the system to the Agile user stories was a multi-step process. Some user stories, such as “As a guest, I want to book a room,” naturally translated into workflows like `Book Room`. However, others—especially backend or system-level stories—required combining multiple diagrams to fully illustrate the behavior.

**Example:** The `Check-Out` activity involves both the guest (front-end action) and the system (backend processes like updating room status, issuing invoice, and initiating feedback collection). Aligning that to user stories required breaking down epics into smaller features and tracing those into functional workflows.

**Lesson:** Maintaining traceability between user stories, use cases, and diagram flows helped ensure consistency and avoided missing critical functionality.

---

## Challenge 3: Comparing State Diagrams vs. Activity Diagrams

| Aspect                  | State Diagrams                                | Activity Diagrams                                  |
|------------------------|-----------------------------------------------|----------------------------------------------------|
| Focus                  | Object lifecycle behavior                     | Process flow / workflows                           |
| Example                | Room → Booked → Checked-in → Available        | Book Room → Validate → Confirm → Payment          |
| Strengths              | Shows valid states & transitions over time    | Highlights logic, decisions, concurrency           |
| Limitations            | Doesn’t capture who performs actions          | Doesn’t show long-term object state changes        |

**Summary:**
- **State diagrams** are ideal for understanding how system entities behave and change.
- **Activity diagrams** are better for modeling full workflows, user interactions, and system sequences.

Both diagram types complement each other, and using them together provides a complete picture of system behavior—both from an internal object state and a user-facing workflow perspective.










