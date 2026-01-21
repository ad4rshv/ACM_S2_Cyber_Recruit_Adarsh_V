Interactive Cyber Incident Response Simulation

ACM Recruitment Task Write-Up

📌 Introduction

This task was given as part of the ACM recruitment process.
The objective was not only to run the given application, but to understand how it works, analyze its design, and reason about cybersecurity concepts used inside it.

The application is a Flask-based interactive simulation that walks a user through different stages of a cyber security incident, from detecting something suspicious to preventing it from happening again.

The task helped me understand how theory concepts can be converted into a simple and interactive system.

🎯 Purpose of the Application

The main goal of this application is to teach non-technical users how a cyber incident usually unfolds.

Instead of directly explaining concepts, the app:

Shows alerts

Asks questions

Lets users make decisions

Scores them based on instincts and reasoning

This makes learning more engaging and realistic.

🧩 How the Application Works

The application is built using Flask and uses multiple routes to control the flow.

🔹 Starting Point (/)

When the user opens the application, the index page is loaded.
At this point:

A session is started

The timer begins

Scores are initialized

The user is redirected to the first stage

🔹 Stage System (/stage/<id>)

Each stage represents a phase of a cyber incident, such as:

Suspicious login

Data access

Damage control

Cleanup

Prevention

Each stage contains:

An alert message

One or more questions (MCQ or text)

Expected answers for scoring

The user must complete one stage before moving to the next, so skipping stages is not possible.

🔹 Scoring Mechanism

The scoring is divided into three parts:

Correct instincts (40 points)

Right decisions (40 points)

Explanation (20 points)

MCQ answers are easier to score accurately, while text answers are evaluated using simple keyword matching.

Because of this, sometimes even correct explanations may not receive full points, which is a limitation of the current logic.

📊 Result Analysis

After completing all stages, the results page shows:

Time taken

Individual score breakdown

Total score out of 100

The final section maps the actions to Incident Response Lifecycle phases, such as:

Detection

Containment

Eradication

Recovery

Lessons Learned

This helped connect practical actions to real cybersecurity frameworks.

⚠️ Observed Limitations

While analyzing the application, I noticed some limitations:

The Flask secret key is hardcoded

Global statistics are stored in memory and reset on restart

Text-based scoring is very basic

Debug mode should not be enabled in production

No input sanitization for text responses

These are acceptable for a learning simulation but would need improvement in a real-world system.

🔧 Possible Improvements

If I were to extend this task further, I would:

Improve explanation scoring using keyword lists

Store statistics in a database instead of memory

Use environment variables for secrets

Add feedback after each stage to help learning

What I Learned From This Task

Through this task, I learned:
How Flask handles routing and sessions
Why HTTP being stateless makes sessions necessary
How cyber incidents follow a step-by-step response flow
How system limitations can affect automated evaluation
How to analyze code instead of just running it
This task helped me think more like an engineer rather than only focusing on output.

Conclusion

Overall, this task was a good mix of technical understanding and logical reasoning.
It was less about writing large amounts of code and more about understanding why things work the way they do.

This experience also showed how cybersecurity concepts can be simplified without losing their core meaning.
