# Feedback Form Frontend (Achelous)

## Project Setup

### Clone the Repository

To clone the repository, use the following command:

```bash
git clone <repository-url>
cd feedback-form-frontend
```

### Install Dependencies
To install all the necessary dependencies, run the following command:

```bash
npm install
```

### Run the Development Server
To start the development server, use the following command:

```bash
npm run serve
```
This will run the application in development mode. Open your browser and navigate to http://localhost:8080 to see the application.

## Project Structure
The project structure is as follows:

```css
feedback-form-frontend/
│
├── public/
│   ├── index.html
│   └── ...
├── src/
│   ├── assets/
│   ├── components/
│   │   └── FeedbackForm.vue
│   ├── App.vue
│   ├── main.js
│   └── ...
├── .gitignore
├── package.json
├── README.md
└── ...
```

## FeedbackForm Component
The `FeedbackForm` component is located in the `src/components/` directory and is responsible for collecting user feedback via a star rating system and submitting it to the backend.

## Axios
Axios is used for making HTTP requests. It is already included in the dependencies and can be used throughout the project for API calls.

## Scripts
In the `package.json` file, you will find various scripts that can be run using `npm run <script>`:

- `serve`: Compiles and hot-reloads for development.
- `build`: Compiles and minifies for production.
- `lint`: Lints and fixes files.

## Customize Configuration
For more details on customizing the configuration, refer to the Vue CLI Configuration Reference.

## License
This project is licensed under the MIT License - see the LICENSE file for details.

