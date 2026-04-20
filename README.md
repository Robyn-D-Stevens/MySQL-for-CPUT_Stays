# BUSINESS RULES  
*(Influence data design and tables)*

## Student – Booking
- A student may make a booking for one or many rooms per year **only after registering** (creating an account) on the website.  
- A booking can be made by one or zero students.  
- A student can only have **one approved booking per year**.  
- A student may have up to **3 pending bookings**.  
  - If 1 booking is approved, the remaining pending bookings are automatically revoked.  
  - If none are approved, all 3 bookings must remain pending.  

## Student – Maintenance
- A student can submit **zero or many maintenance requests** to the accommodation that approved them.  
- Maintenance requests can only be submitted if the student has an **approved booking** (is an occupant).  
- Maintenance requests must be **assigned to staff within 24 hours** of submission.  

## Rooms (Accommodation) – Booking
- One accommodation can receive multiple bookings from different students, but only **one booking per accommodation per student per year**.  
- Each accommodation can have a different number of rooms, room types, amenities, and prices.  
- A booking must be linked to both a **valid student** and a **valid accommodation**.  
- An accommodation must have a room available to approve a booking:  
  - If approved, the number of available rooms decreases by 1 on the website.  
  - If no rooms are available, no bookings can be approved.  

## Booking – Payment
- Students do not pay accommodations directly; **payments are made through bookings**.  
- A payment can only be made if the associated booking has been **approved**.  
- A booking can have **one or more payments**, but each payment is linked to only one booking for a specific student.  
- Each payment must include:  
  - Method  
  - Amount  
  - Date  
  - Validation against the booking’s payment status  

## DB Management – Booking
- One DB Management staff member oversees **many bookings at a time**.  
- DB Management staff can view all information on the website and have **full administrative permissions**.  
- DB Management is linked with Students, Accommodation Staff, and Rooms via **Booking**, representing all the data they oversee.  

<img src="https://github.com/Robyn-D-Stevens/MySQL-for-CPUT_Stays/blob/main/Screenshot%202026-04-20%20185747.png" alt="ERD Image" width="700"/>
