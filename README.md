I want to create a production-ready full stack web application using React (frontend) and Python (backend, preferably using FastAPI or Flask). 

The goal of the app is to allow users to run AppEngine commands from a user-friendly interface and display the command output.

✅ FRONTEND:
- Build a React web app UI.
- The UI should have:
  - A dropdown or input field to select the cluster (options: im1, im2).
  - Input fields for:
    - Family Name (e.g., csm)
    - App Name (e.g., smz)
    - Environment (e.g., prod)
  - A button labeled: "Check App Status".
  - When button is clicked, send the data to the backend via API call.
  - Display the output from the backend in a formatted way (like a terminal view or styled text area).

✅ BACKEND:
- Use Python (FastAPI preferred for async support and easy API integration).
- The backend should:
  - Expose a POST endpoint `/check_status`.
  - Accept a JSON body with:
    - cluster_name
    - family_name
    - app_name
    - environment
  - First run the command: `engine target <cluster_name>`
  - Then run the command: `engine app status <family_name>.<app_name> --env-<environment>`
  - Capture the command output (stdout).
  - Return the output as JSON to the frontend.

✅ Other:
- Handle errors gracefully (e.g., command fails or invalid input).
- Use appropriate loading indicators on the frontend while command is running.
- Structure the project cleanly for future extensibility (add deploy/scale later).
