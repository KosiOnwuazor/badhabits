Getting Started
Prerequisites
Before running the app, ensure that you have the following installed:

Node.js (LTS version is recommended)
npm (Node package manager)
Installation
Clone this repository to your local machine:

git clone https://github.com/your-username/bad-habit-app.git
cd bad-habit-app
Install the required dependencies:

npm install
Ensure that the database.sqlite file exists or is created automatically. The app will create a table for storing habits if it doesn't already exist.

Running the Application
Start the server:

node server.js
The server will start running at http://localhost:3000.

API Endpoints
The app exposes the following API endpoints:

1. GET /api/habits
Description: Get all habits (both good and bad) stored in the database.
Example request:

curl http://localhost:3000/api/habits
2. GET /api/habits/:id
Description: Get a specific habit by its id.
Example request:

curl http://localhost:3000/api/habits/1
3. POST /api/habits
Description: Add a new habit to the database (good or bad).
Request body (JSON):
json

{
  "name": "Exercise",
  "type": "good"
}
Example request (using curl):

curl -X POST http://localhost:3000/api/habits -H "Content-Type: application/json" -d '{"name": "Exercise", "type": "good"}'
4. PUT /api/habits/:id
Description: Increment the count of a habit (e.g., mark it as done for the day).
Example request:

curl -X PUT http://localhost:3000/api/habits/1
5. GET /api/advice
Description: Get advice for bad habits that have a count greater than or equal to 3.
Example request:

curl http://localhost:3000/api/advice
Project Structure

/bad-habit-app
  ├── /public         # Static files (HTML, CSS, JS)
  ├── server.js       # The main backend server code (Express)
  ├── database.sqlite # SQLite database file
  ├── package.json    # npm dependencies and scripts
  ├── README.md       # This file
Troubleshooting
Error: Database does not exist: If the database.sqlite file is missing, it will be created automatically when the app is run, and the habits table will be initialized. Ensure your database file has the correct permissions.

Server not starting: If the server fails to start, try checking the dependencies or ensure that Node.js and npm are correctly installed.

Bad Request Error (400): If you receive a 400 Bad Request error when adding a habit, it might be because the required fields name and type are missing. Make sure to provide both fields when creating a new habit.

License
This project is licensed under the MIT License - see the LICENSE file for details.

Future Enhancements
Implement a frontend for users to interact with the app through a web interface.
Add authentication for personalized habit tracking.
Track habit streaks and provide more personalized advice.
Provide notifications or reminders for habits.
Conclusion
This project helps track and manage habits, providing helpful advice based on recurring bad habits. It's ideal for college students or anyone looking to break free from distractions and manage their time more effectively.

How it Works with the Code
Database Setup: The app automatically creates the habits table in SQLite if it doesn't exist, and the table stores habits with columns id, name, type, and count.
API Endpoints: The endpoints interact with the SQLite database to fetch, insert, and update habits.
User Input: Users can add habits through the POST /api/habits endpoint and update counts for habits through the PUT /api/habits/:id endpoint. They can also get feedback on recurring bad habits via the GET /api/advice endpoint.

This README.md file is aligned with the app's structure and usage. It guides the user on installing the app, running the server, and interacting with the available API endpoints. If there are further changes or features added to the app, the README.md can be easily updated to reflect them.
