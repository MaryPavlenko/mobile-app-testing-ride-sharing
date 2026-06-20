# Checklist #7 — My Trips

Format: `check → expected result`. **⚠ Found:** links a check to a defect.
Related requirements: REQ-MYTRIPS-01, REQ-MYTRIPS-02.

## 1. "My Trips" screen
- Title "My Trips" shown without truncation.
- Tabs "Active", "Requests", "History" are visible and legible; "Active" is selected by default (underline/bold).
- Empty-state icon (car/road) centred; "You have no upcoming trips yet" and the sub-text show without truncation.
- Bottom navigation is visible and not overlapped by UI.

## 2. Tabs & empty states
- "Requests" switches the screen; empty list shows "No requests yet".
- "History" switches the screen; empty list shows "Trip history is empty".
- Returning to "Active" restores state without freezing; the active-tab indicator moves smoothly.
- When a tab has trips, the empty state is not shown (data loads).

## 3. Trip list display
- After creating a trip it appears in the right tab (e.g. "Active").
- The trip card shows correct data: "From → To", date and time.
- Trip status is correct (e.g. "Looking for passengers", "Awaiting confirmation").
- Long lists scroll without freezing; cards do not overlap the bottom navigation; refresh pulls current data (if an API is present). **⚠ Found:** sorting puts the nearest trip last (BUG-084).

### 3.1 Loading on slow networks
- A loader/spinner is shown until the list is received and does not disappear prematurely on slow connections.
- The UI does not shift on slow connections (no overlap, no text truncation); after loading the loader disappears and the list renders cleanly.
- Backgrounding and returning preserves the tab state; date and time display correctly.

## 4. No-data / error handling
- First entry: "Active" is empty with a placeholder and a "Create trip" CTA (as per the mockup).
- Empty "Requests" / "History" show their placeholders.
- On a load error (e.g. network): a clear error message and a "Retry" / "Refresh" option.
- Opening "My Trips" with no network: the app does not crash; an empty list or an offline message is shown.

## 5. UX / Android-specific (Galaxy A12)
- All texts render without truncation at the device's font density.
- Rotation preserves the tab data/state with no reload or navigation.
- Repeated switching between tabs does not freeze or crash the app.
- The system Back button goes to the previous screen (e.g. Home), not a restart of "My Trips". **⚠ Found: BUG-069** (back-stack loss across the app).
- Rapid repeated open/close of "My Trips" does not crash the app.
