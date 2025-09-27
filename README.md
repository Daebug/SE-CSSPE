# CSSPE Management System

A comprehensive web-based management system designed for the Computer Science Society of the Philippines - Educators (CSSPE) organization. This system facilitates inventory management, event coordination, member administration, and organizational operations.

## 🏗️ System Architecture

The application follows a modular PHP architecture with role-based access control and automated administrative functions.

### Core Modules

- **Super Admin** (`/superAdmin/`) - System-wide administration and user management
- **Inventory Admin** (`/inventoryAdmin/`) - Equipment and resource management
- **Information Admin** (`/informationAdmin/`) - Content and announcement management
- **Home Portal** (`/homePage/`) - Main user interface and member functions

## 🔐 User Roles & Access Control

### Administrator Roles

- **Super Admin** - Full system access, user account management
- **Inventory Admin** - Equipment tracking, borrowing oversight, inventory reports
- **Information Admin** - Announcements, events, organizational content

### Member Roles

- **Instructor** - Basic member access, borrowing privileges
- **Faculty Member** - Enhanced member privileges

### Access Features

- Session-based authentication with role validation
- Automatic account deactivation system (May 24th annually)
- Pending user approval workflow
- Ban status monitoring for borrowing violations

## 📊 Key Features

### Inventory Management

- **Equipment Tracking** - Comprehensive item catalog with brands, projects, and quantities
- **Borrowing System** - Request, approval, and return workflow
- **Transaction History** - Complete audit trail of all equipment movements
- **Status Monitoring** - Real-time availability and condition tracking

### Event & Communication

- **Event Management** - Create, manage, and track organizational events
- **Announcements** - System-wide communication platform
- **Notifications** - Real-time updates and alerts
- **Memorandums** - Official document distribution

### Member Administration

- **Profile Management** - User information and photo management
- **Organization Tracking** - Department and project affiliations
- **Account Lifecycle** - Registration, approval, and deactivation processes

### Reporting & Analytics

- **Transaction Reports** - Detailed borrowing and return analytics
- **Inventory Reports** - Stock levels and usage patterns
- **Member Reports** - User activity and engagement metrics

## 🗄️ Database Schema

The system utilizes a MySQL database (`csspe`) with 20 core tables:

### Primary Tables

- `users` - User accounts and profile information
- `items` - Equipment and resource inventory
- `item_transactions` - Borrowing and return records
- `events` - Organizational events and activities
- `announcements` - System-wide communications
- `organizations` - Department and group management

### Supporting Tables

- `item_quantities` - Stock level tracking
- `item_status_tracking` - Equipment condition monitoring
- `notifications` - User alert system
- `memorandums` - Official document management
- `pending_users` - Account approval queue
- `deactivation_logs` - System maintenance records

## 🛠️ Technology Stack

### Backend

- **PHP 8.2+** - Server-side scripting
- **MySQL/MariaDB** - Database management
- **Session Management** - User authentication and state

### Frontend

- **HTML5** - Semantic markup
- **CSS3** - Responsive styling with Tailwind CSS
- **JavaScript** - Client-side interactivity
- **Tailwind CSS** - Utility-first styling framework

### Development Tools

- **npm** - Package management
- **Tailwind CLI** - CSS processing

## 📁 Project Structure

```
SE-CSSPE/
├── assets/                 # Static resources
│   └── css/               # Stylesheets for each module
├── backup/                # System backups
├── conn/                  # Database connection and authentication
├── database/              # SQL schema and data
├── homePage/              # Main user interface
├── informationAdmin/      # Content management interface
├── inventoryAdmin/        # Inventory management interface
├── superAdmin/            # System administration interface
├── index.php              # Main application entry point
├── logout.php             # Session termination
└── package.json           # Node.js dependencies
```

## 🚀 Installation & Setup

### Prerequisites

- PHP 8.2 or higher
- MySQL/MariaDB 10.4+
- Web server (Apache/Nginx)
- Node.js (for Tailwind CSS)

### Installation Steps

1. **Clone the repository**

   ```bash
   git clone [repository-url]
   cd SE-CSSPE
   ```

2. **Database Setup**

   ```bash
   # Import the database schema
   mysql -u root -p < database/csspe.sql
   ```

3. **Configure Database Connection**

   ```php
   // Update conn/conn.php with your database credentials
   $host = "localhost";
   $username = "root";
   $password = "your_password";
   $database_name = "csspe";
   ```

4. **Install Dependencies**

   ```bash
   npm install
   ```

5. **Build Styles**

   ```bash
   npm run build  # or npx tailwindcss -i input.css -o assets/css/output.css
   ```

6. **Configure Web Server**
   - Point document root to project directory
   - Ensure PHP modules are enabled
   - Configure proper file permissions

## 🔧 Configuration

### Automatic Deactivation

The system includes an automated user deactivation feature that triggers annually on May 24th, preserving admin accounts while deactivating regular members for the new academic year.

### Role-Based Access

Access control is enforced through the `auth.php` module, which validates user sessions and role permissions for each protected resource.

### File Upload Settings

Profile images and document uploads are configured with appropriate security restrictions and file type validation.

## 🔒 Security Features

- **SQL Injection Protection** - Prepared statements for all database queries
- **Session Security** - Secure session management with role validation
- **File Upload Security** - Type validation and secure storage
- **Access Control** - Role-based permissions for all system functions
- **Audit Logging** - Complete transaction and system activity logs

## 📈 System Monitoring

### Logging

- **Deactivation Logs** - Annual user account management
- **Transaction History** - Complete borrowing and return records
- **Notification Tracking** - User engagement and communication metrics

### Reporting

- **Inventory Reports** - Stock levels and utilization
- **User Activity** - Engagement and system usage patterns
- **Administrative Actions** - System maintenance and management activities

**CSSPE Management System** - Streamlining organizational operations through comprehensive digital management solutions.
