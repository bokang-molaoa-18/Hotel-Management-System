# Domain Model – Hotel Management System

| Entity         | Attributes                                  | Methods                               | Relationships                                                 | Business Rules                                                 |
|----------------|---------------------------------------------|----------------------------------------|----------------------------------------------------------------|----------------------------------------------------------------|
| Guest          | guestId, name, email, phoneNumber           | register(), login(), makeBooking()     | One Guest can make many Bookings                              | A guest must be registered to make a booking                  |
| Booking        | bookingId, startDate, endDate, status       | confirm(), cancel(), updateDates()     | Linked to one Guest and one Room                              | A guest can cancel a booking before check-in                  |
| Room           | roomId, roomType, availability, price       | assign(), markAvailable(), cleanRoom() | A Room can have many Bookings                                 | Room must be available to be booked                          |
| Payment        | paymentId, amount, status, paymentDate      | process(), refund()                    | Associated with one Booking                                   | Booking must be confirmed before payment                     |
| Invoice        | invoiceId, totalAmount, issuedDate          | generate(), print()                    | One Invoice per Booking                                        | Invoice is created only after payment confirmation           |
| Staff          | staffId, name, role, shiftSchedule          | checkInGuest(), checkOutGuest()        | One Staff member can handle many Check-ins/outs               | Staff roles determine access rights to check-in functions    |
| Feedback       | feedbackId, content, rating, submittedDate  | submitFeedback()                       | One Guest can give many Feedbacks                             | Feedback must be linked to completed bookings                |

