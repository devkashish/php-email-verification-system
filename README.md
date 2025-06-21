# XKCD Email Verification System

A complete PHP-based email verification and XKCD comic subscription system that allows users to register with email verification and receive daily random XKCD comics via email.

## 🚀 Project Overview

This project implements a fully functional email verification system where users can:
- Register using their email with 6-digit verification codes
- Subscribe to daily XKCD comic deliveries
- Unsubscribe with email verification
- Receive HTML-formatted XKCD comics every 24 hours via automated CRON jobs

## 📁 Project Structure

```
src/
├── index.php              # Main registration page with email verification
├── functions.php          # Core functionality and helper functions
├── cron.php              # CRON job script for sending daily comics
├── unsubscribe.php       # Unsubscribe page with verification
├── setup_cron.sh         # Automated CRON job setup script
├── vendor/
│   └── autoload.php      # Custom autoloader and utility functions
├── registered_emails.txt  # Database file for storing verified emails
├── cron_log.txt          # CRON job execution logs
└── email_log.txt         # Email sending logs
```

## ✨ Features Implemented

### 1️⃣ **Email Registration & Verification**
- ✅ User-friendly registration form with email input
- ✅ 6-digit numeric verification code generation
- ✅ Email delivery with verification codes
- ✅ Code verification and email registration
- ✅ Persistent storage in `registered_emails.txt`

### 2️⃣ **XKCD Comic Subscription**
- ✅ Daily automated comic delivery via CRON jobs
- ✅ Random XKCD comic selection from API
- ✅ HTML-formatted email content with comic images
- ✅ Unsubscribe links in every email

### 3️⃣ **Unsubscribe System**
- ✅ Dedicated unsubscribe page (`unsubscribe.php`)
- ✅ Email verification for unsubscription
- ✅ 6-digit confirmation code system
- ✅ Secure email removal from database

### 4️⃣ **Automated CRON System**
- ✅ `setup_cron.sh` script for automatic CRON configuration
- ✅ 24-hour interval comic delivery
- ✅ Comprehensive logging system
- ✅ Error handling and monitoring

## 🛠 Technical Implementation

### Core Functions (`functions.php`)
- `generateVerificationCode()` - Creates 6-digit numeric codes
- `registerEmail($email)` - Stores verified emails
- `unsubscribeEmail($email)` - Removes emails from database
- `sendVerificationEmail($email, $code)` - Sends verification emails
- `verifyCode($email, $code)` - Validates verification codes
- `fetchAndFormatXKCDData()` - Retrieves and formats XKCD comics
- `sendXKCDUpdatesToSubscribers()` - Distributes comics to subscribers

### Utility Functions (`vendor/autoload.php`)
- `getXKCDComic($num)` - Fetches specific XKCD comics
- `getRandomXKCD()` - Selects random comics
- `sendEmail($to, $subject, $message)` - Email sending wrapper
- `formatEmailContent($comic, $email)` - HTML email formatting

### Database Management
- Uses `registered_emails.txt` as a simple file-based database
- No external database dependencies
- Thread-safe file operations

## 📧 Email System

### Email Types & Formats
1. **Verification Email**
   - Subject: "Your Verification Code"
   - Contains 6-digit verification code

2. **XKCD Comic Email**
   - Subject: "Your XKCD Comic"
   - HTML format with comic image and unsubscribe link

3. **Unsubscribe Confirmation Email**
   - Subject: "Confirm Un-subscription"
   - Contains 6-digit confirmation code

### Email Features
- ✅ HTML formatting for rich content
- ✅ Unsubscribe links in every comic email
- ✅ Professional email headers
- ✅ Error logging and monitoring

## 🔄 CRON Job System

### Automated Setup
- `setup_cron.sh` automatically configures system CRON jobs
- Runs `cron.php` every 24 hours
- Comprehensive logging in `cron_log.txt`

### CRON Job Features
- ✅ Fetches random XKCD comics from API
- ✅ Sends formatted emails to all subscribers
- ✅ Error handling and logging
- ✅ Automatic execution every 24 hours

## 🚀 Installation & Setup

1. **Clone the repository**
   ```bash
   git clone https://github.com/devkashish/php-email-verification-system.git
   cd php-email-verification-system/src
   ```

2. **Configure web server**
   - Point web server to `src/` directory
   - Ensure PHP mail() function is enabled
   - Set proper file permissions

3. **Setup CRON job**
   ```bash
   chmod +x setup_cron.sh
   ./setup_cron.sh
   ```

4. **Access the application**
   - Open `index.php` in your browser
   - Register with email verification
   - Start receiving daily XKCD comics!

## 📋 Requirements

- **PHP Version:** 8.3 (recommended)
- **Web Server:** Apache/Nginx with PHP support
- **Mail Server:** Configured SMTP or local mail server
- **CRON Support:** System-level CRON access
- **File Permissions:** Read/write access for log files

## 🔧 Configuration

### Email Configuration
- Update sender email in `functions.php`
- Configure SMTP settings if needed
- Set proper email headers

### CRON Configuration
- `setup_cron.sh` handles automatic setup
- Manual CRON entry: `0 */24 * * * /path/to/php /path/to/cron.php`

## 📊 Monitoring & Logs

### Log Files
- `cron_log.txt` - CRON job execution logs
- `email_log.txt` - Email sending activity logs
- `registered_emails.txt` - Current subscriber database

### Monitoring Features
- ✅ CRON job execution tracking
- ✅ Email delivery confirmation
- ✅ Error logging and debugging
- ✅ Subscriber count monitoring

## 🛡️ Security Features

- ✅ Email verification for all operations
- ✅ 6-digit numeric codes for security
- ✅ File-based database with proper permissions
- ✅ Input validation and sanitization
- ✅ Secure unsubscribe mechanism

## 🎯 Use Cases

1. **Newsletter Systems** - Daily content delivery
2. **Comic Subscription Services** - Regular comic updates
3. **Email Marketing** - Verified subscriber lists
4. **Content Distribution** - Automated content delivery

## 🤝 Contributing

This project is open for contributions. Please ensure:
- Follow existing code structure
- Maintain backward compatibility
- Add proper error handling
- Update documentation

## 📄 License

This project is open source and available under the MIT License.

---

**Built with ❤️ using PHP and XKCD API**
