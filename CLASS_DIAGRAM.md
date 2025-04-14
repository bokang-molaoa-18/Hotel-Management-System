# Class Diagram – Hotel Management System

```mermaid
classDiagram
class Guest {
  -guestId: String
  -name: String
  -email: String
  -phoneNumber: String
  +register()
  +login()
  +makeBooking()
}

class Booking {
  -bookingId: String
  -startDate: Date
  -endDate: Date
  -status: String
  +confirm()
  +cancel()
  +updateDates()
}

class Room {
  -roomId: String
  -roomType: String
  -availability: Boolean
  -price: Float
  +assign()
  +markAvailable()
  +cleanRoom()
}

class Payment {
  -paymentId: String
  -amount: Float
  -status: String
  -paymentDate: Date
  +process()
  +refund()
}

class Invoice {
  -invoiceId: String
  -totalAmount: Float
  -issuedDate: Date
  +generate()
  +print()
}

class Staff {
  -staffId: String
  -name: String
  -role: String
  -shiftSchedule: String
  +checkInGuest()
  +checkOutGuest()
}

class Feedback {
  -feedbackId: String
  -content: String
  -rating: Int
  -submittedDate: Date
  +submitFeedback()
}

Guest "1" -- "0..*" Booking : makes
Booking "1" -- "1" Room : reserves
Booking "1" -- "1" Payment : pays
Booking "1" -- "1" Invoice : generates
Booking "1" -- "0..*" Feedback : allows
Staff "1" -- "0..*" Booking : manages
Room "1" -- "0..*" Booking : availableFor
