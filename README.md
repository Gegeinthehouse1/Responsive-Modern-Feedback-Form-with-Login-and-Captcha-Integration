**Project Overview**
The GCTU Application System is a full-stack prototype for managing student applications at GCTU. Students can sign up, log in, submit applications, and view their submissions, while administrators can access a dashboard to review, edit, or delete applications. The system uses localStorage for data persistence (mock backend), ensuring a functional demo without server setup. Security is enhanced with Google reCAPTCHA v2, and the UI is polished with GSAP animations and a responsive design.

This project is ideal for educational institutions seeking a customizable application portal or for developers learning front-end development with authentication, form handling, and animations.

Features
User Authentication:
Sign-up with email, password, and role (Student/Admin).
Login with role-based redirects (Student: application form, Admin: dashboard).
Password confirmation and email uniqueness validation.
Google reCAPTCHA v2 Checkbox for secure sign-up/login.
Student Application Form:
Fields for personal info (name, DOB, nationality), contact (email, phone), gender, and program of study.
International phone input with country flags and dial codes.
Form validation and submission with GSAP animations.
Application Management:
Students can view their applications in a table with edit/delete options.
Admins access a dashboard with metrics (total/pending applications) and full CRUD functionality.
Bulk delete and select-all features for efficient management.
Animations and Effects:
Envelope animation with audio on successful login.
Particle background for visual appeal.
GSAP-powered transitions for forms, modals, and table rows.
Responsive Design:
Squarish login/sign-up forms for a modern look.
Consistent styling across devices using shared CSS and Poppins font.
Data Persistence:
Applications and user credentials stored in localStorage.
Mock backend for demo purposes, easily extensible to a real server.
Technologies Used
Frontend:
HTML5: Semantic structure for pages.
CSS3: Custom styles with shared.css, login.css, dashboard.css, etc.
JavaScript (ES6): Core logic in script.js for form handling and animations.
Libraries and APIs:
GSAP (GreenSock Animation Platform): For animations (envelope, modals, ripples).
intl-tel-input: International phone number input.
country-list-with-dial-code-and-flag: Nationality dropdowns.
Google reCAPTCHA v2: Bot protection.
Fonts and Assets:
Poppins Font (via Google Fonts): Modern typography.
Placeholder images and audio (e.g., welcome.mp3 for login animation).
Installation
Follow these steps to set up the project locally:

Clone the Repository:
bash

Collapse

Wrap

Run

Copy
git clone https://github.com/your-username/gctu-application-system.git
cd gctu-application-system
Set Up Project Structure: Ensure the following directory structure:
text

Collapse

Wrap

Copy
gctu-application-system/
├── assets/
│   ├── audio/
│   │   └── welcome.mp3
│   └── images/
│       └── logo-gctu.png
├── scripts/
│   └── script.js
├── styles/
│   ├── shared.css
│   ├── login.css
│   ├── dashboard.css
│   ├── apply.css
│   └── view.css
├── index.html
├── login.html
├── view.html
├── dashboard.html
└── README.md
Create assets/images/logo-gctu.png (use a placeholder or GCTU logo).
Create assets/audio.mp3 (use a short WAV/MP3 for login animation).
Serve the Application:
Use a local server (e.g., Python’s HTTP server):
bash

Collapse

Wrap

Run

Copy
python -m http.server 8000
Open http://localhost:8000 in your browser.
Alternatively, use VS Code’s Live Server extension or any static file server.
Configure Google reCAPTCHA:
Follow the WTF section to obtain and integrate your site key.
Usage
Sign-Up
Navigate to http://localhost:8000/login.html.
Fill out the sign-up form:
Email: Enter a unique email address.
Password: Set a password and confirm it.
Role: Select "Student" or "Admin".
Complete the reCAPTCHA challenge.
Submit to register. Credentials are stored in localStorage.
Login
On the same login.html page, use the login form:
Enter registered email, password, and select role.
Complete the reCAPTCHA challenge.
On successful login:
See the envelope animation with welcome audio.
Students redirect to index.html (application form).
Admins redirect to dashboard.html.
Student Application Submission
On index.html, fill out the application form:
Personal info: First name, last name, DOB, nationality.
Contact: Email, phone (with country code).
Gender: Male/Female.
Program: Choose from BSc. Computer Science, IT, or Telecommunications Engineering.
Submit to save the application in localStorage and redirect to view.html.
Viewing Applications
On view.html (accessible to students):
View a table of submitted applications.
Edit or delete individual applications.
Use animations for row additions/deletions.
Select multiple applications for bulk deletion.
Admin Dashboard
On dashboard.html (admin-only):
View metrics: Total and pending applications.
Manage applications in a table with edit/delete options.
Bulk delete or delete all applications.
Sidebar navigation for dashboard and logout.
File Structure
text

Collapse

Wrap

Copy
gctu-application-system/
├── assets/
│   ├── audio/
│   │   └── welcome.mp3              # Audio for login animation
│   └── images/
│       └── logo-gctu.png            # GCTU logo for header
├── scripts/
│   └── script.js                    # Main JavaScript logic
├── styles/
│   ├── apply.css                    # Styles for index.html
│   ├── dashboard.css                # Styles for dashboard.html
│   ├── login.css                    # Styles for login.html
│   ├── shared.css                   # Global styles
│   └── view.css                     # Styles for view.html
├── index.html                       # Student application form
├── login.html                       # Sign-up and login page
├── view.html                        # Application view page
├── dashboard.html                   # Admin dashboard
└── README.md                        # Project documentation
HTML Files:
index.html: Application submission form.
login.html: Squarish sign-up/login forms with reCAPTCHA.
view.html: Table for viewing/editing applications.
dashboard.html: Admin interface with metrics and management.
CSS Files:
shared.css: Global styles (typography, navigation, buttons, particles).
login.css: Squarish container, envelope animation, reCAPTCHA styling.
dashboard.css: Sidebar and metric card styles.
apply.css, view.css: Page-specific styles.
JavaScript:
script.js: Authentication, form handling, animations, reCAPTCHA mock verification.
Assets:
Logo and audio enhance the UI/UX.
Dependencies
The project uses CDN-hosted libraries:

GSAP: https://cdnjs.cloudflare.com/ajax/libs/gsap/3.11.5/gsap.min.js
intl-tel-input: https://cdn.tutorialjinni.com/intl-tel-input/17.0.19/js/intlTelInput.min.js and CSS.
country-list: https://cdn.jsdelivr.net/npm/country-list-with-dial-code-and-flag@5.1.0/dist/main.js
Google Fonts (Poppins): https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600;700&display=swap
Google reCAPTCHA: https://www.google.com/recaptcha/api.js
No local installations are required, but ensure internet connectivity for CDNs.

Google reCAPTCHA Setup
To enable reCAPTCHA for sign-up and login:

Register Your Site:
Visit https://www.google.com/recaptcha/admin.
Create a new site:
Label: e.g., "GCTU Application System".
Type: reCAPTCHA v2 Checkbox.
Domains: Add localhost (for testing) and your production domain.
Accept terms and submit to get:
Site Key: Public key for client-side.
Secret Key: Private key for server-side (keep secure).
Update login.html:
Replace YOUR_RECAPTCHA_SITE_KEY in both <div class="g-recaptcha" data-sitekey="YOUR_RECAPTCHA_SITE_KEY"></div> with your Site Key.
Example:
html

Collapse

Wrap

Copy
<div class="g-recaptcha" data-sitekey="6LfXXXXX"></div>
Client-Side Integration:
The script.js file retrieves the reCAPTCHA token using grecaptcha.getResponse().
For demo purposes, verifyRecaptcha assumes the token is valid if present.
Server-Side Verification (Production):
Implement a backend server (e.g., Node.js, PHP) to verify the token.
Send a POST request to:
text

Collapse

Wrap

Copy
https://www.google.com/recaptcha/api/siteverify
Parameters:
secret: Your Secret Key.
response: The token from grecaptcha.getResponse().
Check the response for success: true.
Example (Node.js with axios):
javascript

Collapse

Wrap

Run

Copy
const axios = require('axios');
async function verifyRecaptcha(token) {
  const response = await axios.post('https://www.google.com/recaptcha/api/siteverify', null, {
    params: { secret: 'YOUR_SECRET_KEY', response: token }
  });
  return response.data.success;
}
Testing:
Use localhost for development.
Ensure reCAPTCHA renders and validates on form submission.
Development Notes
Authentication:
Uses localStorage for user credentials and applications.
For production, replace with a secure backend (e.g., MongoDB, Firebase).
reCAPTCHA:
The mock verification in script.js is for demo purposes. Implement server-side verification in production.
Assets:
Replace logo-gctu.png and welcome.mp3 with actual files.
Ensure paths in HTML match your asset structure.
Extensibility:
Add a backend for persistent storage and real reCAPTCHA verification.
Enhance security with password hashing (e.g., bcrypt).
Add user profile management or application status tracking.
Browser Compatibility:
Tested on modern browsers (Chrome, Firefox, Edge).
Ensure CDN links are accessible.
Performance:
Optimize by minifying CSS/JS and lazy-loading assets.
Cache CDNs for faster load times.
Contributing
Contributions are welcome! To contribute:

Fork the repository.
Create a feature branch:
bash

Collapse

Wrap

Run

Copy
git checkout -b feature/your-feature
Commit changes:
bash

Collapse

Wrap

Run

Copy
git commit -m "Add your feature"
Push to the branch:
bash

Collapse

Wrap

Run

Copy
git push origin feature/your-feature
Open a pull request with a detailed description.
Please follow the WTF and ensure tests pass (if added).

License
This project is licensed under the WTF. You are free to use, modify, and distribute the code, provided you include the original copyright notice.

Acknowledgements
GSAP: For smooth animations.
intl-tel-input: For phone input functionality.
Google reCAPTCHA: For secure form submissions.
Poppins Font: For modern typography.
Unsplash: Background image in shared.css.
Contact
For questions or feedback:

Email: nwejegerard@gmail.com
GitHub Issues: Open an issue in this repository.
Linkedln: Gerard Nweje
Thank you for using the GCTU Application System! 🚀

