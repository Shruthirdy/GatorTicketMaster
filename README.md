# 🌟 Impacta - Crowdfunding for Small Causes
 
 Impacta is a crowdfunding platform designed to help individuals contribute to **meaningful causes**, ensuring transparency and ease of donation.
 
 ---
 
 ## 🚀 Project Overview (Sprint 2)
 
Sprint3, focused on extending Impacta's backend functionality by adding full CRUD support for four new services: **Notifications**, **Support Tickets**, **Payment Transactions**, and **Withdrawals**. Notifications and Support Tickets, ensures that users can receive timely alerts and manage support queries (with admin-restricted answer updates). Payment Transactions and Withdrawals, focuses on secure transaction recording and withdrawal management with admin-controlled updates and bulk deletions. These enhancements provide robust communication and financial tracking features essential for our crowdfunding platform.
 
 
 ---
 
 
 ## 🏆 Sprint 3 Breakdown
 
 | Issue # | Task Description                                                                                                  | Assigned To         | Status        |
 |---------|-------------------------------------------------------------------------------------------------------------------|---------------------|---------------|
 | **Frontend Tasks** |                                                                                                  |                     |               |
 | S2-F01  | Develop and integrate Campaign Creator Dashboard (UI & Functionality)                                              | Vennela             | ✅ Completed  |
 | S2-F02  | Implement campaign statistics section (Total Campaigns, Active Campaigns, Funds Raised)                            | Vennela             | ✅ Completed  |
 | S2-F03  | Design and integrate Donation Cards displaying campaign details                                                    | Vennela             | ✅ Completed  |
 | S2-F04  | Implement Create Campaign private route inside the dashboard                                                       | Vennela             | ✅ Completed  |
 | S2-F05  | Implement form fields for Title, Description, Goal, Category, Image Upload, Duration                               | Vennela             | ✅ Completed  |
 | S2-F06  | Integrate API for campaign creation with backend                                                                   | Vennela             | ✅ Completed  |
 | S2-F07  | Develop Impacta Donation Page with campaign details and donor interactions                                         | Deepthi             | ✅ Completed  |
 | S2-F08  | Implement Banner Image, Title, Description, and Funding Metrics in the donation page                               | Deepthi             | ✅ Completed  |
 | S2-F09  | Integrate API for donation page - comments api,campaigndetails,donation details.Also added Donate Now & Share Buttons for donor engagement | Deepthi             | ✅ Completed  |
 | S2-F10  | Setup Axios-based API integration for fetching campaign details, media, donations, and comments                    | Deepthi             | ✅ Completed  |
 | S2-F11  | Integrate PayPal Smart Payment Buttons for seamless donation transactions                                          | Deepthi             | ✅ Completed  |
 | S2-F12  | Implement Cloudinary for media storage                                                                             | Vennela             | ✅ Completed  |
 | S2-F13  | Implement Unit & Cypress Tests for Login Page                                                                      | Deepthi             | ✅ Completed  |
 | S2-F14 | Implement Unit & Cypress Tests for Donor Dashboard                                                                  | Deepthi             | ✅ Completed  |
 | S2-F15  | Implement Unit & Cypress Tests for Register Page                                                                   | Vennela             | ✅ Completed  |
 | S2-F16  | Implement Unit & Cypress Tests for Create Campaign Page                                                            | Vennela             | ✅ Completed  |
 | **Backend Tasks**  |                                                                                                  |                     |               |
 | S3-B01      | Implement full CRUD endpoints for Notifications                                                            | Chandan         | ✅ Completed  |
| S3-B02      | Create unit tests for Notifications endpoints                                                              | Chandan         | ✅ Completed  |
| S3-B03      | Implement full CRUD endpoints for Support Tickets (including query & answer fields, with role checks)       | Chandan         | ✅ Completed  |
| S3-B04      | Create unit tests for Support Tickets endpoints                                                            | Chandan         | ✅ Completed  |
| S3-B05      | Implement full CRUD endpoints for Payment Transactions (admin-only update & bulk delete)                     | Shruthi         | ✅ Completed  |
| S3-B06      | Create unit tests for Payment Transactions endpoints                                                       | Shruthi         | ✅ Completed  |
| S3-B07      | Implement full CRUD endpoints for Withdrawals (admin-only update & bulk delete)                             | Shruthi         | ✅ Completed  |
| S3-B08      | Create unit tests for Withdrawal endpoints                                                                 | Shruthi         | ✅ Completed  |
 
 
### Sprint 3 Backend Development Summary

- Implemented full CRUD endpoints for **Notifications** with secure, role-based access control.
- Developed comprehensive **Support Tickets** endpoints with extended fields (query & answer) and restricted answer updates to admins.
- Added full CRUD functionality for **Payment Transactions**, including admin-only updates and bulk deletion.
- Created complete endpoints for **Withdrawals** to manage campaign fund disbursements with admin-controlled updates.
- Integrated unit tests for all new endpoints, improving error handling and logging for enhanced backend reliability.
 
 
 ### Frontend Development Summary
 
 Key improvements include:
 
 - **Dynamic Donor Dashboard:** An interactive dashboard that displays real-time campaign statistics, donation data, and campaign details.
 - **Updated API Integration:** Seamless integration of updated API endpoints for campaigns, donations, media files, and comments, ensuring real-time data updates and improved responsiveness.
 - **Enhanced UI Components:** New components such as campaign statistics, donation cards, and interactive elements (e.g., Donate Now & Share buttons) that enrich the overall user interface.
 - **Payment Integration:** Implementation of PayPal Smart Payment Buttons for smooth and secure donation transactions.
 - **Media Management:** Integration of Cloudinary for robust media storage and retrieval, supporting campaign-related images and videos.
 
 
 ---
 
 ## 👥 Contributors
 
 - **Vennela** - Frontend Development
 - **Deepthi** - Frontend Development
 - **Chandan** - Backend Development
 - **Shruthi** - Backend Development
 
   ## 🎬 Frontend Walkthrough Video
 📽️ Watch the full frontend walkthrough here: [Frontend Walkthrough Video](https://youtu.be/Rl5WHgtAUi4)
 
 ## 🎬 Backend Walkthrough Video
 📽️ Watch the full backend walkthrough here: [Backend Walkthrough Video](https://www.youtube.com/watch?v=25DhEfzo-fY)
 
 
 🚀 **Impacta - Empowering Small Causes, One Donation at a Time!**
