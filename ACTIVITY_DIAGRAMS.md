## Booking State Transition Diagram

```mermaid
stateDiagram-v2
    [*] --> Requested
    Requested --> Confirmed : Payment Received
    Requested --> Cancelled : User Cancels
    Confirmed --> CheckedIn : Guest Arrives
    CheckedIn --> CheckedOut : Guest Leaves
    Cancelled --> [*]
    CheckedOut --> [*]
```



## Room State Transition Diagram

```mermaid
stateDiagram-v2
    [*] --> Available
    Available --> Reserved : Booking Confirmed
    Reserved --> Occupied : Guest Checks In
    Occupied --> Cleaning : Guest Checks Out
    Cleaning --> Available : Housekeeping Complete
```



## Payment State Transition Diagram

```mermaid
stateDiagram-v2
    [*] --> Pending
    Pending --> Completed : Transaction Successful
    Pending --> Failed : Transaction Declined
    Failed --> Pending : Retry Payment
    Completed --> [*]
```


## User Account State Transition Diagram

```mermaid
stateDiagram-v2
    [*] --> Registered
    Registered --> Active : Email Verified
    Active --> Suspended : Admin Action
    Suspended --> Active : Reinstated
    Active --> Deleted : User Request
    Deleted --> [*]
```


## Reservation State Transition Diagram

```mermaid
stateDiagram-v2
    [*] --> Initiated
    Initiated --> Confirmed : Room Selected and Payment Done
    Confirmed --> Modified : User Updates Dates
    Modified --> Confirmed : Changes Approved
    Confirmed --> Cancelled : User Cancels
    Cancelled --> [*]
```

## Invoice State Transition Diagram

```mermaid
stateDiagram-v2
    [*] --> Generated
    Generated --> Sent : Email to Guest
    Sent --> Paid : Payment Received
    Paid --> Archived : Record Saved
    Archived --> [*]
```

## Invoice State Transition Diagram

```mermaid
stateDiagram-v2
    [*] --> Submitted
    Submitted --> Reviewed : Admin Reads Feedback
    Reviewed --> Resolved : Action Taken
    Resolved --> Archived : Closed
    Archived --> [*]
```

## Staff Schedule State Transition Diagram

```mermaid
stateDiagram-v2
    [*] --> Drafted
    Drafted --> Published : Approved by Manager
    Published --> Modified : Updates Required
    Modified --> Published : Reapproved
    Published --> Archived : Schedule Completed
    Archived --> [*]
```
