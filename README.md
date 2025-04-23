<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Zakaria - Sport Management Consultant</title>
    <style>
        /* Color Palette (Adaptable) */
        :root {
            --primary-color: #007bff; /* A professional blue */
            --secondary-color: #6c757d; /* A muted gray */
            --accent-color: #28a745;   /* A success/growth green */
            --background-color: #f8f9fa; /* Light gray background */
            --text-color: #343a40;     /* Dark gray text */
            --light-text-color: #ffffff; /* White text on darker backgrounds */
            --success-color: #198754;   /* A distinct success green */
        }

        /* Basic Reset and Body Styles */
        body {
            font-family: 'Arial', sans-serif; /* A clean, readable font */
            margin: 0;
            padding: 0;
            background-color: var(--background-color);
            color: var(--text-color);
            line-height: 1.6;
        }

        /* Header Styles */
        header {
            background-color: var(--primary-color);
            color: var(--light-text-color);
            padding: 20px 0;
            text-align: center;
        }

        header h1 {
            margin: 0;
            font-size: 2.5em;
        }

        nav ul {
            list-style: none;
            padding: 0;
            margin: 10px 0;
            display: flex; /* Horizontal navigation */
            justify-content: center;
        }

        nav ul li {
            margin: 0 15px;
        }

        nav a {
            color: var(--light-text-color);
            text-decoration: none;
            font-weight: bold;
            transition: color 0.3s ease; /* Smooth hover effect */
        }

        nav a:hover {
            color: var(--accent-color);
        }

        /* Main Content Styles */
        main {
            padding: 20px;
            max-width: 960px; /* Limit content width for readability */
            margin: 0 auto;
        }

        section {
            margin-bottom: 30px;
        }

        section h2 {
            color: var(--primary-color);
            border-bottom: 2px solid var(--primary-color);
            padding-bottom: 5px;
        }

        /* Meeting Request Form Styles */
        .meeting-form {
            background-color: var(--light-text-color);
            padding: 20px;
            border-radius: 8px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1); /* Subtle shadow */
            position: relative; /* For positioning the message */
        }

        .form-group {
            margin-bottom: 15px;
        }

        label {
            display: block;
            margin-bottom: 5px;
            font-weight: bold;
            color: var(--text-color);
        }

        input[type="text"],
        input[type="email"],
        input[type="tel"],
        textarea,
        select {
            width: 100%;
            padding: 10px;
            border: 1px solid #ddd;
            border-radius: 4px;
            box-sizing: border-box;
            font-size: 1em;
            color: var(--text-color);
        }

        input[type="text"]:focus,
        input[type="email"]:focus,
        input[type="tel"]:focus,
        textarea:focus,
        select:focus {
            outline: none; /* Remove default focus outline */
            border-color: var(--primary-color); /* Highlight on focus */
            box-shadow: 0 0 5px rgba(0, 123, 255, 0.5); /* Subtle focus shadow */
        }

        button {
            background-color: var(--accent-color);
            color: var(--light-text-color);
            padding: 12px 20px;
            border: none;
            border-radius: 4px;
            cursor: pointer;
            font-size: 1.1em;
            transition: background-color 0.3s ease;
        }

        button:hover {
            background-color: #218838; /* Darker green on hover */
        }

        .form-message {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            background-color: rgba(255, 255, 255, 0.9);
            padding: 20px;
            border-radius: 8px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.2);
            text-align: center;
            color: var(--success-color);
            font-weight: bold;
            font-size: 1.2em;
            display: none; /* Hidden by default */
        }

        /* Footer Styles */
        footer {
            background-color: var(--secondary-color);
            color: var(--light-text-color);
            text-align: center;
            padding: 10px 0;
            font-size: 0.9em;
        }

        /* Responsive Design (Basic) */
        @media (max-width: 768px) {
            nav ul {
                flex-direction: column; /* Stack navigation on smaller screens */
                align-items: center;
            }

            nav ul li {
                margin: 10px 0;
            }

            header h1 {
                font-size: 2em; /* Smaller heading on smaller screens */
            }
        }
    </style>
    <script>
        function submitForm(event) {
            event.preventDefault(); // Prevent the default form submission

            const form = document.querySelector('.meeting-form');
            const formData = new FormData(form);

            fetch("https://formspree.io/f/{your_form_id}", { // REPLACE WITH YOUR FORMSPREE ID
                method: 'POST',
                body: formData,
                headers: {
                    'Accept': 'application/json'
                }
            })
            .then(response => response.json())
            .then(data => {
                if (data.ok) {
                    const messageDiv = document.createElement('div');
                    messageDiv.classList.add('form-message');
                    messageDiv.textContent = 'Complete! Thank you for your request. We will be in touch soon.';
                    form.appendChild(messageDiv);

                    const formElements = form.querySelectorAll('label, input, textarea, select, button');
                    formElements.forEach(element => {
                        element.style.display = 'none';
                    });
                } else {
                    alert("There was an error submitting your request. Please try again later.");
                }
            })
            .catch((error) => {
                alert("There was an error submitting your request. Please try again later.");
            });
        }
    </script>
</head>
<body>
    <header>
        <h1>Zakaria - Sport Management and organizational governance Consultant</h1>
        <nav>
            <ul>
                <li><a href="#about">About Me</a></li>
                <li><a href="#services">Services</a></li>
                <li><a href="#contact">Contact</a></li>
                <li><a href="#meeting">Book a Meeting</a></li>
            </ul>
        </nav>
    </header>

    <main>
        <section id="about">
            <h2>About Me</h2>
            <p>As a sport management consultant, I bring a dynamic blend of strategic insight and practical expertise to help organizations thrive within the ever-evolving sports landscape. Whether you're looking to optimize operational efficiency, develop innovative marketing strategies, enhance revenue generation, or navigate the complexities of governance and compliance, I offer tailored solutions designed to achieve your unique goals and drive sustainable success. Let's collaborate to unlock your organization's full potential and make a lasting impact in the world of sport.</p>
        </section>

        <section id="services">
            <h2>Services</h2>
            <ul>
                <li>Carriere management</li>
                <li>Media</li>
                <li>Marketing</li>
                <li>[And more...]</li>
            </ul>
        </section>

         <section id="contact">
            <h2>Contact</h2>
            <p>Email: zakaria692003@gmail.com</p>
            <p>Phone: +212612953960</p>
        </section>

        <section id="meeting">
            <h2>Book a Meeting</h2>
            <p>Please fill out the form below to request a meeting. I will get back to you as soon as possible to confirm availability.</p>
            <div class="meeting-form">
                <form action="https://formspree.io/f/{your_form_id}" method="POST" onsubmit="submitForm(event)">
                    <div class="form-group">
                        <label for="name">Name:</label>
                        <input type="text" id="name" name="name" required>
                    </div>
                    <div class="form-group">
                        <label for="email">Email:</label>
                        <input type="email" id="email" name="_replyto" required>
                        <input type="hidden" name="_subject" value="New Meeting Request from Website">
                    </div>
                    <div class="form-group">
                        <label for="phone">Phone Number (Optional):</label>
                        <input type="tel" id="phone" name="phone">
                    </div>
                    <div class="form-group">
                        <label for="subject">Subject:</label>
                        <input type="text" id="subject" name="subject">
                    </div>
                    <div class="form-group">
                        <label for="meeting-type">Type of Meeting:</label>
                        <select id="meeting-type" name="meeting-type">
                            <option value="initial-consultation">Initial Consultation</option>
                            <option value="project-discussion">Project Discussion</option>
                            <option value="follow-up">Follow-up Meeting</option>
                            <option value="other">Other</option>
                        </select>
                    </div>
                    <div class="form-group">
                        <label for="preferred-date">Preferred Date(s) and Time(s):</label>
                        <textarea id="preferred-date" name="preferred-date" rows="4" placeholder="Please provide your preferred dates and times."></textarea>
                    </div>
                    <div class="form-group">
                        <label for="message">Additional Information (Optional):</label>
                        <textarea id="message" name="message" rows="5" placeholder="Please provide any additional information that might be helpful."></textarea>
                    </div>
                    <button type="submit">Request Meeting</button>
                </form>
            </div>
        </section>
    </main>

    <footer>
        &copy; 2025 Zakaria - Sport Management Consultant
    </footer>

    <script>
        function submitForm(event) {
            event.preventDefault(); // Prevent the default form submission

            const form = document.querySelector('.meeting-form');
            const formData = new FormData(form);

            fetch("https://formspree.io/f/{your_form_id}", { // REPLACE WITH YOUR FORMSPREE ID
                method: 'POST',
                body: formData,
                headers: {
                    'Accept': 'application/json'
                }
            })
            .then(response => response.json())
            .then(data => {
                if (data.ok) {
                    const messageDiv = document.createElement('div');
                    messageDiv.classList.add('form-message');
                    messageDiv.textContent = 'Complete! Thank you for your request. We will be in touch soon.';
                    form.appendChild(messageDiv);

                    const formElements = form.querySelectorAll('label, input, textarea, select, button');
                    formElements.forEach(element => {
                        element.style.display = 'none';
                    });
                } else {
                    alert("There was an error submitting your request. Please try again later.");
                }
            })
            .catch((error) => {
                alert("There was an error submitting your request. Please try again later.");
            });
        }
    </script>
</body>
</html>
