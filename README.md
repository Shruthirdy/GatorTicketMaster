# 📬 SMTP Email Notification Integration (New Feature)

We’ve added SMTP-based email notifications to enhance user engagement and platform communication. This new feature automatically sends beautifully styled HTML emails upon **user registration** and **campaign creation**, helping users stay informed and feel welcomed.

---

### 🔔 Feature Highlights

| Feature | Description | Trigger Event |
|--------|-------------|----------------|
| 🎉 **Welcome Email** | Sends a personalized welcome message to new users with Impacta branding and message styling. | On successful user registration |
| 📢 **Campaign Created Email** | Notifies campaign creators that their campaign has been created and provides a link to their campaign dashboard. | On successful campaign creation |

---

### 💻 Backend Integration

| Issue # | Task Description | Assigned To | Status |
|---------|------------------|-------------|--------|
| S3-B01 | Integrate SMTP-based email notifications using `net/smtp` | Shruthi | ✅ Completed |
| S3-B02 | Trigger welcome email upon user registration | Shruthi | ✅ Completed |
| S3-B03 | Trigger campaign confirmation email with campaign details and dashboard link | Shruthi | ✅ Completed |

---

### 📧 Email Template Overview

Emails are sent in **HTML format** with inline CSS for enhanced readability and aesthetics. Templates include:

- ✅ Clean typography
- ✅ Responsive layout
- ✅ Dynamic content injection (e.g., user name, campaign title, deadline)
- ✅ Fallback styling for email clients

### ⚙️ Backend Technical Details

- **SMTP Provider:** Gmail (via `smtp.gmail.com:587`)
- **Authentication:** `smtp.PlainAuth` with credentials from environment variables
- **Email Logic File:** `utils/email.go`
- **Integration Points:** `controllers/user_controller.go`, `controllers/campaign_controller.go`
- **Non-blocking Sending:** Email sending runs in a background goroutine to avoid blocking API responses

---

## 🧑‍💻 Contributors

- **Shruthi** - Backend Email Integration, Template Design, and SMTP Setup

