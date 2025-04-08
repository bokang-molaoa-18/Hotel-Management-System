# Activity Workflow Modeling with UML Activity Diagrams

## 1. User Registration – Activity Diagram

```mermaid
flowchart TD
    %% Define swimlanes
    subgraph User
        A[Access registration page]
        B[Fill in user details]
        C[Submit registration form]
    end

    subgraph System
        D[Validate input data]
        E{Are all fields complete?}
        F[Validate email uniqueness]
        G[Create user account]
        H[Send confirmation email]
    end

    A --> B --> C --> E
    E -- Yes --> D --> F
    F -- Yes --> G --> H
    H --> Z[End: Welcome email sent]
    E -- No --> Z
    F -- No --> Z
```

## 2. Booking Management – Activity Diagram

```mermaid
flowchart TD
    %% Define swimlanes
    subgraph User
    A[Access booking dashboard]
    B[View current bookings]
    C[Edit booking details]
    F[Cancel booking]
    end

    subgraph System
        D{Is editing allowed?}
        E[Confirm changes]
        G[Update booking records]
        H[Notify affected users]
    end

    A --> B --> C --> D
    D -- Yes --> E --> G
    G --> H
    H --> Z[End: Booking changes confirmed]
    D -- No --> Z
    B --> F --> Z[End: Booking changes canceled]

```

## 3. Check-In Process – Activity Diagram

```mermaid
flowchart TD
    %% Define swimlanes
    subgraph Guest
        A[Arrive at hotel]
        B[Present identification]
    end

    subgraph Receptionist
        C[Verify reservation]
        D{Is identification valid?}
        E{Is reservation confirmed?}
        F[Assign room]
        G[Issue room key]
    end

    subgraph System
        H[Update guest status]
        I[Prepare welcome package]
    end

    A --> B --> C --> D
    D -- Yes --> E
    E -- Yes --> F --> G --> H
    H --> I --> Z[End: Guest receives room key]
    D -- No --> Z
    E -- No --> Z
```

## 5. Feedback Submission – Activity Diagram

```mermaid
flowchart TD
    %% Define swimlanes
    subgraph User
        A[Access feedback form]
        B[Fill out feedback form]
        C[Submit feedback]
    end

    subgraph System
        D{Is feedback form complete?}
        E{Is feedback valid?}
        F[Acknowledge receipt]
        G[Analyze feedback]
        H[Notify management of new submission]
    end

    A --> B --> C --> D
    D -- Yes --> E
    E -- Yes --> F --> G --> H --> Z[End: Feedback submitted]
    D -- No --> Z
    E -- No --> Z
```

## 6. Room Cleaning Task – Activity Diagram

```mermaid
flowchart TD
    %% Define swimlanes
    subgraph Staff
        A[Mark room for cleaning]
        B[Notify cleaning staff]
        C[Clean room]
    end

    subgraph Supervisor
        D[Inspect room for readiness]
    end

    subgraph System
        E{Is cleaning completed satisfactorily?}
        F[Update room status]
        G[Prepare cleaning report]
    end

    A --> B --> C --> D --> E
    E -- Yes --> F --> G --> Z[End: Room ready for next guest]
    E -- No --> Z
```

## 7. Checkout Process – Activity Diagram

```mermaid
flowchart TD
    %% Define swimlanes
    subgraph Guest
        A[Indicate intention to check out]
        B[Review charges]
    end

    subgraph Receptionist
        C[Collect payment]
    end

    subgraph System
        D{Are all charges accurate?}
        E[Generate invoice]
        F[Update room status]
        G[Email invoice to guest]
    end

    A --> B --> C --> D
    D -- Yes --> E --> F --> G --> Z[End: Checkout confirmation received]
    D -- No --> Z
```

## 8. Report Generation – Activity Diagram

```mermaid
flowchart TD
    %% Define swimlanes
    subgraph Management
        A[Request report]
        B[Select report type]
    end

    subgraph System
        C[Gather required data]
        D{Is the data complete?}
        E[Generate report]
        F[Send report]
        G[Archive report]
    end

    A --> B --> C --> D
    D -- Yes --> E --> F --> G --> Z[End: Report generated and sent]
    D -- No --> Z
```


