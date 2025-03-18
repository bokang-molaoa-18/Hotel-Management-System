graph TD;
  Guest -->|Initiates| BookRoom;
  Guest -->|Checks in| CheckIn;
  Guest -->|Modifies reservation| ModifyReservation;
  Guest -->|Views| GenerateReports;
  
  HotelStaff -->|Manages| BookRoom;
  HotelStaff -->|Handles| CheckIn;
  HotelStaff -->|Updates| ModifyReservation;
  HotelStaff -->|Reviews| GenerateReports;
  
  System -->|Processes| BookRoom;
  System -->|Authenticates| CheckIn;
  System -->|Executes| ModifyReservation;
  System -->|Generates| GenerateReports;
  
  ThirdParty -->|Syncs bookings| SyncBookings;
  System -->|Integrates| SyncBookings;

