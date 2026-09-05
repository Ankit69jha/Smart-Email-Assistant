# Smart Email Assistant

An AI-powered email assistant that automatically summarizes emails and generates smart replies, built with **Spring Boot**, **React**, and **Spring AI**.

## Overview

Smart Email Assistant helps users cut down time spent reading and responding to emails. Paste in an email (or connect a mailbox), and the app generates a suggested reply drafts in different tones.

## Features

- AI-generated email summaries
- Smart reply suggestions (e.g., formal, friendly, brief)
- Tone/style customization for generated replies
- Clean, responsive UI for viewing and editing suggestions before sending
- REST API backend powered by Spring AI

## Tech Stack

**Backend**
- Java 17+
- Spring Boot
- Spring AI (LLM integration)
- Spring Web (REST API)
- Maven

**Frontend**
- React
- Axios
- Material UI

**AI**
- LLM provider integrated via Spring AI (e.g., OpenAI / Claude — update accordingly)

## Project Structure

```
smart-email-assistant/
├── backend/
│   ├── src/main/java/com/emailassistant/
│   │   ├── controller/     # REST controllers (e.g., EmailController)
│   │   ├── service/        # Business logic, AI prompt handling
│   │   ├── model/          # Entity/DTO classes
│   │   └── config/         # Spring AI configuration
│   ├── src/main/resources/
│   │   └── application.properties
│   └── pom.xml
├── frontend/
│   ├── src/
│   │   ├── components/     # EmailInput, SummaryCard, ReplySuggestions, etc.
│   │   ├── pages/
│   │   ├── services/       # API call functions
│   │   └── App.js
│   ├── package.json
└── README.md
```

## Prerequisites

- Java 17 or higher
- Node.js and npm
- Maven
- API key for your chosen AI provider (set as an environment variable)

## Setup Instructions

### 1. Clone the repository

```bash
git clone https://github.com/<your-username>/smart-email-assistant.git
cd smart-email-assistant
```

### 2. Backend Setup

```bash
cd backend
```

Configure your AI provider key in `src/main/resources/application.properties` (avoid committing real keys — use environment variables instead):

```properties
spring.ai.openai.api-key=${OPENAI_API_KEY}
server.port=8080
```

Run the backend:

```bash
mvn spring-boot:run
```

The backend will start on `http://localhost:8080`.

### 3. Frontend Setup

```bash
cd frontend
npm install
npm start
```

The frontend will start on `http://localhost:3000`.

## API Endpoints

| Method | Endpoint                       | Description                                |
|--------|--------------------------------|--------------------------------------------|
| POST   | /api/email/reply               | Generate a reply suggestion for an email   |
| POST   | /api/email/reply?tone=formal   | Generate a reply with a specific tone      |

*(Update this table to match your actual controller endpoints.)*

## Example Usage

1. Paste the email content into the input box on the frontend.
2. Click **Generate Reply** to get an AI-drafted response.
3. Edit the draft as needed and copy/send.

## Environment Variables

| Variable         | Description                        |
|-------------------|----------------------------------------|
| `OPENAI_API_KEY`  | API key for the AI provider used       |

## Future Improvements

- Direct Gmail/Outlook inbox integration (OAuth)
- Multi-language support
- Save reply templates
- Sentiment analysis on incoming emails
- User authentication and history of past summaries/replies

## License

This project is for educational/portfolio purposes.
