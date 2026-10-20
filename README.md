# College Compass

A college discovery web app for students: browse and filter colleges, read reviews, see rating charts, and get AI-generated college recommendations from your interests, preferred location and budget. Built in Firebase Studio.

> Formerly named `collegecompass`.

## Features

- **College directory** filterable by state, city and course.
- **College pages** with details and student reviews.
- **AI recommendations:** a Genkit flow (Google Gemini) takes academic interests, preferred location and financial constraints and returns suggested colleges.
- **Visualizations:** colleges by state, rating distribution, and average rating by course.
- **Resources** page with links for applications and financial aid.

## Tech stack

Next.js 15 (App Router), TypeScript, Tailwind CSS with shadcn/ui, Genkit with Google AI (Gemini 2.0 Flash), Recharts, Firebase App Hosting config.

## Status

Prototype. College and review data are **mock data** in `src/lib/data.ts` (10 sample colleges and reviews), and the AI recommender answers from the model's general knowledge, not from that dataset. Treat the output as a starting point, not as verified advice.

## Getting started

Requirements: Node.js 18+ and a Google AI (Gemini) API key.

```bash
git clone https://github.com/crazysandy1/college-compass.git
cd college-compass
npm install
echo "GEMINI_API_KEY=your_key_here" > .env.local
npm run dev            # http://localhost:9002
npm run genkit:dev     # optional: Genkit developer UI for the flow
```

## Project layout

```
src/app/            Pages: home, colleges, college detail, recommendations, visualizations, about
src/ai/             Genkit setup and the college-recommendation flow
src/components/     Charts, college cards and filters, layout, UI primitives
src/lib/data.ts     Mock colleges and reviews, filter helpers
docs/blueprint.md   Original product brief and style guidelines
```

## Roadmap

- Replace mock data with a real database (Firestore or PostgreSQL) and real submitted reviews.
- Ground the recommender in the college dataset (retrieval) instead of free generation.
- Review moderation and user accounts.

## License

MIT
