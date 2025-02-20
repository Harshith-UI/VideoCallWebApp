# Chime Video Call App

## Overview
This project is a basic video calling web application that uses AWS Chime for video conferencing. The backend is built with AWS Lambda (Python) and API Gateway, while the frontend is a simple static web page hosted on AWS Amplify.

## Backend Services

- **AWS Lambda (Python):**
  - Uses Boto3 to call the AWS Chime SDK Meetings API.
  - Creates a meeting and registers an attendee.
  - Returns meeting and attendee details as JSON.

- **API Gateway (HTTP API):**
  - Exposes the Lambda function via a RESTful POST endpoint (`/create-meeting`).
  - Configured with CORS to allow requests from the frontend.

- **IAM Roles/Policies:**
  - A custom IAM role is used to grant the Lambda function permissions for `chime-sdk-meetings:CreateMeeting` and `chime-sdk-meetings:CreateAttendee`.

## Frontend

- **Single-Page Application:**
  - A single `index.html` file contains the HTML, inline CSS, and JavaScript.
  - Uses the AWS Chime SDK for JavaScript to join the meeting using details obtained from the backend.

- **AWS Amplify Hosting:**
  - The app is deployed as a static site on AWS Amplify, making it easily accessible via a public URL.

## Usage

1. **Deploy the Backend:**
   - Set up the Lambda function and API Gateway endpoint via the AWS Console.
   - Ensure that CORS is enabled to allow the frontend to communicate with the API.

2. **Deploy the Frontend:**
   - Push the `index.html` file to a Git repository.
   - Connect the repository to AWS Amplify and deploy the site.

3. **Run the App:**
   - The frontend makes a POST request to `/create-meeting` to generate meeting and attendee details.
   - The meeting session is then initialized using the AWS Chime SDK.

## Notes
- Customize and extend the application (e.g., add screen sharing or chat) as needed.
- Verify all CORS settings and API configurations during development.

