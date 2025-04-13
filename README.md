# CSS Layouts and Responsive Design

## Objectives

Implement Flexbox and Grid for layout design.
Make the webpage responsive using media queries.
Ensure proper alignment and spacing.

## Instructions

- use Flexbox or CSS Grid.
- Add a navigation bar and structure the content.
- Use media queries to adjust layout for mobile, tablet, and desktop.

>[!NOTE]
>  - Include at least:
>  - navigation bar
>  - media queries

# Tasks

- Apply Flexbox or Grid for layout.
- Make the page responsive.
- Test across different screen sizes.

Happy Coding! 💻✨

ANSWER
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Project Dashboard</title>
    <style>
        body {
            font-family: sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f4f4f4;
            color: #333;
        }

        /* Navigation Bar */
        nav {
            background-color: #333;
            color: white;
            padding: 1em;
        }

        nav ul {
            list-style: none;
            padding: 0;
            margin: 0;
            display: flex;
            justify-content: space-around; /* Distribute items evenly */
        }

        nav ul li a {
            color: white;
            text-decoration: none;
            padding: 0.5em 1em;
            border-radius: 5px;
            transition: background-color 0.3s ease;
        }

        nav ul li a:hover {
            background-color: #555;
        }

        /* Main Content */
        .container {
            padding: 20px;
        }

        .hero {
            background-color: #ddd;
            padding: 2em;
            margin-bottom: 20px;
            text-align: left; /* Align text to the left for a dashboard feel */
            border-radius: 8px;
        }

        .hero h1 {
            margin-top: 0;
            color: #333;
        }

        .hero p {
            color: #555;
            line-height: 1.6;
        }

        .button {
            display: inline-block;
            background-color: #007bff;
            color: white;
            padding: 0.8em 1.5em;
            text-decoration: none;
            border-radius: 5px;
            margin-top: 1em;
            transition: background-color 0.3s ease;
        }

        .button:hover {
            background-color: #0056b3;
        }

        .content-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr)); /* Responsive columns */
            gap: 20px;
        }

        .content-item {
            background-color: white;
            padding: 1.5em;
            border-radius: 8px;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
        }

        .content-item h3 {
            margin-top: 0;
            color: #333;
        }

        .content-item p {
            color: #555;
            line-height: 1.6;
        }

        .sidebar {
            background-color: #eee;
            padding: 1.5em;
            border-radius: 8px;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
        }

        .sidebar h3 {
            margin-top: 0;
            color: #333;
        }

        .sidebar ul {
            list-style: none;
            padding: 0;
        }

        .sidebar ul li a {
            display: block;
            padding: 0.5em 0;
            text-decoration: none;
            color: #007bff;
            transition: color 0.3s ease;
        }

        .sidebar ul li a:hover {
            color: #0056b3;
        }

        /* Footer */
        footer {
            background-color: #333;
            color: white;
            text-align: center;
            padding: 1em 0;
            position: sticky; /* Or fixed, depending on desired behavior */
            bottom: 0;
            width: 100%;
        }

        /* Media Queries */

        /* Mobile (up to 600px) */
        @media (max-width: 600px) {
            nav ul {
                flex-direction: column; /* Stack navigation items */
                align-items: center;
            }

            nav ul li {
                margin: 0.5em 0;
            }

            .container {
                padding: 10px;
            }

            .content-grid {
                grid-template-columns: 1fr; /* Single column for mobile */
            }

            .sidebar {
                display: none; /* Hide sidebar on mobile */
            }
        }

        /* Tablet (601px to 960px) */
        @media (min-width: 601px) and (max-width: 960px) {
            .container {
                padding: 15px;
            }

            .content-grid {
                grid-template-columns: repeat(auto-fit, minmax(350px, 1fr)); /* Adjust column width */
            }
        }

        /* Desktop (961px and above) */
        @media (min-width: 961px) {
            .container {
                display: grid;
                grid-template-columns: 3fr 1fr; /* Main content takes more space */
                gap: 20px;
                padding: 20px;
            }

            .content-grid {
                /* Content grid remains the same or can be adjusted */
            }
        }
    </style>
</head>
<body>
    <nav>
        <ul>
            <li><a href="#">Dashboard</a></li>
            <li><a href="#">Tasks</a></li>
            <li><a href="#">Team</a></li>
            <li><a href="#">Reports</a></li>
        </ul>
    </nav>

    <div class="container">
        <section class="hero">
            <h1>Project "Phoenix" - Status Overview</h1>
            <p>Welcome to the project dashboard. Here you can find a summary of the current status, key milestones, and team updates for Project Phoenix.</p>
            <p>Current Status: <strong style="color: green;">On Track</strong></p>
            <a href="#" class="button">View Detailed Report</a>
        </section>

        <section class="content-grid">
            <div class="content-item">
                <h3>Upcoming Milestone: Phase 2 Completion</h3>
                <p>The deadline for completing Phase 2 (Development) is **April 26, 2025**. The team is currently focused on finalizing the core features and addressing critical bugs.</p>
                <p>Progress: **75% Complete**</p>
                <a href="#">View Phase 2 Details</a>
            </div>
            <div class="content-item">
                <h3>Key Risk: Third-Party API Integration</h3>
                <p>We are closely monitoring the integration with the external payment gateway API. There have been minor delays on their end, but we have a contingency plan in place.</p>
                <p>Status: <strong style="color: orange;">Monitoring</strong></p>
                <a href="#">View Risk Assessment</a>
            </div>
            <div class="content-item">
                <h3>Team Update: New UI/UX Designer Onboarded</h3>
                <p>We are pleased to welcome Sarah Chen to the team as our new UI/UX Designer. She will be contributing to the user interface enhancements in the next phase.</p>
                <p>Joined On: **April 10, 2025**</p>
                <a href="#">Meet the Team</a>
            </div>
            <div class="content-item">
                <h3>Budget Status: Within Budget</h3>
                <p>The project is currently tracking within the allocated budget. A detailed financial report will be shared at the end of the month.</p>
                <p>Variance: **+5% (Contingency)**</p>
                <a href="#">View Budget Report</a>
            </div>
        </section>

        <aside class="sidebar">
            <h3>Quick Links</h3>
            <ul>
                <li><a href="#">Project Timeline</a></li>
                <li><a href="#">Meeting Minutes</a></li>
                <li><a href="#">Document Repository</a></li>
                <li><a href="#">Communication Plan</a></li>
                <li><a href="#">Risk Register</a></li>
            </ul>
        </aside>
    </div>

    <footer>
        <p>&copy; 2025 Project Phoenix Dashboard</p>
    </footer>
</body>
</html>
