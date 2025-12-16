# calendar
# Calendar View Component

A production-grade interactive calendar component built with React, TypeScript, and Tailwind CSS. Features month and week views, full event management, keyboard navigation, and responsive mobile support.

## Live Storybook

**[Add your deployed Storybook URL here after deployment]**

## Installation

```bash
npm install
npm run dev          # Start development server (http://localhost:5173)
npm run storybook    # Start Storybook (http://localhost:6006)
npm run build        # Build for production
npm run build-storybook  # Build Storybook for deployment
```

## Architecture

**Component Structure:**
- `CalendarView` - Main orchestrator with month/week view toggle, navigation controls, and month/year dropdowns
- `MonthView` - 42-cell grid with weekday labels, muted adjacent months, today highlight
- `WeekView` - 7-day time grid with hourly slots, event positioning by duration, overlap handling
- `CalendarCell` - Memoized cell component with event badges, keyboard focus management (React.memo)
- `EventModal` - Lazy-loaded modal (React.lazy/Suspense) with full form validation
- `MobileListView` - Responsive list view for mobile devices with expandable day sections

**State Management:**
- `useCalendar` - Date navigation and view state
- `useEventManager` - CRUD operations for events (fallback if no props passed)

**Utilities:**
- `date.utils.ts` - Date calculations (calendar grid, day comparisons, week boundaries)
- `event.utils.ts` - Event filtering and sorting logic

## Features

✅ **Month View** - 42-cell grid with prev/next/today navigation, month/year dropdowns  
✅ **Week View** - Time-based 7-day view with hourly slots, duration-based event height  
✅ **Event Management** - Create, edit, delete events via modal with validation  
✅ **Keyboard Navigation** - Arrow keys for grid navigation, Enter/Space to open cells  
✅ **Responsive Design** - Desktop grid, tablet optimized, mobile list view toggle  
✅ **Accessibility** - ARIA labels, keyboard focus indicators, semantic HTML  
✅ **Performance** - React.memo on cells, lazy-loaded modal, useMemo for grid calculations  
✅ **TypeScript Strict Mode** - Full type safety with no `any` types

## Storybook Stories

- **Default** - Current month with sample events
- **Empty State** - Calendar with no events
- **Week View** - Week view with time slots and events
- **With Many Events** - Month with 20+ events (performance test)
- **Interactive Demo** - Fully functional with Storybook controls
- **Mobile View** - Responsive mobile layout demonstration
- **Accessibility** - Keyboard navigation demonstration

## Technologies

- **React 18** + **TypeScript 5** (strict mode)
- **Vite 5** - Fast build tool and dev server
- **Tailwind CSS 3** - Utility-first styling with custom design tokens
- **Storybook 8** - Component documentation and testing

## Deployment

### Option 1: Vercel (Recommended for Vite apps)

```bash
# Install Vercel CLI
npm i -g vercel

# Deploy
vercel

# Build Storybook separately and deploy
npm run build-storybook
vercel --prod ./storybook-static
```

### Option 2: Chromatic (Recommended for Storybook)

```bash
# Install Chromatic
npm install --save-dev chromatic

# Deploy Storybook
npx chromatic --project-token=<your-project-token>
```

### Option 3: Netlify

```bash
# Install Netlify CLI
npm i -g netlify-cli

# Build and deploy
npm run build
netlify deploy --prod --dir=dist

# Deploy Storybook
npm run build-storybook
netlify deploy --prod --dir=storybook-static
```

## Contact

[your-email@example.com]
