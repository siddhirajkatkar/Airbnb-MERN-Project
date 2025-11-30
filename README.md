{"id":"47101","variant":"standard","title":"SRS for Airbnb Clone (MERN + MySQL)"}
# **Software Requirements Specification (SRS)**  
## **Airbnb Clone Web Application**  
### **Technology Stack: MERN + MySQL**

---

# **1. Introduction**

## **1.1 Purpose**
The purpose of this SRS document is to define the functional and non-functional requirements for the **Airbnb Clone** web application built using **React (Frontend), Node.js + Express.js (Backend), and MySQL (Database)**.

This system allows users to list properties, browse available stays, book accommodations, and manage reservations.

---

## **1.2 Scope**
The system will provide:
- User registration & login  
- Property listing management  
- Property search & filters  
- Booking and reservation system  
- User profile management  
- Admin panel for listing moderation  

Actors:
- **Guest User**
- **Registered User (Traveller / Host)**
- **Admin**

---

## **1.3 Definitions**
- **Host:** User who lists properties.  
- **Traveller:** User who books properties.  
- **Listing:** Property added by a host.  
- **Reservation:** Confirmed booking.

---

# **2. System Overview**
This is a full-stack travel accommodation web app where:
- Users browse available stays.
- Hosts add properties with images and details.
- Travellers book stays.
- Admin monitors all users and listings.

The database uses **MySQL**, not MongoDB.

---

# **3. Functional Requirements**

## **3.1 User Module**
### **FR-1: User Registration**
- Users can sign up using email & password.
- Passwords must be hashed.

### **FR-2: User Login**
- JWT-based authentication.
- Email verification (optional).

### **FR-3: Profile Management**
- User can update name, email, phone, photo.

---

## **3.2 Listing Module (Host Features)**
### **FR-4: Add New Listing**
A host can add:
- Title  
- Description  
- Address  
- City, State, Country  
- Price per night  
- Max guests  
- Amenities  
- Images (multiple)

### **FR-5: Edit Listing**
- Host can update any property information.

### **FR-6: Delete Listing**
- Host can remove a listing.

### **FR-7: View All Host Listings**
- Show all properties listed by the host.

---

## **3.3 Search & Filter Module**
### **FR-8: Property Search**
Travellers can search by:
- City  
- Dates  
- Number of guests  

### **FR-9: Filters**
- Price range  
- Amenities  
- Ratings (future feature)

---

## **3.4 Booking Module**
### **FR-10: Check Availability**
- System verifies property availability for given dates.

### **FR-11: Create Reservation**
Traveller can book a property:
- Check-in date  
- Check-out date  
- Number of guests  
- Payment status (future integration)

### **FR-12: Booking History**
- Users can view past and upcoming reservations.

---

## **3.5 Admin Module**
### **FR-13: Admin Login**
- Admin authenticates using secure login.

### **FR-14: Manage Users**
- View all users  
- Block/unblock accounts  

### **FR-15: Manage Listings**
- Approve / remove listings  
- Remove inappropriate content  

---

# **4. Database Requirements (MySQL)**

## **Tables**
1. **users**
   - id, name, email, password, phone, role, created_at

2. **listings**
   - id, host_id, title, description, price, address, city, state, country, max_guests, created_at

3. **listing_images**
   - id, listing_id, image_url

4. **reservations**
   - id, listing_id, user_id, check_in, check_out, total_price, status

5. **amenities**
   - id, name

6. **listing_amenities**
   - id, listing_id, amenity_id

---

# **5. Non-Functional Requirements**

## **5.1 Performance**
- Search and listing pages must load under **2 seconds**.
- API response time under **500 ms**.

## **5.2 Reliability**
- Daily automated backup of MySQL database.

## **5.3 Security**
- JWT Authentication  
- Password hashing (bcrypt)  
- SQL Injection prevention  
- Rate limiting for APIs  

## **5.4 Usability**
- Fully responsive UI.  
- Easy navigation similar to Airbnb.

## **5.5 Scalability**
- Can scale using load balancing & horizontal scaling.

---

# **6. System Architecture**

## **Frontend**
- React.js with hooks
- Tailwind/Bootstrap UI
- Axios for API requests

## **Backend**
- Node.js + Express  
- JWT Auth  
- Multer for image upload  
- Sequelize / Knex.js as ORM for MySQL

## **Database**
- MySQL relational tables

---

# **7. Future Enhancements**
- Online payment integration  
- Reviews & Ratings  
- Real-time chat between host & customer  
- Wishlist feature  
- Map integration  

---

# **8. Conclusion**
This SRS provides a detailed, clear, and structured requirement specification for the **Airbnb Clone built using MERN with MySQL**.  
This can be used for development, documentation, or academic submission.

