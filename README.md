# Smart-Garden-Log-Application

🪴 Smart Garden Log
A simple yet effective web application designed to help gardeners and nature hobbyists track and manage their plants' needs and growth.

💡 Concept
The Smart Garden Log aims to simplify plant care by providing a centralized system to log essential information, set reminders, and track the progress of your beloved plants. No more guessing when to water or fertilize – let the app keep you organized!

🔧 Features
Add Plants: Easily add new plants to your log with customizable details.

Set Sunlight Needs: Choose from options like Full Sun, Partial Sun, Partial Shade, or Full Shade.

Define Watering Frequency: Specify how often your plant needs water (in days).

Set Fertilizing Frequency: Track how often to fertilize (in days), with an option to set to 0 if not applicable.

Water/Fertilize Log & Reminder System:

Quickly log when you last watered or fertilized a plant with a single click.

The app automatically calculates and displays the next due date for watering and fertilizing.

Visual Reminders: Plant cards will highlight (red border and pulse animation) when watering or fertilizing is due, ensuring you never miss a crucial care step.

Photo Upload & Growth Tracker:

Add detailed growth logs for each plant, including notes.

Upload photos to visually track your plant's growth over time.

View a comprehensive growth history for any plant, sorted by date.

Edit & Delete Plants: Easily update plant details or remove plants from your log.

Persistent Storage: All your plant data and growth logs are securely saved using Firestore (Firebase), so your information is always available across sessions.

User-Friendly Interface: Built with Tailwind CSS for a clean, modern, and responsive design that works well on various devices.

Custom Modals: Utilizes custom modal dialogs for a consistent and non-disruptive user experience, replacing native browser alerts and confirms.

🚀 How to Use
Add a New Plant: Click the "Add New Plant" button. Fill in the plant's name, select its sunlight needs, and specify watering and fertilizing frequencies. Click "Save Plant".

Manage Your Plants: Your added plants will appear as cards on the main page.

Log Actions: Click the "💧 Log Water" or "🧪 Log Fertilize" buttons to record the current date as the last time you performed that action.

Edit Plant Details: Click the pencil icon on a plant card to modify its information.

Delete Plant: Click the trash can icon to remove a plant (a confirmation will appear).

Track Growth:

Add Growth Log: Click the "📈 Add Growth Log" button on a plant card. You can add notes and upload a photo to document its progress.

View Growth History: Click the "📚 View History" button to see all recorded growth logs and photos for that plant.

Reminders: Keep an eye on the plant cards. If a plant's "Next Water" or "Next Fertilize" date is today or in the past, its card will be visually highlighted to remind you.

💻 Technologies Used
HTML5: For the structure of the web application.

Tailwind CSS: A utility-first CSS framework for rapid and responsive styling.

JavaScript (ES6+): For all the interactive logic, data handling, and DOM manipulation.

Firebase:

Firestore: A NoSQL cloud database used for real-time data storage and synchronization of plant information and growth logs.

Firebase Authentication: Used for anonymous user authentication to manage private user data.

🛠️ Setup (for local development)
This application is designed to run directly in a browser environment that provides the __app_id and __firebase_config global variables, typically within a specialized platform.

To run this code in a standard local development environment, you would need to:

Set up a Firebase Project:

Go to the Firebase Console.

Create a new project.

Enable Firestore Database and Authentication (specifically, enable Anonymous authentication).

Get Your Firebase Config: In your Firebase project settings, find your web app's configuration object.

Update the Code: Replace the placeholder __app_id and __firebase_config variables in the <script type="module"> section with your actual Firebase project ID and config object.

Set Firestore Security Rules:
To allow users to read and write their own data, you'll need to set up Firestore Security Rules. Here's an example for private user data:

rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    match /artifacts/{appId}/users/{userId}/{documents=**} {
      allow read, write: if request.auth != null && request.auth.uid == userId;
    }
  }
}

Open in Browser: Save the HTML file and open it directly in your web browser.

Enjoy tracking your garden's journey with the Smart Garden Log!
