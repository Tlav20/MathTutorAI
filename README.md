# MathTutor - AI Math Tutor for Middle School Students

This project is an interactive web application that serves as an AI-powered math tutor for middle school students. It features a step-by-step math problem solver, calculator, and note-taking functionality.

## Project Structure

```
mathtutor/
├── index.html             # Main dashboard page
├── login.html             # Login and registration page
├── css/
│   ├── style.css          # Main dashboard styles
│   ├── login.css          # Login page styles
│   └── math_solver.css    # Math solver component styles
├── js/
│   ├── main.js            # Main initialization script
│   ├── login.js           # Login page functionality
│   ├── math_api.js        # API integration with math solver backend
│   ├── math_solver.js     # Math solver UI component
│   ├── calculator.js      # Calculator functionality
│   └── notes.js           # Notes functionality
└── python_backend/        # Python backend for math solving
    ├── requirements.txt   # Python dependencies
    └── app.py             # Flask app with math solver
```

## Setup Instructions

### 1. Frontend Setup

1. Clone or download this repository
2. Place all files in your web server directory or local development environment
3. Open `login.html` in a browser to start (or serve using a local development server)

### 2. Python Backend Setup

The math solver requires a Python backend to function. Follow these steps to set it up:

1. Ensure you have Python 3.8+ installed
2. Create a virtual environment:
   ```
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```
3. Install the required packages:
   ```
   pip install flask flask-cors sympy numpy
   ```
4. Create a new file `python_backend/app.py` with the Python backend code provided
5. Start the Flask server:
   ```
   python app.py
   ```
   
The server will start on http://localhost:5000

## Integration Details

### Math Solver Integration

The math solver works by sending math problems to the Python backend, which uses SymPy and NumPy to solve them and generate step-by-step explanations. The results are then displayed in the UI.

Key files for the math solver:
- `math_api.js`: Handles communication with the backend
- `math_solver.js`: Creates and manages the UI component
- `math_solver.css`: Styles the math solver component
- `python_backend/app.py`: Contains the solver logic

To integrate the math solver into the dashboard:
1. Include the necessary JavaScript and CSS files
2. Add a container with id `math-solver-section` in your HTML
3. Make sure the backend server is running

### File Structure Requirements

Ensure these paths match your project structure:
- CSS files should be in a `css/` directory
- JavaScript files should be in a `js/` directory
- The Python backend code should be in a `python_backend/` directory

## Features

### 1. Math Problem Solver
- Solves a wide range of middle school math problems
- Provides step-by-step explanations
- Supports multiple math topics (algebra, arithmetic, fractions, percentages, geometry, statistics)

### 2. Calculator
- Basic calculator functionality
- Supports keyboard input
- Shows calculation history

### 3. Notes
- Create, edit, and save notes
- Auto-save functionality
- Sample notes for common math formulas

### 4. User Authentication
- Login and registration system
- User data stored in localStorage (for demo purposes)
- Password strength meter

## Customization

### Changing the Backend URL

If you deploy the Python backend to a different server or port, update the API URL in `math_api.js`:

```javascript
constructor(baseURL = 'http://your-server-url:port')
```

### Adding More Math Topics

To add support for more math topics:
1. Extend the Python solver in `app.py` with new topic handling
2. Update the topic selector in `math_solver.js` to include the new topics

## Deployment Considerations

For a production environment:
1. Replace localStorage with a proper database
2. Implement secure user authentication
3. Set up CORS properly on the Python backend
4. Consider dockerizing the Python backend for easier deployment
5. Add proper error handling and logging

## Technologies Used

- Frontend: HTML, CSS, JavaScript
- Backend: Python, Flask
- Math Libraries: SymPy, NumPy
- Storage: localStorage (demo only)

## Further Development

Potential enhancements:
- Add more advanced math topics
- Implement a chat interface for conversational problem-solving
- Create a progress tracking system
- Add interactive exercises and quizzes
- Implement machine learning for problem type detection