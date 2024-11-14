# Student Housing and Roommate Finder Database

## Project Overview

The **Student Housing and Roommate Finder Database** is designed to address the housing challenges faced by college students in Kigali, Rwanda. With an increasing student population and limited affordable housing, students struggle to find suitable living arrangements that match their preferences for location, affordability, and compatibility with roommates. This platform provides a centralized, database-driven solution to streamline the housing search process, enabling students to find rooms, compare listings, and connect with potential roommates. At the same time, it helps landlords efficiently manage listings and reach their target tenants, fostering a transparent and accessible housing market for all.

## Problem Statement

Kigali’s growing college student population faces challenges in securing affordable and suitable housing. The lack of a centralized platform for housing listings leads to wasted time and missed opportunities for students and landlords alike. Students often struggle with identifying affordable options that match their preferences for location and roommate compatibility, while landlords have limited channels to reach student tenants effectively. This project aims to bridge the gap between students and landlords, creating a more efficient and accessible housing ecosystem.

## Objectives

- Provide an easy-to-use interface for students to find affordable rooms, compare options by location, and connect with potential roommates.
- Enable landlords to manage listings effectively and reach student tenants.
- Foster transparency and trust within the local housing market by improving communication and reducing inefficiencies.

## ERD (Entity-Relationship Diagram)

![ERD](https://github.com/user-attachments/assets/72bf1f13-dc3a-4edc-8e47-65ec8efe95e3)


The Entity-Relationship Diagram illustrates the relationships between various entities within the platform, including users (students and landlords), properties, roommate profiles, listings, and reviews.

## BPMN (Business Process Modeling Notation)

![swimlanes](https://github.com/user-attachments/assets/1962c0c0-c773-418c-bd3d-e3f2e2581582)


The Business Process Model provides a workflow for both students and landlords, outlining the steps each user type follows to interact with the system, from property posting to searching and connecting with roommates.

## Data Model

### 1. Users Table
This table stores basic information about all users (students and landlords) on the platform.

- **Attributes:**
  - `user_id` (Primary Key): Unique identifier for each user.
  - `username`: User’s name for identification.
  - `email`: User’s email address.
  - `password_hash`: Securely hashed password.
  - `role`: Defines if the user is a "student" or "landlord".
  - `phone_number`: Optional contact number.
  - `created_at`: Date and time of profile creation.

### 2. Properties Table
Stores details of rental properties listed by landlords.

- **Attributes:**
  - `property_id` (Primary Key): Unique identifier for each property.
  - `landlord_id` (Foreign Key): Links to `user_id` of the landlord.
  - `address`: Location of the property.
  - `price_per_month`: Monthly rental price.
  - `room_type`: Defines room type (shared, private, apartment).
  - `amenities`: List of property amenities.
  - `available_from_date`: When the property is available.
  - `created_at`: Date and time of posting.

### 3. Roommates Table
Contains student roommate preferences.

- **Attributes:**
  - `roommate_id` (Primary Key): Unique identifier for roommate profile.
  - `student_id` (Foreign Key): Links to `user_id` of the student.
  - `budget`: Max rent student is willing to pay.
  - `room_type_preference`: Room type preference.
  - `smoking`: Boolean indicating smoking preference.
  - `gender_preference`: Preferred roommate gender.
  - `created_at`: Date and time of profile creation.

### 4. Listings Table
Connects students to properties they’re interested in.

- **Attributes:**
  - `listing_id` (Primary Key): Unique identifier for each listing.
  - `student_id` (Foreign Key): Links to `user_id` of the student.
  - `property_id` (Foreign Key): Links to `property_id`.
  - `status`: Current status of interaction (interested, visited, booked).
  - `created_at`: Date and time of listing creation.

### 5. Reviews Table
Stores reviews for properties and roommates.

- **Attributes:**
  - `review_id` (Primary Key): Unique identifier for each review.
  - `reviewer_id` (Foreign Key): Links to `user_id` of the reviewer.
  - `reviewee_id` (Foreign Key): Links to `user_id` of the person being reviewed.
  - `review_type`: Type of review (property, roommate).
  - `rating`: Rating score (1-5 stars).
  - `comments`: Text feedback.
  - `created_at`: Date and time of review.

## Key Relationships

- **Users**: Can act as either a student or landlord, with landlords owning properties and students setting roommate preferences.
- **Roommates**: Each student has a 1:1 relationship with their roommate profile, detailing roommate preferences.
- **Listings**: Students can have multiple listings associated with different properties, representing their interactions with various properties.
- **Reviews**: Students can review properties and roommates, promoting accountability and transparency.

## Conclusion

The Student Housing and Roommate Finder Database aims to create an efficient, accessible, and transparent housing ecosystem for college students in Kigali. By organizing key data points—user profiles, property details, roommate preferences, and reviews—the platform will streamline the housing search process, facilitate better communication between students and landlords, and improve overall access to affordable housing for students.
