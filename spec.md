Build a professional, modern, full-stack personal developer portfolio for P. Sreenivasulu using the MERN stack.

## 1. Technology Stack

Frontend:

* React.js with Vite
* JavaScript
* Tailwind CSS
* React Router
* Framer Motion
* Lucide React

Backend:

* Node.js
* Express.js
* MongoDB Atlas
* Mongoose
* REST APIs

Deployment:

* Vercel
* GitHub for version control

## 2. Developer Information

Name: P. Sreenivasulu

Education: B.Tech in Computer Science & Data Science at Aditya Institute of Technology and Management.

Expected graduation: 2029.

Programming languages: Java, Python, JavaScript.

Frontend skills: HTML, CSS, React.js.

Tools: Git and GitHub.

Current interests:

* Java programming
* Data Structures & Algorithms
* Web development
* Backend development
* Software engineering

Career interests:

* Software Development
* Backend Engineering

Do not invent employment history, certifications, awards, completed projects, coding statistics, or technical proficiency.

Use placeholders for information that has not been provided.

## 3. Design Requirements

Create a premium, minimal, dark-themed developer portfolio.

Use:

* Deep charcoal backgrounds
* Electric green accents
* White primary text
* Muted gray secondary text
* Subtle borders
* Rounded cards
* Generous spacing
* Modern typography
* Responsive layouts
* Subtle entrance animations

The website must look professional, polished, and distinctive without excessive visual effects.

Avoid generic templates, excessive gradients, unnecessary glowing elements, and distracting animations.

## 4. Pages

Implement:

* Home
* About
* Projects
* Project Details
* Skills
* DSA Journey
* Contact
* Custom 404

Use React Router for page navigation.

The homepage should also support smooth scrolling between its primary sections.

## 5. Homepage

Create:

* Sticky navigation
* Hero section
* Developer introduction
* Project CTA
* Resume download
* GitHub and LinkedIn links
* Current learning status
* Featured projects
* Skills overview
* DSA journey preview
* Contact CTA
* Footer

Use authentic content and clearly marked placeholders where necessary.

## 6. Projects

Retrieve project information from MongoDB through the Express API.

Each project should include:

* Title
* Unique slug
* Description
* Long description
* Technologies
* Category
* Thumbnail
* GitHub URL
* Live URL
* Featured status
* Completion status
* Timestamps

Implement project filtering by category.

Create project detail pages with:

* Overview
* Problem statement
* Solution
* Features
* Technology stack
* Screenshots
* Challenges
* Lessons learned
* Repository link
* Live demo link

Do not fabricate project information.

## 7. Skills

Group skills into:

* Programming
* Frontend
* Backend
* Database
* Tools

Retrieve skill data from MongoDB.

Distinguish existing skills from technologies currently being learned.

Avoid arbitrary proficiency percentages.

## 8. Contact Form

Implement fields for:

* Name
* Email
* Subject
* Message

Create a POST /api/contact endpoint.

Validate all inputs on the frontend and backend.

Store valid messages in MongoDB.

Add rate limiting, error handling, loading states, and user-friendly success and error messages.

Keep all credentials and email-service secrets on the server.

## 9. Database

Create Mongoose models for:

* Project
* Skill
* Message

Add validation, timestamps, appropriate indexes, and a unique project slug.

Use environment variables for the MongoDB connection string.

Handle database connection errors gracefully.

## 10. API

Implement:

* GET /api/projects
* GET /api/projects/featured
* GET /api/projects/:slug
* GET /api/skills
* GET /api/skills/:id
* POST /api/contact

Add optional project management endpoints only if authentication and authorization are implemented.

Never expose public project modification endpoints without protection.

## 11. Code Quality

Use reusable React components.

Keep API calls in a dedicated service layer.

Separate backend routes, controllers, models, configuration, and middleware.

Use consistent naming conventions.

Avoid unnecessarily complicated abstractions.

Add loading states, error states, empty states, and appropriate HTTP status codes.

Do not hardcode production credentials.

## 12. Accessibility and Performance

Ensure:

* Mobile-first responsive layouts
* Keyboard-accessible navigation
* Visible focus states
* Semantic HTML
* Accessible form labels
* Appropriate image alt text
* Reduced-motion support
* Optimized images
* SEO metadata
* Custom 404 page

## 13. Deployment

Prepare the application for Vercel deployment.

Use a deployment-compatible backend entry point.

Document the required environment variables.

Ensure frontend API requests use the correct production API configuration.

Explain any deployment-specific configuration before implementing it.

Do not assume that a conventional persistent Express server can be deployed unchanged as a serverless function.

## 14. Implementation Workflow

Build in the following order:

1. Initialize frontend and backend.
2. Configure styling and routing.
3. Build the responsive UI.
4. Create MongoDB models.
5. Implement REST APIs.
6. Connect React to the APIs.
7. Implement contact form storage.
8. Add error handling and security.
9. Test the application.
10. Configure Vercel deployment.
11. Write a README.

Before creating files, present the proposed folder structure.

Implement one phase at a time.

After each phase:

* Explain the files created.
* Explain how to run the application.
* Identify any environment variables needed.
* Test the implemented functionality.
* Resolve errors before proceeding.

The final result must be a working, maintainable MERN portfolio rather than just a static visual mockup.
