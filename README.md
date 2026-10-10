# Winstone's General Knowledge Quiz

A customisable, timed quiz built with **HTML, CSS and vanilla JavaScript**, using questions from the **Open Trivia Database API**.

Choose a category, difficulty, number of questions and time limit, then test your knowledge with multiple-choice questions. The interface includes a countdown bar, answer feedback, a final score and a restart option.

## Features

- **Custom quiz length:** 5, 10, 15, 20, 25 or 30 questions.
- **Category selection:** general knowledge, books, films, music, computers, history, science and more.
- **Difficulty selection:** Easy, Medium, Hard or any difficulty.
- **Question timers:** 10, 15, 20, 25, 30 or 60 seconds per question.
- **Questions fetched from an API** when a quiz begins.
- **Four answer choices**, with their order shuffled for each question.
- **Selection feedback** using a coloured circular indicator and check icon.
- **Manual submission or automatic checking** when the countdown expires.
- **Correct and incorrect answer feedback** before moving to the next question.
- **Final score** displayed against the total number of questions.
- **Restart Quiz** to reload the app and return to the settings screen.
- **Responsive styling**, including a full-width layout on smaller screens.

## How to Play

1. Choose the number of questions, category, difficulty and time per question.
2. Select **Start Here** to load the quiz.
3. Select an answer and press **Submit**, or let the timer expire.
4. Review the answer feedback and select **Next**.
5. After the final question, view your score.
6. Select **Restart Quiz** to begin again.

Each correct answer earns one point. Wrong answers and unanswered questions earn zero points. Scores are held in memory during the quiz; restarting or reloading does not preserve them.

## Technologies

| Technology | Purpose |
| --- | --- |
| HTML5 | Settings, question area and results screen |
| CSS3 | Layout, gradient backgrounds, progress bar and answer states |
| JavaScript | API requests, answer rendering, timer, scoring and navigation |
| Fetch API | Retrieve trivia questions as JSON |
| Open Trivia Database | Question and answer source |
| Font Awesome | Check icons |
| Google Fonts | Oswald typography |

The current quiz has no backend, framework, package installation or build step. It needs an internet connection to fetch questions and load external fonts and icons.

## Project Files

| File | Contents |
| --- | --- |
| `index.html` | App structure and quiz settings |
| `style.css` | Styling, answer feedback and responsive layout |
| `script.js` | Quiz behaviour and API integration |
| `favicon.ico` | Browser tab icon |
| `README.md` | Project documentation |

## Run Locally

1. Download or clone the project.
2. Keep all project files in the same folder.
3. If using timestamped exports, rename them to `index.html`, `style.css`, `script.js` and `favicon.ico` to match the HTML references.
4. Serve `index.html` with VS Code's Live Server extension or another local static web server.
5. Open the local address in a browser and start a quiz.

The front end can also be hosted as a static site, for example using GitHub Pages.

## API Integration

Questions come from [Open Trivia Database](https://opentdb.com/), a free JSON API that does not require an API key.

Example request for five easy, multiple-choice general-knowledge questions:

```text
https://opentdb.com/api.php?amount=5&category=9&difficulty=easy&type=multiple
```

The app builds its request from the selected settings. Each returned question includes its text, a correct answer and incorrect answers. JavaScript combines the choices and displays them in the quiz interface.

Open Trivia DB uses HTML-encoded text by default. Answer checking should compare the displayed answer with a decoded correct-answer string, rather than compare a DOM element with a string.

The API permits one request per IP address every five seconds and returns response codes for cases such as insufficient questions or rate limits. See the [API documentation](https://opentdb.com/api_config.php).

## Learning Focus

- Retrieving and processing JSON using `fetch()`.
- Rendering questions and answer choices dynamically.
- Using CSS classes to represent selection, correctness and screen visibility.
- Managing a countdown with `setInterval()` and `clearInterval()`.
- Tracking the current question and calculating the final score.
- Handling encoded text when comparing API data with rendered content.
- Building a complete flow from settings to results.

## Planned Additions

The current version uses trivia data; AI explanations are a future feature.

- An **Explain this answer** action after checking a question.
- A readable explanation area beside a supporting image or illustration.
- An input for follow-up questions, with a textarea if longer user messages are needed.
- A small backend or serverless endpoint for AI requests, keeping any private API key out of browser code.
- Loading and error states for unavailable questions, failed requests and API limits.
- Keyboard-operable answer controls and clearer focus feedback.
- A single-submission guard to ensure a question can only award one point.
- A timer that checks the answer on the tick reaching zero, without an extra second's delay.

## Question Data Attribution

Trivia questions and answers are supplied by **Open Trivia Database** under the [Creative Commons Attribution-ShareAlike 4.0 International licence](https://creativecommons.org/licenses/by-sa/4.0/). This attribution applies to the question data; it does not declare a licence for this project's source code.

## Author

**Winstone Anderson** — UI-focused front-end developer in London.

- [GitHub](https://github.com/winstone01)
- [Portfolio](https://winstoneanderson.com)

