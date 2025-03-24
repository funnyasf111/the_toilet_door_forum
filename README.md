# Toilet Door Anonymous Forum - Documentation

## Overview
The Toilet Door is a modern, professional anonymous forum website where users can post messages on an endlessly scrolling virtual toilet door. The application features:

- Anonymous posting system with auto-assigned IDs (e.g., anon10234)
- Text-only posts (no images or videos)
- Endless scrolling functionality
- No user accounts required
- Modern, professional design with a toilet door theme

## Project Structure

```
toilet-door-forum/
├── migrations/              # Database migration files
│   └── 0001_initial.sql     # Initial database schema
├── public/                  # Public assets
├── src/
│   ├── app/                 # Next.js app directory
│   │   ├── api/             # API routes
│   │   │   └── posts/       # Post-related API endpoints
│   │   ├── globals.css      # Global styles
│   │   ├── layout.tsx       # Root layout
│   │   └── page.tsx         # Main page
│   ├── components/          # React components
│   │   ├── ui/              # UI components
│   │   ├── Post.tsx         # Post display component
│   │   ├── PostForm.tsx     # Post submission form
│   │   └── ToiletDoor.tsx   # Main toilet door component
│   └── lib/                 # Utility functions
│       ├── posts.ts         # Post-related functions
│       └── utils.ts         # General utilities
├── next.config.ts           # Next.js configuration
├── package.json             # Project dependencies
├── tailwind.config.ts       # Tailwind CSS configuration
└── wrangler.toml            # Cloudflare configuration
```

## Features

### Anonymous Posting System
- Users are automatically assigned anonymous IDs in the format "anon" followed by a 5-digit number
- No registration or login required
- Posts are stored in a database with content, timestamp, and anonymous ID

### Endless Scrolling
- Posts are loaded in batches as the user scrolls down
- Infinite scrolling implementation with optimized performance
- Loading indicators for better user experience

### Modern UI Design
- Custom toilet door theme with appropriate styling
- Responsive design that works on all device sizes
- Dark mode support for better readability

## Technical Implementation

### Frontend
- Built with Next.js and React
- Styled with Tailwind CSS
- Custom UI components for consistent design

### Backend
- API routes for post creation and retrieval
- Database integration with Cloudflare D1
- Pagination support for endless scrolling

### Database
- SQL database schema for storing posts
- Indexed for efficient retrieval by timestamp
- Migration files for easy setup

## Deployment Instructions

### Local Development
1. Install dependencies:
   ```
   npm install
   ```

2. Initialize the database:
   ```
   wrangler d1 execute DB --local --file=migrations/0001_initial.sql
   ```

3. Start the development server:
   ```
   npm run dev
   ```

### Production Deployment
1. Deploy to Cloudflare Pages:
   ```
   npm run deploy
   ```

2. Or deploy to any hosting service that supports Next.js applications

## Maintenance

### Adding New Features
1. Extend the database schema in migrations folder
2. Update the API routes in src/app/api/
3. Modify the frontend components as needed

### Troubleshooting
- Check browser console for JavaScript errors
- Verify API responses in Network tab
- Ensure database migrations are applied correctly

## Customization Options
- Edit globals.css to change the color scheme
- Modify the ToiletDoor component for layout changes
- Update the Post component to change post appearance
