graph TD
    subgraph HotelSystem
        Guest -->|Initiates| BookRoom
        HotelStaff -->|Manages| BookRoom
        System -->|Processes| BookRoom
    end
    
    subgraph GuestInteractions
        Guest -->|Checks in| CheckIn
        Guest -->|Modifies reservation| ModifyReservation
    end
    
    ThirdParty -->|Syncs bookings| SyncBookings
    System -->|Integrates| SyncBookings



