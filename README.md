# 360 Solution Provider

A multi-page service portal for engineering students to browse, query, and review professional technical and educational solutions across Computer Science, Mechanical Engineering, and Academia.

## Features

- **SPA shell with iframe navigation** — persistent sidebar and topbar stay in place while page content loads in a managed iframe without full-page reloads
- **Collapsible sidebar** — slide-in navigation with active-link highlighting and an overlay backdrop for mobile
- **Home page** — hero section, animated student-count stat card (counts to 500+), service overview cards with technology tags, about section, and customer testimonials
- **Categories page** — three service categories (Computer Services, Mechanical Services, Educational Services), each exposing individual service pills that open a query modal
- **Query submission** — modal form collects email and query description, validates inputs client-side, and posts the request asynchronously to a Google Apps Script backend (Google Sheets integration)
- **Reviews page** — star-rating widget (1–5), name and comment fields, and live submission to the same Google Apps Script endpoint; existing reviews rendered from the sheet
- **About Us page** — team and mission information
- **Help page** — FAQ / support content
- **Toast notifications** — non-blocking success/error feedback after form submissions
- **Social links** — Twitter/X, LinkedIn, Instagram in sidebar footer

## Tech Stack

- HTML5, CSS3 (custom properties, CSS Grid, Flexbox)
- Bootstrap 5.3
- Bootstrap Icons 1.11
- Google Fonts (Inter)
- Vanilla JavaScript (ES6+)
- Google Apps Script (serverless backend — query and review persistence to Google Sheets)

## Getting Started

### Prerequisites

- A modern web browser (Chrome, Firefox, Edge)
- No build tools required

### Installation / Setup

1. Clone or download the repository.

2. Open `index.html` in a browser. All pages load via the iframe shell — no server required for browsing.

3. To enable query and review submissions, deploy a Google Apps Script Web App to your own Google account and replace the `SHEET_URL` constant in `pages/category.html` and `pages/review.html`:
   ```javascript
   const SHEET_URL = 'https://script.google.com/macros/s/YOUR_DEPLOYMENT_ID/exec';
   ```

## Project Structure

```
360-solution-provider-project/
├── index.html              # App shell — topbar, sidebar, and iframe container
├── favicon.svg             # Brand logo / favicon
├── pages/
│   ├── home.html           # Landing page with hero, stats, services, testimonials
│   ├── category.html       # Service category cards with query submission modal
│   ├── review.html         # Star-rating review form and review feed
│   ├── about-us.html       # Team and mission page
│   └── help.html           # FAQ / help page
└── assest/
    ├── css/                # Per-page stylesheets (index.css, home.css, category.css, etc.)
    ├── js/                 # App-shell navigation logic (index.js)
    └── images/             # Category icons and other imagery
```

## License

MIT
