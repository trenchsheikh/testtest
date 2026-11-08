# still.

**Make space to focus.**

A beautifully simple, distraction-free workspace for doing your best work. Still combines a focus timer, a lightweight to-do list, and gentle progress tracking in one calm, responsive interface.

**[Open the live app](https://testtest-darkbet.vercel.app)** · [Source code](https://github.com/trenchsheikh/testtest)

---

## Overview

Still is designed around a simple idea: doing one thing well is better than trying to do everything at once. Start a focused session, write down what matters, and build momentum without accounts, complicated setup, or distracting features.

| Feature | Description |
| --- | --- |
| **Focus timer** | Start, pause, resume, or reset a visual countdown with an animated progress ring. |
| **Flexible sessions** | Choose a 25-minute or 50-minute work session, or take a 5-minute break. |
| **Today's intentions** | Add, complete, and delete tasks in a simple checklist. |
| **Daily activity** | See how many work sessions and focus minutes you've completed today. |
| **Three themes** | Switch between lilac, mint, and peach accent palettes. |
| **Local-first preferences** | Tasks, theme, and daily statistics are stored in your browser. |
| **Responsive layout** | Designed to work comfortably on mobile, tablet, and desktop. |
| **Accessible controls** | Semantic buttons, accessible labels, visible focus states, and reduced-motion support. |

## Live demo

**Production:** https://testtest-darkbet.vercel.app

The application is deployed on [Vercel](https://vercel.com/) and linked to this repository. Changes pushed to the production branch (`main`) trigger new deployments through Vercel's Git integration.

## Getting started

### Requirements

All you need is a modern web browser. The project uses **no JavaScript framework, package manager, or build step**.

### Run locally

Clone the repository:

```bash
git clone https://github.com/trenchsheikh/testtest.git
cd testtest
```

Open `index.html` directly in your browser, or start a local HTTP server:

```bash
python3 -m http.server 8000
```

Then visit **http://localhost:8000**.

> On Windows, `py -m http.server 8000` may be available instead of `python3`.

## How to use

1. **Choose a duration.** Pick 25 or 50 minutes to focus, or select the 5-minute break preset.
2. **Start a session.** Use **Start focusing** to begin the countdown. You can pause, resume, and reset at any time.
3. **Capture your intentions.** Enter a task in the input field and press **+** or Enter.
4. **Track your progress.** Check tasks off as you finish them. Completed work sessions update your daily statistics automatically.
5. **Set the mood.** Use **Change the mood** to cycle through the colour palettes.

### Keyboard shortcuts

| Shortcut | Action |
| --- | --- |
| `Space` | Start or pause the timer when focus is not inside an input or button. |
| `Escape` | Pause a running timer when focus is not inside an input or button. |
| `Enter` (inside the task input) | Add the typed task. |

## Tech stack

- **HTML5** for the document structure and semantic controls.
- **CSS3** for design tokens, layout, gradients, transitions, and responsive styles.
- **Vanilla JavaScript** for timer logic, task interactions, preferences, and statistics.
- **Web Storage API** (`localStorage`) for browser-side persistence.
- **Google Fonts** for the DM Sans and Manrope typefaces.
- **Vercel** for deployment and hosting.

There are **no runtime JavaScript dependencies**.

## Project structure

```text
testtest/
├── index.html    # Markup, styles, and application logic
└── README.md     # Project documentation
```

The app is intentionally implemented in a single HTML file to make it easy to explore, modify, and deploy.

## Data and privacy

Still has no account system, database, analytics SDK, or application backend.

- Tasks and selected theme are saved using the browser's `localStorage`.
- Daily completed-session statistics are also saved locally and reset when a new local calendar day begins.
- Focus session progress is **not** persisted across a page refresh.
- The 5-minute break is not included in focus-session statistics.
- Data is specific to the browser and device. Clearing site storage removes saved preferences and tasks.
- Fonts are fetched from Google Fonts, so the page is not entirely network-independent.

### Local storage keys

| Key | Content |
| --- | --- |
| `still-tasks-v1` | Checklist items and completion state |
| `still-theme-v1` | Selected colour theme |
| `still-stats-v1` | Date, completed sessions, and focused minutes |

## Customisation

The colour system is defined using CSS variables near the start of `index.html`:

```css
:root {
  --page: #f7f6f2;
  --paper: #ffffff;
  --ink: #22221f;
  --accent: #775ce8;
  --accent-light: #f0ecff;
  --accent-soft: #cbbdfd;
  --accent-dark: #5841ba;
}
```

Update these values to change the core visual identity. Alternate themes live in the `[data-theme="mint"]` and `[data-theme="peach"]` rules. Timer presets are defined by the buttons' `data-minutes` attributes.

## Deployment

Vercel serves the project as a static site. No build command, environment variables, or output directory configuration is required.

To create a separate deployment:

1. Import this GitHub repository into a Vercel project.
2. Select **Other** (or no framework preset) if prompted.
3. Leave build and output settings at their defaults.
4. Deploy.

For this repository, the existing production deployment is already connected to `main`.

## Contributing

Suggestions and improvements are welcome. For a change:

1. Fork the repository and create a descriptive branch.
2. Make your changes, keeping the experience lightweight and accessible.
3. Test the timer, tasks, and layouts at different screen sizes.
4. Open a pull request explaining the change.

## Roadmap ideas

The current application is intentionally minimal. Potential future additions include optional sound notifications, configurable durations, and an export/import option for locally stored tasks.

---

<p align="center"><strong>still.</strong> — A little space for big things.</p>
