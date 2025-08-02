# Twitter Clone 🐦

A full-featured Twitter clone built with modern web technologies, replicating the core functionalities of the popular social media platform. This project demonstrates advanced web development practices with a focus on user experience, real-time interactions, and social networking features.

**Developed by Kritika Kumari Mishra** 👨‍💻

## 🚀 Features

### Core Social Features
- **User Authentication**: Secure registration and login system with session management
- **Profile Management**: Customizable user profiles with cover photos and avatars
- **Tweet System**: Create, edit, and delete tweets with 280-character limit
- **Retweet & Quote**: Retweet with or without comments, quote tweets
- **Like System**: Like and unlike tweets with real-time counters
- **Comment System**: Nested comments on tweets with threading support
- **Follow/Unfollow**: Follow other users and manage your following list
- **Notifications**: Real-time notifications for likes, comments, follows, and mentions

### Advanced Features
- **Search Functionality**: Search users by name or username with instant results
- **Hashtag Support**: Use hashtags in tweets for better discoverability
- **Mentions**: Mention other users using @username with auto-completion
- **Who to Follow**: Smart suggestions for users to follow based on interests
- **Responsive Design**: Mobile-friendly interface that works on all devices
- **Real-time Updates**: Dynamic content updates without page refresh using AJAX
- **Image Upload**: Profile picture and cover photo upload functionality
- **Password Management**: Secure password change and recovery system

### User Experience
- **Modern UI**: Clean and intuitive interface inspired by Twitter's design
- **Bootstrap Framework**: Responsive design with Bootstrap 4 components
- **Font Awesome Icons**: Beautiful iconography throughout the application
- **Modal Dialogs**: Smooth user interactions with modal popups
- **Session Management**: Secure session handling and user state management
- **Form Validation**: Client-side and server-side form validation
- **Error Handling**: Comprehensive error handling and user feedback

## 🛠️ Technology Stack

### Backend Technologies
- **PHP 7.4+**: Server-side scripting language for dynamic content
- **MySQL 5.6+**: Relational database management system
- **Apache**: Web server for hosting the application
- **PDO**: PHP Data Objects for secure database connections

### Frontend Technologies
- **HTML5**: Semantic markup for structure
- **CSS3**: Advanced styling with animations and responsive design
- **JavaScript (ES6+)**: Client-side interactivity and AJAX requests
- **jQuery 3.4.1**: DOM manipulation and AJAX functionality
- **Bootstrap 4**: Responsive CSS framework for UI components
- **Font Awesome 4.6.3**: Icon library for beautiful UI elements

### Development Tools & Libraries
- **XAMPP/WAMP**: Local development environment
- **phpMyAdmin**: Database management interface
- **Git**: Version control system
- **AJAX**: Asynchronous JavaScript for real-time updates

### Security Features
- **Session Management**: Secure user session handling
- **SQL Injection Prevention**: Prepared statements and parameterized queries
- **XSS Protection**: Input sanitization and output encoding
- **CSRF Protection**: Cross-site request forgery prevention
- **Password Hashing**: Secure password storage using PHP's password_hash()

## 📋 Prerequisites

Before running this application, make sure you have the following installed:

### Required Software
- **XAMPP** (v7.4+) or **WAMP** (v3.2+) server
- **PHP** 7.4 or higher
- **MySQL** 5.6 or higher
- **Apache** web server
- **Web browser** (Chrome, Firefox, Safari, Edge)

### System Requirements
- **RAM**: Minimum 2GB (4GB recommended)
- **Storage**: At least 1GB free space
- **OS**: Windows, macOS, or Linux
- **Network**: Internet connection for CDN resources

## 🚀 Installation Guide

### Step 1: Download and Setup
1. Clone or download this repository
   ```bash
   git clone https://github.com/Kritikameeshra/twitter-clone.git
   ```
2. Extract the files to your XAMPP/WAMP `htdocs` folder
3. Rename the folder to `twitterclone` (or your preferred name)

### Step 2: Database Setup
1. Start your XAMPP/WAMP server
2. Open **phpMyAdmin** in your browser (`http://localhost/phpmyadmin`)
3. Create a new database named `tweetphp`
4. Select the newly created database
5. Go to the **Import** tab
6. Choose the `DATABASE FILE/tweetphp.sql` file from the project
7. Click **Import** to create all the necessary tables

### Step 3: Configuration
1. Open `core/init.php` in your code editor
2. Update the `BASE_URL` constant if needed:
   ```php
   define("BASE_URL" , "http://localhost/twitterclone/");
   ```
3. Ensure your database connection settings are correct in `core/classes/connection.php`

### Step 4: Access the Application
1. Open your web browser
2. Navigate to `http://localhost/twitterclone/`
3. You should see the Twitter Clone login page

## 📁 Project Structure

```
twitterclone/
├── assets/                 # Static assets (CSS, JS, images)
│   ├── css/               # Stylesheets
│   │   ├── bootstrap.min.css
│   │   ├── all.min.css
│   │   ├── index_style.css
│   │   └── home_style.css
│   ├── js/                # JavaScript files
│   │   ├── jquery-3.4.1.slim.min.js
│   │   ├── popper.min.js
│   │   ├── bootstrap.min.js
│   │   └── mine.js
│   └── images/            # Images and icons
│       ├── twitter.svg
│       └── twitter-logo.png
├── core/                  # Core application files
│   ├── ajax/              # AJAX handlers
│   ├── classes/           # PHP classes
│   │   ├── connection.php
│   │   ├── User.php
│   │   ├── Follow.php
│   │   └── Tweet.php
│   ├── database/          # Database connection
│   └── init.php           # Application initialization
├── DATABASE FILE/         # Database schema
│   └── tweetphp.sql       # MySQL database file
├── handle/                # Form handlers
│   ├── handleAccountSetting.php
│   ├── handleChangePassword.php
│   ├── handleDeleteCover.php
│   ├── handlelogin.php
│   ├── handleSignUp.php
│   ├── handleTweet.php
│   └── handleUpdateData.php
├── includes/              # Reusable components
│   ├── icons/             # Icon assets
│   ├── login.php          # Login form
│   ├── logout.php         # Logout functionality
│   ├── signup-form.php    # Registration form
│   └── tweets.php         # Tweet components
├── account.php            # Account settings page
├── home.php              # Main dashboard
├── index.php             # Landing page
├── notification.php      # Notifications page
├── profile.php           # User profile page
├── status.php            # Tweet detail page
└── README.md             # This file
```

## 🗄️ Database Schema

The application uses the following main tables:

### Core Tables
- **users**: User accounts and profile information
  - `id`, `username`, `email`, `password`, `name`, `profileImage`, `coverImage`, `bio`, `location`, `website`, `created`
- **tweets**: Tweet content and metadata
  - `id`, `user_id`, `tweet`, `image`, `created`, `likes_count`, `retweet_count`, `retweet_id`
- **comments**: Tweet comments and replies
  - `id`, `comment`, `user_id`, `post_id`, `time`
- **follow**: User follow relationships
  - `id`, `follower_id`, `following_id`, `time`
- **likes**: Tweet like records
  - `id`, `user_id`, `tweet_id`, `time`
- **notifications**: User notification system
  - `id`, `notificationFor`, `notificationFrom`, `target`, `type`, `time`, `status`

### Relationships
- Users can have multiple tweets (one-to-many)
- Users can follow multiple users (many-to-many through follow table)
- Tweets can have multiple likes and comments (one-to-many)
- Notifications are linked to users and actions

## 👤 Default Users

After installation, you can create new accounts or use the default test accounts that may be included in the database.

## 🔧 Customization

### Changing the Base URL
Update the `BASE_URL` constant in `core/init.php`:
```php
define("BASE_URL" , "http://your-domain.com/your-folder/");
```

### Database Configuration
Modify `core/classes/connection.php` for different database settings:
```php
$host = 'localhost';
$dbname = 'tweetphp';
$username = 'your_username';
$password = 'your_password';
```

### Styling
- Main styles are in `assets/css/`
- Bootstrap theme can be customized
- Font Awesome icons can be replaced or extended
- Custom CSS can be added to existing files

### Features
- Add new features by extending the existing classes
- Modify the database schema for additional functionality
- Customize the notification system
- Implement additional social features

## 🐛 Troubleshooting

### Common Issues

1. **Database Connection Error**
   - Verify XAMPP/WAMP is running
   - Check database credentials in `core/classes/connection.php`
   - Ensure the `tweetphp` database exists
   - Verify MySQL service is started

2. **Page Not Found (404)**
   - Confirm files are in the correct `htdocs` folder
   - Check Apache is running
   - Verify the folder name matches the URL
   - Check file permissions

3. **Images Not Loading**
   - Check file permissions (755 for folders, 644 for files)
   - Verify image paths in the code
   - Ensure `assets` folder is accessible
   - Check for case sensitivity in file names

4. **Session Issues**
   - Clear browser cookies
   - Check PHP session configuration
   - Verify session storage permissions
   - Restart Apache server

5. **AJAX Not Working**
   - Check browser console for JavaScript errors
   - Verify jQuery is loaded
   - Check network tab for failed requests
   - Ensure PHP error reporting is enabled

## 🔒 Security Considerations

- All user inputs are sanitized and validated
- SQL queries use prepared statements
- Passwords are hashed using PHP's password_hash()
- Session management prevents unauthorized access
- CSRF protection is implemented
- XSS protection through output encoding

## 🚀 Performance Optimization

- Database queries are optimized with proper indexing
- Images are compressed and optimized
- CSS and JS files are minified
- CDN resources are used for faster loading
- Caching strategies are implemented

## 🤝 Contributing

This project is open for contributions! Feel free to:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

### Contribution Guidelines
- Follow PHP PSR-12 coding standards
- Add comments to complex code sections
- Test your changes thoroughly
- Update documentation if needed

## 📝 License

This project is developed for educational purposes. Feel free to use and modify as needed.

## 👨‍💻 Developer

**Developed by Kritika Kumari Mishra**

This Twitter Clone project showcases modern web development techniques and provides a solid foundation for building social media applications. The code is well-structured, documented, and follows PHP best practices.

### Contact Information
- **GitHub**: [Kritika Kumari Mishra](https://github.com/Kritikameeshra)
- **LinkedIn**: [Kritika Kumari Mishra](https://www.linkedin.com/in/kritika-kumari-mishra-3471a0256)

---

**Note**: This is a clone project created for educational purposes. It replicates Twitter's core functionality but is not affiliated with Twitter Inc.

## 🔗 Quick Links

- [Home Page](http://localhost/twitterclone/)
- [Login](http://localhost/twitterclone/index.php)
- [Sign Up](http://localhost/twitterclone/index.php#signup)

## 📊 Project Statistics

- **Lines of Code**: 2000+
- **Files**: 50+
- **Database Tables**: 6
- **Features**: 15+
- **Technologies**: 8

---

*Built with ❤️ using PHP, MySQL, and Bootstrap by Kritika Kumari Mishra*
