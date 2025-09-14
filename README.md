# X4UTimelineCleanup
html and api timeline cleanup for you (untested)

X For You Timeline Cleaner
This project provides a web-based tool to help users clean up their "For You" timeline on X, making it more relevant by leveraging the X API for supported actions and guiding users through manual steps where API access is limited. The tool includes a checklist interface to track progress through recommended cleanup steps.
Features

Authentication: Uses OAuth 2.0 with PKCE to securely authenticate with your X account.
Checklist Interface: Step-by-step guide with checkboxes to track completion of timeline cleanup tasks.
API Integration: Supports actions like unfollowing, muting, blocking, creating lists, bulk unliking, and deleting tweets (requires Basic or higher X API tier).
Manual Guidance: For actions not supported by the free X API tier, clear instructions are provided for manual execution within the X app or website.
Responsive Design: Simple, clean UI styled with basic CSS for usability on both desktop and mobile.

Prerequisites

X Developer Account: Create an app at developer.x.com to obtain a Client ID.
API Tier: The free tier supports limited read-only operations. For full functionality (e.g., unfollow, mute, block, bulk unlike/delete), a Basic ($100/month) or higher tier is required due to X API restrictions as of August 2025.
Local Server: Run the tool locally (e.g., via Python's http.server) to handle OAuth redirects.

Setup

Clone the Repository:git clone https://github.com/yourusername/x-timeline-cleaner.git
cd x-timeline-cleaner


Set Up X Developer App:
Go to developer.x.com and create a new app.
Obtain your Client ID.
Set the OAuth 2.0 redirect URI to http://localhost:8000/cleaner.html (or your hosted URL).
Enable OAuth 2.0 with PKCE in the app settings.


Run Locally:
Serve the cleaner.html file using a local server:python3 -m http.server 8000


Open http://localhost:8000/cleaner.html in your browser.


Authenticate:
Enter your Client ID and redirect URI (default: http://localhost:8000/cleaner.html).
Click "Authorize with X" to log in and grant permissions.


Use the Tool:
Follow the checklist, checking off completed steps.
For API-supported actions (e.g., unfollow, mute), enter usernames and click the respective buttons.
For manual steps (e.g., muting words), follow the provided instructions in the X app.



API Limitations

Free Tier: Limited to read-only operations (e.g., fetching user IDs, likes) and very restricted write actions (e.g., 100 posts/month, no unfollow/mute/block). Bulk operations like unliking or deleting tweets are capped or blocked.
Basic Tier: Required for full functionality (e.g., 10,000 posts/month, access to unfollow, mute, block endpoints). Check X API pricing for details.
Rate Limits: Even with Basic tier, expect rate limits (e.g., 50 tweet deletes/day, 15 list creations/month). The tool handles pagination for bulk actions but may take time due to API constraints.

Steps Covered
The tool guides you through the following steps to clean your For You timeline:

Switch to Following Timeline: Toggle to a chronological feed (manual, no API).
Mark "Not Interested": Flag irrelevant posts in the X app (manual).
Unfollow/Mute Accounts: Unfollow or mute via API (Basic tier) or manually.
Mute Words/Topics: Filter keywords/topics in X settings (manual).
Clear History: Bulk unlike tweets (Basic tier) or clear searches manually.
Use X Lists: Create/add to lists via API (limited on free tier) or manually.
Block Spam: Block accounts via API (Basic tier) or manually.
Bulk Delete Tweets/Followers: Delete tweets (capped on free tier) or remove followers (Basic tier).

Usage Notes

Free Tier Users: Expect errors for write actions (e.g., 403 Forbidden for unfollow/mute). Use the tool as a guide for manual cleanup in the X app.
Be Patient: Algorithm changes take 1–2 weeks to reflect. Avoid engaging with unwanted content to train the algorithm effectively.
Backup Data: Before bulk deleting tweets/likes, download your X archive (Settings > Your account > Download an archive).
Security: The tool uses PKCE for secure OAuth and stores tokens locally. Do not share your Client ID or tokens.

Contributing
Contributions are welcome! To contribute:

Fork the repository.
Create a feature branch (git checkout -b feature/your-feature).
Commit changes (git commit -m 'Add your feature').
Push to the branch (git push origin feature/your-feature).
Open a pull request.

Please ensure code follows the existing style and includes comments for clarity.
License
This project is licensed under the MIT License. See the LICENSE file for details.
Disclaimer
This tool is provided as-is and relies on the X API, which may change. Some features may not work due to API restrictions or rate limits. Always review X's terms of service and API policies before use.
