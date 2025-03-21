# FluidCalendar Implementation Plan
# Random Tasks
- [ ] add a calculator comparing motion to FC
- [ ] move homepage to this repo.
- [ ] 
# CalDAV Implementation
## Phase 1: Setup and Basic Structure ✅
- [x] Add required libraries (`tsdav`, `ical.js`)
- [x] Update database schema with CalDAV-specific fields
- [x] Create basic CalDAV client class structure
- [x] Update validation logic for CalDAV events
- [x] Fix linter errors in CalDAV implementation

## Phase 2: Authentication and Calendar Discovery ✅
- [x] Create UI for adding CalDAV accounts
- [x] Implement authentication flow for CalDAV
- [x] Discover available calendars from CalDAV server
- [x] Update calendar selection UI to support CalDAV
- [x] Fix form component errors and align with project patterns
- [x] Fix logger usage to match project conventions

## Phase 3: Calendar Synchronization (Pending)
- [x] Implement calendar event fetching from CalDAV server
- [x] Create/update/delete events on CalDAV server
- [x] Handle recurring events
- [ ] Implement two-way sync with change tracking
- [ ] all day events are off by a day

## Phase 4: Advanced Features (Pending)
- [ ] Support for CalDAV collections
- [ ] Handle different calendar permissions
- [ ] Implement free/busy status
- [ ] Add support for calendar sharing

## Focus Mode Implementation
- [ ] fix keyboard shortcuts
- [ ] in taskmodal make the tags more obvious if they are selected
- [ ] Daily Email

# BUG
- [ ] if i have a bunch of tasks that have isautoscheduled false and i click autoschedule the UI updates with a blank list because no tasks are returned. i have to refresh the page to get the tasks.
- [ ] auto scheduling is creating task in the past (it might be off by one day)
- [ ] auto scheduling did not schedule high priority tasks first
- [ ] save task completed date and sync it with outlook 
- [ ] deleteing a recurring event from quickview doens't work well and doesn't ask me if i want to delete the series or just the instance.
  
## Next Steps
- [ ] Integrate google calendar
  - [ ] auto sync with webhooks
  - [ ] when deleting one event from the series, it deletes all instances locally but google is working fine.
- [ ] prevent adding events to read-only calendars
- [ ] allow changing calendar color
- [ ] allow calendar re-ordering in the UI
- [ ] when deleting a recurring event, it deletes all instances but it shows a random instance which disappears after a sync, also i tried it again and it only deleted the instance locally but the entire series deleted from google.
- [ ] add ability to RSVP
- [ ] show events not RSVPed to
- [ ] show spinner when deleting/creating/updating in event modal
- [ ] Use AI to break down tasks
- [ ] recurring tasks don't indicate that it's recurring
- [ ] Ability to add tasks in calendar view

## Focus Mode Enhancements (Future)
- [ ] Add focus session analytics
  - [ ] Track time spent in focus mode
  - [ ] Record tasks completed per session
  - [ ] Visualize productivity patterns
- [ ] Implement custom focus modes
  - [ ] Deep work mode (2+ hour sessions)
  - [ ] Quick task mode (15-30 minute sessions)
  - [ ] Meeting preparation mode
- [ ] Add Pomodoro technique integration
  - [ ] Configurable work/break intervals
  - [ ] Break reminders
  - [ ] Session statistics

## Outlook sync issues
- [ ] deleting one instance doesn't sync correctly
- [ ] add real-time updates with webhooks
- [ ] implement offline support

## Tasks
- [ ] task dependencies

## 1. Core Calendar Features
- [ ] Calendar Grid Component
  - [ ] Add month view layout
  - [ ] Implement day view layout
  - [ ] Add navigation between days/weeks/months

## 2. Task Management
- [ ] Task Data Structure
  - [ ] Define task interface (title, description, date, duration, status, etc.)
  - [ ] Create task store using Zustand
  - [ ] Implement CRUD operations for tasks
- [ ] Task UI Components
  - [ ] Create task card component
  - [ ] Add task creation modal
  - [ ] Implement task edit modal
  - [ ] Add task details view
  - [ ] Create task list view in sidebar

## 3. Drag and Drop Features
- [ ] Task Rescheduling
  - [ ] Enable drag and drop between time slots
  - [ ] Add visual feedback during drag
  - [ ] Implement time snapping
  - [ ] Handle task duration during drag
- [ ] Task List Reordering
  - [ ] Allow reordering in list view
  - [ ] Sync order changes with store

## 4. Smart Features
- [ ] Task Auto-scheduling
  - [ ] Implement algorithm for finding free time slots
  - [ ] Add priority-based scheduling
  - [ ] Consider task dependencies
- [ ] Time Blocking
  - [ ] Add ability to block out time
  - [ ] Create different block types (focus, meeting, break)
  - [ ] Allow recurring blocks

## 5. Data Persistence
- [ ] Local Storage
  - [ ] Save tasks to localStorage
  - [ ] Implement data migration strategy
- [ ] State Management
  - [ ] Set up Zustand stores
  - [ ] Add undo/redo functionality
  - [ ] Implement data synchronization

## 6. UI/UX Improvements
- [ ] Animations
  - [ ] Add smooth transitions between views
  - [ ] Implement task drag animation
  - [ ] Add loading states
- [ ] Keyboard Shortcuts
  - [ ] Navigation shortcuts
  - [ ] Task creation/editing shortcuts
  - [ ] View switching shortcuts
- [ ] Responsive Design
  - [ ] Mobile-friendly layout
  - [ ] Touch interactions
  - [ ] Adaptive UI based on screen size

## 7. Advanced Features
- [ ] Dark Mode
  - [ ] Implement theme switching
  - [ ] Add system theme detection
- [ ] Calendar Integrations
  - [ ] Google Calendar sync
  - [ ] iCal support
  - [ ] External calendar subscriptions
- [ ] Task Categories
  - [ ] Add custom categories
  - [ ] Color coding
  - [ ] Category-based filtering

## 8. Performance Optimization
- [ ] Component Optimization
  - [ ] Implement virtualization for long lists
  - [ ] Add lazy loading for views
  - [ ] Optimize re-renders
- [ ] State Management
  - [ ] Add request caching
  - [ ] Implement optimistic updates
  - [ ] Add error boundaries

## 9. Testing
- [ ] Unit Tests
  - [ ] Test core utilities
  - [ ] Test state management
  - [ ] Test UI components
- [ ] Integration Tests
  - [ ] Test user flows
  - [ ] Test data persistence
  - [ ] Test drag and drop functionality

## 10. Documentation
- [ ] Code Documentation
  - [ ] Add JSDoc comments
  - [ ] Document component props
  - [ ] Create usage examples
- [ ] User Documentation
  - [ ] Write user guide
  - [ ] Add keyboard shortcut reference
  - [ ] Create onboarding guide

## Implementation Order:
1. Database schema and migrations
2. Core logger service updates
3. API endpoints
4. Settings UI and commands
5. Testing and documentation

## Next Steps
1. Implement the calendar grid component
2. Add basic task management
3. Implement drag and drop functionality
4. Add data persistence
5. Enhance UI with animations and responsive design

## Calendar Sync and Auto-scheduling
- [ ] Implement background sync system
  - [ ] Create useCalendarSync custom hook
  - [ ] Add sync status indicators in UI
  - [ ] Implement error handling and retry logic
  - [ ] Add manual sync trigger to command registry
  - [ ] Add sync preferences to settings
  - [ ] Implement proper cleanup on unmount
  - [ ] Add visual indicators for sync status
  - [ ] Add sync error notifications

## Landing Page Implementation

- [x] Create landing page component in SAAS directory
- [x] Create landing page route in SAAS directory
- [x] Add feature flag for landing page
- [x] Modify middleware to redirect non-logged-in users to landing page
- [x] Create layout file for landing page
- [x] Create helper functions for landing page
- [x] Add tests for landing page
- [x] Update documentation
