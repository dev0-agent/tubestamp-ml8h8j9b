# Task List

This file shows the current progress of all tasks in this project.
It is automatically updated by dev0 as tasks are completed.

---

## Phase 1

- [ ] ⏳ **Project Configuration & Environment Setup**
  Create a `src/utils/env.ts` file to validate environment variables (DATABASE_URL). Configure Drizzle ORM connection settings in `drizzle.config.ts` and `src/db/index.ts`. Ensure the app runs with the base configuration.

- [ ] ⏳ **Database Schema Definition**
  Define the Drizzle schema in `src/db/schema.ts`. Create a `bookmarks` table with columns: `id` (uuid/serial), `youtubeId` (text), `title` (text), `notes` (text), `timestamp` (integer, in seconds), `tags` (text/json for array of strings), and `createdAt` (timestamp). Run migration generation.

- [ ] ⏳ **YouTube URL Parsing Utility**
  Create a utility `src/utils/youtube.ts`. It should export functions to: 1) Extract the Video ID from various YouTube URL formats (standard, short, embed). 2) Extract the timestamp query param (t=1m20s) and convert it to total seconds. 3) Format seconds back to HH:MM:SS for display. Write unit tests if possible.

## Phase 2

- [ ] ⏳ **Bookmark Server Functions (CRUD)**
  Implement TanStack Start server functions for database operations: `getBookmarks` (fetch all, ordered by date), `createBookmark` (insert new), and `deleteBookmark` (remove by ID). Ensure proper type safety with Zod validators.

- [ ] ⏳ **Add Bookmark Form Component**
  Create a UI component `AddBookmarkForm`. It should accept a URL input. On blur/change, use the utility from Task-3 to pre-fill the Video ID and Timestamp fields. Include fields for Title, Notes, and a comma-separated Tags input. Wire up to the `createBookmark` server function.

- [ ] ⏳ **Bookmark Card & List View**
  Create a `BookmarkList` component that fetches data using the `getBookmarks` server function. Map over results to render a `BookmarkCard` component. The card should display the thumbnail (https://img.youtube.com/vi/[ID]/mqdefault.jpg), title, timestamp, tags, and notes.

## Phase 3

- [ ] ⏳ **Embedded Video Player Modal**
  Create a `VideoPlayer` component (using a Dialog/Modal). When a user clicks 'Play' on a Bookmark Card, open this modal. The iframe src should be constructed as `https://www.youtube.com/embed/[ID]?start=[SECONDS]&autoplay=1`. Ensure the modal closes cleanly.

- [ ] ⏳ **Tag Filtering Logic**
  Update the `getBookmarks` server function to accept an optional `search` or `tag` parameter. Update the main UI to include a search bar or a list of clickable tags. Clicking a tag filters the list to show only matching bookmarks.

- [ ] ⏳ **Edit Bookmark Functionality**
  Add an `updateBookmark` server function. Add an 'Edit' button to the Bookmark Card that re-opens the form (or a modal) pre-filled with existing data to allow modifying notes, tags, or timestamps.

## Phase 4

- [ ] ⏳ **UI Polish & Empty States**
  Add a skeleton loader while bookmarks are fetching. Create a friendly 'No bookmarks found' empty state component. Improve the styling of the timestamp badges and tag pills using Tailwind.

---

_Last updated by dev0 automation_
