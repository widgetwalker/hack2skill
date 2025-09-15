GURU your AI Mentor

Overview
GURU your AI Mentor is a React + Vite single-page app that helps users generate a personalized career roadmap using an LLM (Gemini). The UI has been refactored for stable keyboard input, clear spacing, and a modern look aligned to a custom color palette.

Key Features
- Clean component architecture: inputs and display components extracted from `App` for stability and maintainability
- Guided form with four fields: Current Role, Key Skills, Interests, Career Goals
- Conversational panel and structured career plan display
- Keyboard focus stability (fix for prior focus loss when everything lived inside `App`)
- Modern styling with large spacing, icon-aligned labels, and gradients

Tech Stack
- React 18
- Vite 4
- lucide-react (icons)
- Plain CSS with CSS variables

Getting Started
1) Install dependencies
   npm install

2) Run the dev server
   npm run dev

3) Build for production
   npm run build

4) Preview the build
   npm run preview

Environment Variables
The app calls Gemini to generate the career plan.

- REACT_APP_GEMINI_API_KEY: Your Gemini API key

Create a `.env` file in the project root and add:
  REACT_APP_GEMINI_API_KEY=your_api_key_here

Note: The current code reads this variable directly from `process.env`. If you later migrate to Vite’s `import.meta.env`, you’ll want to rename this to a `VITE_` prefixed variable and reference it accordingly.

Project Structure (key files)
- index.html               → App mount and Vite entry
- public/index.html        → Static HTML variant
- src/index.jsx            → React bootstrap
- src/App.jsx              → App state, flow, and API call
- src/index.css            → Global styles and design tokens
- src/components/
  - WelcomeScreen.jsx      → Title/hero
  - UserInputForm.jsx      → Form with four inputs
  - InputField.jsx         → Label + icon + input control
  - ChatMessage.jsx        → Message bubble
  - CareerPlanDisplay.jsx  → Plan container
  - CareerStep.jsx         → Individual plan step

Design System
Color palette (from provided image):
- Blue (accent): #72BBFF
- Ink (text): #050F2A
- Surface (background): #F2FDFF
- Lavender (primary): #BBA0FF

These are mapped to CSS variables in `src/index.css` and applied consistently:
- Inputs: soft surface, blue focus ring
- Primary actions and user bubbles: blue → lavender gradient
- Titles and body text: deep ink

Typography
- Main title uses a high-contrast display face (Playfair Display) as a stand‑in for the requested “Talkine – Bold Title Font”.
- Subheadings (labels) are bold and italic for emphasis.

Recent UI Improvements
- Increased vertical spacing between labels and inputs
- Icons aligned horizontally next to subheadings
- Larger breathing room for form sections and primary button
- Subtle gradient background wash using palette colors

API Flow (high level)
1) User enters profile data and submits the form
2) App builds a structured prompt and calls Gemini
3) The API is instructed to return a strict JSON structure
4) The JSON plan is parsed and rendered in the right panel

Troubleshooting
- Vite not recognized: run `npm install` in the project root
- JSX parse error: ensure entry file is `src/index.jsx` and referenced in `index.html`
- API key error: ensure `REACT_APP_GEMINI_API_KEY` is set in `.env`

License
This project is provided as-is for personal and educational use.


