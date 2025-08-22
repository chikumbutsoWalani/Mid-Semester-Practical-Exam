# Course Enrollment System - Mid-Semester Practical Examination

**SCHOOL OF ENGINEERING - ELECTRICAL ENGINEERING DEPARTMENT**  
**BACHELOR OF ELECTRONICS AND COMPUTER ENGINEERING (BECE5)**  
**INTERNET AND WEB SERVICES (ELE-IWS-521)**

**Duration:** 2 Hours  
**Total Marks:** 60 marks  
**Date:** ___/___/2025

---

## 📋 STUDENT INFORMATION

**Student Name:** [Your Full Name]  
**Student ID:** [Your Student ID]  
**Course:** Internet and Web Services (ELE-IWS-521)  
**Examination Date:** ___/___/2025

---

## 🎯 EXAMINATION OVERVIEW

### **Project Scenario**
You are hired as a junior web developer for **MegaUniversity**. The Computer Science department needs an urgent solution for their **Course Enrollment System** before the new semester begins. The current paper-based system is inefficient and error-prone.

**Your Mission:** Build a complete web-based enrollment system that allows students to register for elective courses online and enables staff to manage enrollments efficiently.

### **Technologies Required**
- **Backend:** Node.js with Express.js framework
- **Middleware:** Body-parser for form data processing  
- **Frontend:** HTML5, CSS3, JavaScript, jQuery
- **Data Storage:** In-memory arrays (no database required)
- **Version Control:** Git with regular commits

---

## 📝 EXAMINATION INSTRUCTIONS

### **Setup Instructions**
1. **Repository Setup:** This is your GitHub Classroom repository
2. **Dependencies:** Run `npm install` to install required packages
3. **Development:** Create all required files as specified below
4. **Testing:** Use `npm start` to run your server
5. **Git Commits:** Make minimum 5 commits with descriptive messages
6. **Final Submission:** Push final commit with message "FINAL SUBMISSION"

### **Allowed Resources**
- ✅ Course lecture notes and materials
- ✅ Textbooks and assigned readings  
- ✅ Official documentation (Node.js, Express.js, jQuery)
- ✅ Previous lab assignments
- ❌ Internet research or external tutorials
- ❌ Collaboration with other students
- ❌ AI code generation tools

### **Time Management**
- **0-10 min:** Setup and planning
- **10-40 min:** Express server development
- **40-70 min:** HTML form development  
- **70-95 min:** CSS styling and responsive design
- **95-115 min:** JavaScript/jQuery functionality
- **115-120 min:** Advanced feature and final testing

---

## 📁 REQUIRED FILE STRUCTURE

Create the following file structure in your repository:

```
course-enrollment-system/
├── server.js                    ⭐ TO CREATE
├── package.json                 ✅ PROVIDED
├── README.md                    ✅ THIS FILE
├── .gitignore                   ✅ PROVIDED
└── public/                      ⭐ TO CREATE
    ├── index.html              ⭐ TO CREATE (Main enrollment form)
    ├── enrollments.html        ⭐ TO CREATE (View all enrollments)
    ├── courses.html            ⭐ TO CREATE (Available courses)
    ├── css/
    │   └── style.css           ⭐ TO CREATE
    └── js/
        └── script.js           ⭐ TO CREATE
```

---

## 📋 DETAILED TASK REQUIREMENTS

## **TASK 1: EXPRESS SERVER DEVELOPMENT (15 marks)**

### **Server Setup Requirements (4 marks)**
Create `server.js` with the following specifications:

**Required Imports and Setup:**
- Import Express.js framework
- Import body-parser middleware
- Create Express application instance
- Set server to run on port 3000

**Middleware Configuration:**
- Configure body-parser for URL-encoded form data
- Enable static file serving from 'public' directory
- Add basic error handling middleware

**Data Storage:**
- Create global array `enrollments = []` for storing enrollment data
- Create global variable `enrollmentIdCounter = 1` for unique IDs
- Create array `availableCourses` with at least 5 course objects

### **Route Implementation (7 marks)**

**Route 1: GET / (1.5 marks)**
- Serve the main enrollment form page (index.html)
- Handle file not found errors gracefully

**Route 2: POST /enroll (2.5 marks)**
- Extract form data from request body
- Validate all required fields (studentName, studentId, courseCode, semester)
- Create enrollment object with unique ID and timestamp
- Add enrollment to global enrollments array
- Send success response or redirect to confirmation page

**Route 3: GET /enrollments (1.5 marks)**
- Display all current enrollments
- Show enrollment details in HTML format
- Include navigation back to enrollment form

**Route 4: GET /courses (1 mark)**
- Display all available courses
- Show course details (code, name, instructor, credits)
- Include navigation to enrollment form

**Route 5: POST /unenroll/:id (0.5 marks)**
- Remove enrollment by ID from enrollments array
- Validate ID exists before deletion
- Provide success/error feedback

### **Data Structure Requirements (4 marks)**

**Enrollment Object Structure:**
```javascript
{
    id: 1,
    studentName: "John Doe",
    studentId: "2024-1234", 
    courseCode: "CS401",
    courseName: "Web Development",
    semester: "Fall 2025",
    reason: "Required for major",
    enrollmentDate: "2025-01-15T10:30:00Z"
}
```

**Course Object Structure:**
```javascript
{
    code: "CS401",
    name: "Advanced Web Development", 
    instructor: "Dr. Smith",
    credits: 3,
    capacity: 30
}
```

**Required Courses (minimum 5):**
- CS401 - Advanced Web Development
- CS402 - Database Systems
- CS403 - Software Engineering
- CS404 - Computer Networks
- CS405 - Artificial Intelligence

---

## **TASK 2: HTML FORM DEVELOPMENT (12 marks)**

### **Main Enrollment Form - index.html (6 marks)**

**Required HTML Structure:**
- Proper HTML5 doctype and meta tags
- Link to CSS stylesheet
- Include jQuery CDN and link to script.js
- Semantic HTML elements (header, nav, main, footer)

**Form Fields Required:**

**Student Full Name (1 mark)**
- Text input field
- Required attribute
- Minimum length: 2 characters
- Maximum length: 50 characters
- Placeholder text

**Student ID (1.5 marks)**
- Text input field  
- Required attribute
- Pattern validation: YYYY-NNNN format
- Placeholder: "2024-1234"

**Course Selection (1.5 marks)**
- Select dropdown element
- Required attribute
- Default "Choose a Course" option
- Minimum 5 course options with values matching course codes

**Semester Selection (1 mark)**
- Radio button group
- Required attribute
- Options: Fall 2025, Spring 2026, Summer 2026
- Proper labels associated with inputs

**Enrollment Reason (0.5 marks)**
- Textarea element
- Optional field
- Maximum length: 200 characters
- Placeholder text

**Form Buttons (0.5 marks)**
- Submit button with proper type
- Clear/Reset button
- Appropriate button text

### **Additional Pages (3 marks)**

**Enrollments Page - enrollments.html (1.5 marks)**
- Display all enrollments in organized layout
- Show: student name, ID, course, semester, enrollment date
- Include search/filter input field
- Navigation menu to other pages

**Courses Page - courses.html (1.5 marks)**
- List all available courses
- Display: course code, name, instructor, credits
- Include course descriptions
- Navigation menu to other pages

### **Navigation and Accessibility (3 marks)**

**Navigation Menu (1.5 marks)**
- Present on all pages
- Links to: Home (/), Enrollments (/enrollments), Courses (/courses)
- Styled navigation bar
- Active page indication

**Accessibility Features (1.5 marks)**
- All form inputs have associated labels
- Required fields marked with asterisk (*)
- Logical tab order throughout forms
- Semantic HTML5 elements used appropriately
- Alt text for any images used

---

## **TASK 3: CSS STYLING & RESPONSIVE DESIGN (12 marks)**

### **Visual Design Requirements (5 marks)**

**Color Scheme (1 mark)**
- Professional university-themed colors
- Consistent color palette throughout
- Good contrast ratios for accessibility
- Use CSS custom properties (variables)

**Typography (1 mark)**
- Professional font stack
- Proper font sizes and line heights
- Heading hierarchy (h1, h2, h3)
- Readable body text

**Header and Navigation (1.5 marks)**
- Professional header design
- University branding area
- Styled navigation menu
- Hover effects for navigation items

**Form Styling (1.5 marks)**
- Clean, modern form design
- Proper spacing between form elements
- Styled input fields with borders
- Focus states for all form elements
- Button styling with hover effects

### **Responsive Layout Design (4 marks)**

**Mobile-First Approach (2 marks)**
- Base styles designed for mobile devices
- Progressive enhancement for larger screens
- Flexible layouts using percentages or viewport units

**Breakpoint Implementation (2 marks)**
- Media queries for tablet (768px+) and desktop (1024px+)
- Appropriate layout changes at each breakpoint
- Navigation adapts to screen size
- Form layout optimizes for different screens

### **Interactive Elements (3 marks)**

**Button Interactions (1 mark)**
- Hover effects with smooth transitions
- Active/pressed states
- Disabled states where appropriate
- Consistent button styling

**Form Input States (1 mark)**
- Focus states with visual feedback
- Error states for validation
- Success states for valid inputs
- Smooth transitions between states

**Visual Feedback (1 mark)**
- Loading states or progress indicators
- Success/error message styling
- Smooth animations for user interactions
- Consistent visual language

---

## **TASK 4: JAVASCRIPT & JQUERY FUNCTIONALITY (15 marks)**

### **Form Validation (7 marks)**

**Real-time Validation (3 marks)**
- Student ID format validation as user types
- Display validation messages immediately
- Visual indicators for valid/invalid fields
- Prevent invalid characters in appropriate fields

**Pre-submission Validation (2 marks)**
- Validate all required fields before form submission
- Prevent submission if validation fails
- Show clear error messages for missing/invalid data
- Focus on first invalid field

**Visual Feedback (2 marks)**
- Highlight invalid fields with colors/borders
- Show success states for valid fields
- Display helpful error messages
- Clear validation messages when corrected

### **Interactive Features (5 marks)**
**Dynamic Course Information (2 marks)**
- Display course details when course is selected
- Show instructor, credits, and course description
- Update course capacity information
- Smooth transitions for content changes

**Search and Filter (2 marks)**
- Real-time search functionality for enrollments
- Filter enrollments by course, semester, or student
- Highlight search terms in results
- Clear search functionality

**User Experience Enhancements (1 mark)**
- Auto-format Student ID as user types (add hyphen)
- Character counter for textarea fields
- Confirmation dialogs for important actions
- Form auto-save functionality (optional)

### **Code Quality and Organization (3 marks)**
**Clean Code Structure (2 marks)**
- Well-organized functions with clear purposes
- Meaningful variable and function names
- Proper event handler organization
- Utility functions for common operations

**Error Handling (1 mark)**
- Try-catch blocks for risky operations
- Graceful handling of failed AJAX requests
- User-friendly error messages
- Fallback behaviors for failed operations

---

## **TASK 5: ADVANCED FEATURE IMPLEMENTATION (6 marks)**

**Choose ONE of the following advanced features to implement:**

### **Option A: Enrollment Analytics Dashboard**
**Requirements:**
- Create new route `/analytics` and corresponding HTML page
- Display enrollment statistics and trends
- Show total enrollments per course with visual representation
- Display enrollment distribution by semester
- Calculate and show most popular courses
- Include enrollment capacity utilization charts
- Real-time updates when new enrollments are added

### **Option B: Course Management System**
**Requirements:**
- Create administrative interface for course management
- Add new courses functionality with validation
- Edit existing course information
- Course capacity management and warnings
- Instructor assignment and management
- Course status management (active/inactive)
- Validation for all course data inputs

### **Option C: Student Profile Management**
**Requirements:**
- Individual student profile creation and editing
- View comprehensive student enrollment history
- Generate enrollment summary/transcript
- Student contact information management
- Profile photo upload capability (optional)
- Student academic information tracking
- Profile data validation and error handling

### **Option D: Advanced Search & Filtering**
**Requirements:**
- Multi-criteria search functionality
- Advanced filtering options (course, semester, student, date range)
- Sort enrollments by different fields (name, date, course)
- Export enrollment data to CSV or JSON format
- Pagination for large enrollment lists
- Saved search functionality
- Search result highlighting and statistics

---

## ✅ DETAILED COMPLETION CHECKLIST

### **Task 1: Express Server (15 marks)**
- [ ] Express app created and configured
- [ ] Body-parser middleware implemented
- [ ] Static file serving enabled
- [ ] Server runs on port 3000
- [ ] GET / route serves index.html
- [ ] POST /enroll route processes form data
- [ ] GET /enrollments route displays all enrollments
- [ ] GET /courses route shows available courses
- [ ] POST /unenroll/:id route removes enrollments
- [ ] Data validation for all form inputs
- [ ] Error handling for invalid requests
- [ ] In-memory storage arrays created
- [ ] Enrollment objects have proper structure
- [ ] Course objects have all required properties
- [ ] At least 5 courses defined

### **Task 2: HTML Development (12 marks)**
- [ ] Proper HTML5 doctype and structure
- [ ] CSS and JavaScript files linked correctly
- [ ] Semantic HTML elements used
- [ ] Student name input with validation attributes
- [ ] Student ID input with pattern validation
- [ ] Course selection dropdown with 5+ options
- [ ] Semester radio buttons with proper labels
- [ ] Enrollment reason textarea
- [ ] Submit and reset buttons
- [ ] Enrollments page displays enrollment data
- [ ] Courses page lists available courses
- [ ] Navigation menu on all pages
- [ ] All form labels properly associated
- [ ] Required fields marked clearly
- [ ] Accessibility features implemented

### **Task 3: CSS Styling (12 marks)**
- [ ] Professional color scheme implemented
- [ ] Typography hierarchy established
- [ ] Header and navigation styled
- [ ] Form elements styled consistently
- [ ] Button hover effects implemented
- [ ] Mobile-first responsive design
- [ ] Media queries for tablet and desktop
- [ ] Form layout adapts to screen size
- [ ] Interactive hover effects
- [ ] Focus states for form elements
- [ ] Error/success states styled
- [ ] Smooth transitions implemented

### **Task 4: JavaScript/jQuery (15 marks)**
- [ ] jQuery properly loaded and initialized
- [ ] Real-time Student ID format validation
- [ ] Pre-submission form validation
- [ ] Visual feedback for validation errors
- [ ] Dynamic course information display
- [ ] Search functionality for enrollments
- [ ] Filter functionality implemented
- [ ] Auto-format Student ID input
- [ ] Character counter for textarea
- [ ] Confirmation dialogs for actions
- [ ] Clean, organized JavaScript code
- [ ] Proper error handling
- [ ] Event handlers properly organized
- [ ] Utility functions created
- [ ] No console errors

### **Task 5: Advanced Feature (6 marks)**
**Selected Feature:** [Choose ONE]
- [ ] Option A: Analytics Dashboard
- [ ] Option B: Course Management
- [ ] Option C: Student Profiles  
- [ ] Option D: Advanced Search

**Implementation Requirements:**
- [ ] Feature fully functional
- [ ] Integrates well with existing system
- [ ] Provides clear user value
- [ ] Error handling implemented
- [ ] User interface is intuitive
- [ ] Documentation/help provided

---

## 🧪 TESTING REQUIREMENTS

### **Functional Testing**
- [ ] Server starts without errors (`npm start`)
- [ ] Homepage loads at http://localhost:3000
- [ ] All navigation links work correctly
- [ ] Form submission creates new enrollment
- [ ] Form validation prevents invalid submissions
- [ ] Enrollments page displays submitted data
- [ ] Courses page shows all available courses
- [ ] Delete functionality removes enrollments
- [ ] Search and filter features work
- [ ] Advanced feature functions correctly

### **Responsive Design Testing**
- [ ] Mobile view (320px - 768px) displays correctly
- [ ] Tablet view (768px - 1024px) displays correctly  
- [ ] Desktop view (1024px+) displays correctly
- [ ] Navigation works on all screen sizes
- [ ] Forms are usable on mobile devices
- [ ] Text remains readable at all sizes

### **Code Quality Testing**
- [ ] No JavaScript console errors
- [ ] No CSS validation errors
- [ ] HTML validates correctly
- [ ] Code is properly indented and formatted
- [ ] Variable names are meaningful
- [ ] Functions have clear purposes
- [ ] Comments explain complex logic

### **Git Repository Testing**
- [ ] Minimum 5 commits made
- [ ] Commit messages are descriptive
- [ ] All files properly tracked
- [ ] No unnecessary files committed
- [ ] Repository is properly organized

---

## 📊 MARKING SCHEME

### **Detailed Grade Distribution**

| Task | Component | Marks | Assessment Criteria |
|------|-----------|-------|-------------------|
| **Task 1** | Server Setup | 4 | Express config, middleware, static serving |
| | Route Implementation | 7 | All 5 routes working correctly |
| | Data Management | 4 | Proper structures, validation, storage |
| **Task 2** | Form Structure | 6 | Complete form with all required fields |
| | Additional Pages | 3 | Enrollments and courses pages |
| | Navigation/Accessibility | 3 | Semantic markup, labels, navigation |
| **Task 3** | Visual Design | 5 | Professional appearance, typography |
| | Responsive Layout | 4 | Mobile-friendly, media queries |
| | Interactive Elements | 3 | Hover effects, transitions, feedback |
| **Task 4** | Form Validation | 7 | Real-time and pre-submission validation |
| | Interactive Features | 5 | Dynamic content, search, UX enhancements |
| | Code Quality | 3 | Clean code, error handling, organization |
| **Task 5** | Advanced Feature | 6 | Implementation and integration quality |
| **Total** | | **60** | |

### **Grade Boundaries**
- **Excellent (54-60 marks):** All requirements met excellently, exceptional quality
- **Good (42-53 marks):** Most requirements met well, good implementation  
- **Satisfactory (30-41 marks):** Core requirements met, basic functionality working
- **Needs Improvement (<30 marks):** Significant issues, incomplete implementation

---

## 📝 SUBMISSION REQUIREMENTS

### **Git Repository Requirements**
- [ ] Minimum 5 commits with descriptive messages
- [ ] Regular commits throughout development process
- [ ] Final commit message: "FINAL SUBMISSION"
- [ ] All required files present and properly organized
- [ ] No unnecessary files (node_modules, logs, etc.)

### **Code Documentation**
- [ ] README.md updated with student information
- [ ] Comments explaining complex server logic
- [ ] Description of implemented advanced feature
- [ ] Testing checklist completed

### **Final Verification**
- [ ] Application runs without errors
- [ ] All functionality tested and working
- [ ] Responsive design verified
- [ ] No console errors or warnings
- [ ] Repository pushed to GitHub

---

## ⚠️ ACADEMIC INTEGRITY

### **Permitted Resources**
- Course lecture notes and slides
- Assigned textbooks and readings
- Official documentation (Node.js, Express.js, jQuery, MDN)
- Previous lab assignments and class exercises

### **Prohibited Actions**
- Collaboration with other students
- Copying code from external sources (Stack Overflow, GitHub, etc.)
- Using AI code generation tools (ChatGPT, GitHub Copilot, etc.)
- Accessing tutorial websites or video content
- Communication with anyone outside the examination room

### **Consequences**
- Any violation of academic integrity will result in examination failure
- Suspected violations will be investigated and reported
- All submissions are checked for originality and plagiarism

---

## 💡 SUCCESS STRATEGIES

### **Development Approach**
1. **Read all requirements carefully** before starting
2. **Plan your file structure** and approach
3. **Start with basic functionality** and build incrementally
4. **Test frequently** as you develop each feature
5. **Commit regularly** to save your progress
6. **Focus on core requirements** before advanced features

### **Time Management Tips**
- Allocate time proportionally to mark values
- Spend most time on server setup and functionality
- Don't spend too much time on visual perfection
- Leave buffer time for testing and debugging
- Make regular commits to protect your work

### **Technical Tips**
- Use `console.log()` for debugging server-side code
- Use browser developer tools for client-side debugging
- Test your application in different browsers
- Verify responsive design using browser dev tools
- Keep your code clean and well-organized

---

**Good luck with your examination! Focus on demonstrating the web development skills you've learned. Build a functional application that meets the core requirements, then enhance with styling and advanced features as time permits.**

**Remember: Working basic features are better than broken advanced features. Show us what you can create! 🚀💻🎓**

---

**END OF EXAMINATION INSTRUCTIONS**

---

## 🔧 Quick Reference

### **Essential Commands**
```bash
npm install          # Install dependencies
npm start           # Start the server
git add .           # Stage all changes
git commit -m ""    # Commit with message
git push           # Push to GitHub
```

### **Server Testing**
- Start server: `npm start`
- Open browser: `http://localhost:3000`
- Check console for errors
- Test all routes manually

### **Required Dependencies** (Already in package.json)
- express: Web framework
- body-parser: Form data processing
- nodemon: Development auto-restart (optional)

**Focus on functionality first, then styling, then advanced features. Work systematically and test often!**
