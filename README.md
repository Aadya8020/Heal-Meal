# 🥗 Heal Meal – Personalized Nutrition Through Artificial Intelligence

### Because recovery doesn't end at hospital discharge!

## 🌿 About Heal Meal

Recovering from an illness doesn't end when a patient leaves the hospital. In fact, the recovery journey continues long after discharge, and maintaining proper nutrition plays an important role in it.

However, once patients return home, they may not always have access to doctors, nutritionists, or someone who can guide them about what they should eat and which nutrients their body needs.

That's where **Heal Meal** comes in!

Heal Meal is a voice-enabled, AI-powered health information and nutrition assistant designed to support recovering patients and their caregivers. It helps users get personalized meal ideas based on their health concerns and nutritional needs, along with nutritional estimates explaining what each suggested meal contributes to their diet.

Designed with Indian users in mind, Heal Meal focuses on practical, affordable food suggestions featuring familiar Indian meals and seasonal produce.

But that's not all! It also includes medication reminders, voice interaction, and several health and fitness calculators, bringing multiple aspects of everyday health management together in one place.

Our goal is simple: to make the recovery journey a little easier, more informed, and more manageable.

---

## ✨ Features

### 🎙️ 1. Voice-Based Interaction
Users can interact with Heal Meal through voice input wherever browser speech recognition is supported. Typed questions are also available as an alternative.

### 🤖 2. AI-Powered Health Chat
Heal Meal uses the Groq API to provide AI-powered responses to general health-related questions and help users understand different nutritional and wellness topics.

### 🍱 3. Personalized Meal Ideas
Users can receive meal suggestions based on their health concerns and nutritional goals.

The recommendations focus on:
- Familiar and affordable Indian foods.
- Seasonal fruits and vegetables.
- Practical meal choices.
- Approximate nutritional information.

### 🥑 4. Nutritional Insights
Heal Meal doesn't just suggest what to eat; it also provides nutritional estimates to help users understand what different food items contribute to their diet.

### ⏰ 5. Medication Reminders
Users can add and manage medication reminders to help them keep track of their prescribed medication schedules.

### 📊 6. Health & Fitness Calculators

Heal Meal includes ten calculators to help users understand their health and nutritional requirements.

| Calculator | Purpose |
|---|---|
| BMI Calculator | Calculates Body Mass Index. |
| Calorie Calculator | Estimates daily calorie requirements. |
| TDEE Calculator | Calculates Total Daily Energy Expenditure. |
| Calorie Deficit Calculator | Estimates calorie deficit requirements. |
| Body Fat Calculator | Estimates body fat percentage. |
| Macro Calculator | Estimates daily macronutrient requirements. |
| Protein Calculator | Estimates daily protein requirements. |
| Water Intake Calculator | Estimates daily water intake. |
| Weight Loss Calculator | Estimates weight loss requirements. |
| BMR Calculator | Estimates Basal Metabolic Rate. |

### 🔊 7. Text-to-Speech Support
Heal Meal supports optional ElevenLabs text-to-speech for voice output. If ElevenLabs credentials are unavailable or the service cannot be accessed, the application can fall back to the browser's built-in voice.

### 🔐 8. Privacy & Security
- A Clear Saved Data option allows users to remove locally stored chat history and medication reminders after confirmation.
- API request limits help prevent excessive requests.
- Helmet provides HTTP security headers.
- API credentials are managed on the backend rather than exposed in frontend code.

### 📚 9. Health References
The application provides relevant health-reference links selected by the server, including resources from:
- ICMR – National Institute of Nutrition (NIN)
- FSSAI – Food Safety and Standards Authority of India
- NCDC – National Centre for Disease Control

---

## 🛠️ Technologies Used

| Technology | Purpose |
|---|---|
| HTML5 | Structuring the web application |
| CSS3 | Styling and responsive design |
| JavaScript | Frontend functionality and interactions |
| Node.js | Backend runtime environment |
| Express.js | Backend server and API handling |
| Groq API | AI-powered health chat and meal ideas |
| ElevenLabs API | Optional text-to-speech functionality |
| Browser Speech API | Voice input and fallback speech output |
| dotenv | Managing environment variables |
| Upstash Redis | Shared rate-limiting support |
| Upstash Ratelimit | Managing API request limits |
| Express Rate Limit | Additional request-rate control |
| Helmet | HTTP security headers |
| Playwright | Automated browser testing |

---

## 📂 Project Structure

```text
Heal-Meal/
│
├── .env.example
├── .gitignore
├── README.md
│
├── favicon.png
├── healmeal-heart.png
├── healmeal-heart.svg
│
├── index.html
├── styles.css
├── script.js
├── health-tools.js
├── voice.js
│
├── server.js
├── rate-limit.js
│
├── package.json
├── package-lock.json
├── playwright.config.js
├── vercel.json
│
├── privacy.html
└── terms.html
```

---

## 🚀 Getting Started

Want to try Heal Meal on your own system? Follow these steps!

### Prerequisites

Make sure you have the following installed:

- Node.js (version 20 or newer)
- npm
- A Groq API key
- An ElevenLabs API key and Voice ID (optional)
- An Upstash Redis database (optional for local use, recommended for deployment)

### Step 1: Clone the Repository

```bash
git clone YOUR_GITHUB_REPOSITORY_LINK
```

### Step 2: Navigate to the Project Folder

```bash
cd healmeal
```

### Step 3: Install Dependencies

```bash
npm install
```

### Step 4: Set Up Environment Variables

Create a `.env` file using the provided example.

**Windows PowerShell:**
```powershell
Copy-Item .env.example .env
```

**macOS/Linux:**
```bash
cp .env.example .env
```

Open the `.env` file and add your API keys and other required configuration values.

### Step 5: Start the Application

```bash
npm start
```

Open the local address displayed in your terminal. With the default configuration, it is:

http://localhost:3000

Keep the terminal running while using the application. Press `Ctrl + C` to stop the server.

---

## ⚙️ Environment Variables

The following environment variables are used to configure Heal Meal.

| Variable | Required? | Purpose |
|---|---|---|
| `GROQ_API_KEY` | For AI features | Private API key for Groq-powered chat and meal suggestions. |
| `GROQ_MODEL` | Optional | Specifies the Groq model to use. |
| `ELEVENLABS_API_KEY` | For ElevenLabs voice | API key for text-to-speech functionality. |
| `ELEVENLABS_VOICE_ID` | For ElevenLabs voice | Specifies the voice used for speech generation. |
| `ELEVENLABS_MODEL` | Optional | Specifies the ElevenLabs speech model. |
| `PORT` | Optional | Sets the local server port. Defaults to 3000. |
| `UPSTASH_REDIS_REST_URL` | Optional | Upstash Redis REST URL for shared rate limiting. |
| `UPSTASH_REDIS_REST_TOKEN` | Optional | Private Upstash Redis authentication token. |

**Important:** Never upload your actual `.env` file or expose private API keys on GitHub. The `.gitignore` file excludes `.env` from version control.

If ElevenLabs credentials are unavailable, the application can use the browser's built-in voice instead.

If Upstash credentials are not configured, the application uses an in-memory rate limiter, which is suitable for local development but does not share limits across multiple Vercel instances.

---

## 🔗 API Endpoints

Heal Meal uses the following backend API endpoints:

| Endpoint | Method | Purpose |
|---|---|---|
| `/api/health` | GET | Checks whether the backend is responding. |
| `/api/chat` | POST | Handles AI-powered health-related questions. |
| `/api/meal-plan` | POST | Generates meal ideas with approximate nutritional estimates and references. |
| `/api/voice` | POST | Generates speech audio when ElevenLabs is configured. |

---

## 🧪 Testing

Heal Meal uses Node.js testing and Playwright for automated testing.

To run the available tests:

```bash
npm test
```

This runs the backend tests as well as browser-based tests.

To run only the browser tests:

```bash
npm run test:browser
```

Playwright tests cover application functionality, including calculators, medication reminders, data clearing, chat interactions, voice-related scenarios, responsive layouts, keyboard accessibility, and accessibility checks.

The automated tests do not make actual requests to Groq or ElevenLabs.

To install Chromium for browser testing:

```bash
npx playwright install chromium
```

---

## 🌐 Deployment

Heal Meal supports deployment through Vercel.

The backend can run through Vercel's serverless functions, so users can access the deployed application without starting a local server.

For deployment:
1. Import the GitHub repository into Vercel.
2. Configure the required environment variables in the Vercel project settings.
3. Deploy the application.
4. Redeploy whenever you make changes to the environment variables.

For shared rate limiting across Vercel instances, configure an Upstash Redis database and provide its REST URL and token.

---

## 🌱 Future Scope

There is still plenty of room to make Heal Meal even better! Some improvements we would love to explore include:

- Support for more Indian regional languages.
- Integration with wearable devices for better health monitoring.
- More advanced AI-driven meal personalization.
- Recovery progress tracking.
- Integration with healthcare professionals for more reliable dietary guidance.
- Integration with hospital discharge summaries and patient health records, with proper consent and security measures.

---

## ⚠️ Health & Nutrition Disclaimer

Heal Meal is designed to provide general health information and supportive nutrition guidance. It is not a medical device and does not provide medical diagnoses, treatment, or prescriptions.

Meal suggestions and calculator outputs are approximate and should not replace professional medical advice or individualized dietary recommendations.

Patients with allergies, kidney disease, pregnancy, medication interactions, or multiple health conditions should consult a qualified healthcare professional or registered dietitian before making dietary changes.

Heal Meal should not be used for medical emergencies.

---

## 📖 References

Heal Meal uses health-reference links from trusted sources, including:

- [ICMR – National Institute of Nutrition: Dietary Guidelines for Indians (2024)](https://nin.res.in/dietaryguidelines/pdfjs/locale/DGI_2024.pdf)
- [FSSAI – Eat Right India](https://fssai.gov.in/eat-right-india)
- [National Centre for Disease Control (NCDC)](https://ncdc.mohfw.gov.in/)
- [MedlinePlus](https://medlineplus.gov/)

---

## 👩‍💻 Project Contributors

Heal Meal was developed as a collaborative project by:

- Aadya
- Aarchit Saxena
- Ashutosh Badoni

---

## ❤️ Our Vision

We believe that recovery deserves attention even after a patient leaves the hospital.

With Heal Meal, we hope to make nutritional guidance more accessible, help caregivers support their loved ones, and make the journey towards recovery a little easier.

### 🥗 Heal Meal – Because recovery doesn't end at hospital discharge!
