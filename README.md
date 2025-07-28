# Front-End-Developer-Offline-Device-Dashboard-Test
"Single Page Application that helps IT teams monitor and identify offline IoT devices. The dashboard consumes data from a REST API and displays devices that have been idle for longer than specified durations, making it easy to troubleshoot connectivity issues."
1. 📦 API Behavior
The API responded quickly with structured JSON data.

The last_seen_at timestamp was assumed to follow ISO 8601 format and was converted using JavaScript's Date object.

The response did not contain status or location, so "N/A" or placeholders were used in the UI.

2. 🛠 Troubleshoot Button
The "Troubleshoot" button logs the device name and ID to the console for demonstration, as no backend endpoint was provided.

3. 🔄 Field Differences & Error Handling
Since some fields might be optional or missing, optional chaining (?.) and default fallbacks ("N/A") were used to prevent runtime errors.

4. 🧱 UI Responsiveness
Both Table and Card views were implemented.

Layout is fully responsive for typical mobile and desktop sizes.

Further improvements can be made for devices under 320px width.

5. 💾 Offline Persistence
Implemented optional localStorage caching of the most recent successful API fetch.

Helps retain data on reload or offline mode (bonus feature).

🧪 How to Test the App
▶️ Run the App Locally

npm install
npm run dev
Visit the app at:
🔗 http://localhost:5173

✅ Manual Testing Checklist
Enter Input:

Client: hkmu, ibm, or innoport

Idle Hour: e.g., 12

Click Fetch Devices

Expected Behaviors:

Devices matching the criteria appear

Toggle between Table View and Card View

Devices idle for more than 24 hours show red background

A summary statistic shows total idle devices

If no results: “No idle devices found” is displayed

Input validation prevents empty or invalid values

Errors handled gracefully (e.g., invalid client, network issue)

🔬 Optional: Jest Testing (If Implemented)
Run unit tests using:

npm run test
Potential test coverage:

API fetch success & error handling

Input field validations

View toggle functionality

Component rendering with mock data

🧼 Clear Cached Data
To reset cached results stored in localStorage:

Open Developer Tools in your browser

Go to Application → Local Storage

Remove the key: idleDeviceData

Refresh the app
