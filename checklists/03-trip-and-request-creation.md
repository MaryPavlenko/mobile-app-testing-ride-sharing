# Checklist #5 — Trip & Request Creation

Covers the **driver** flow ("I'm a driver") and the **passenger** flow ("I'm a passenger"), screen by screen. Format: `check → expected result`. **⚠ Found:** links a check to a defect.
Related requirements: REQ-HOME-02, REQ-HOME-04, REQ-TRIP-01…05.

> **Shared screen conventions** (apply to every screen in this flow, not repeated below):
> orientation change portrait↔landscape keeps all elements/text visible and readable; the screen scrolls in landscape; back navigation preserves previously entered data; on slow networks a loader is shown and the layout does not shift.

## Reusable field block — "From" / "To" city field
Applied on Home, "Where from?", "Where to?", and "Create request":
- The field is tappable; tapping opens the city list.
- Tapping "Close" or outside the dropdown closes it and returns to the original screen.
- All available cities are shown fully and legibly; the list scrolls smoothly up/down.
- A city can be selected; re-tapping the field reopens the list; closing without a choice keeps the previously selected city.
- A selected city can be changed.
- Negative: enter a non-existent city (e.g. "Moscow") → expected: validation error. **⚠ Found: BUG-036…055** (no error shown across screens).
- Negative: enter digits / special characters → expected: validation error. **⚠ Found:** same cluster.

## Home
- "From" / "To" use the reusable field block above.
- Date field: tappable → a date picker opens. **⚠ Found: BUG-041** (empty calendar opens).
- Date picker allows choosing a trip date, scrolls smoothly, and blocks past dates; re-tapping lets the date be changed.
- "Search" button is active only when "From" and "To" are filled; tapping it searches trips.
- ⚠ Note: on Home the From/To fields cannot be left empty after selecting a city; reopening the app from recents clears both fields.

## My Trips entry point
- Bottom-nav "My Trips" opens the section correctly for the current context.
- "Create trip" is tappable; tapping "Create request" switches to the "+" tab.
- Role cards "I'm a driver" / "I'm a passenger" are shown and selectable; back returns to the role choice.

## Driver — "Where from?"
- Navigation back to the role cards works.
- "From" field uses the reusable field block.
- Leaving "From" empty and tapping "Continue". **⚠ Found: BUG-045 / BUG-049** ("Continue" stays clickable on an empty field).
- "Meeting point" cards change with the chosen city and are selectable (selected card highlighted).
- "Custom option" card → reveals a free-text address field with a cursor; accepts letters, digits, special characters.
- Address field validation: accepts empty value and a single character → expected: proper length validation (boundary 0 / 1 / max). **⚠ Found:** missing address validation.
- "Continue" is active only with a valid "From". **⚠ Found: BUG-045** (clickable while empty, incl. with default meeting-point cards filling Dushanbe addresses).

## Driver — "Where to?"
- Navigation back to "Where from?" preserves entered data.
- "To" field uses the reusable field block.
- Leaving "To" empty and tapping "Continue". **⚠ Found: BUG-049** (advances to the "When?" calendar).
- "Arrival point" cards behave like the meeting-point cards above, with the same address-validation gap.
- "Continue" active only with a valid "To".

## Driver — "When?"
- Navigation back preserves data.
- A calendar opens; a future trip date can be chosen; past dates are blocked. **⚠ Found:** today's date is selectable and an already-passed time can be chosen for today (relates to BUG-071).
- The chosen date is displayed on the screen.

## Driver — "What time?"
- Navigation back reopens the calendar to re-pick the date.
- Time picker opens; hour and minute wheels scroll smoothly; the time can be changed by re-tapping.
- "Continue" is active and advances. **⚠ Found:** "Continue" is active even when an already-passed time of today is selected.

## Driver — "Number of seats"
- Counter "How many passengers will you take?" shows "−", value, "+".
- Value range [1; 4]; at 1 the "−" is disabled, at 4 the "+" is disabled; the value changes on tap.
- Checkboxes "Maximum two in the back" and "Instant booking" are selectable, can be cleared by re-tapping, and can both be left unchecked.
- ⚠ Note: choosing 4 passengers then enabling "Maximum two in the back" reduces the count to 3.
- "Continue" advances to the next step.

## Driver — "Payment"
- Navigation back preserves data.
- "Price per 1 passenger" field is tappable with a cursor; accepts digits (boundaries 0 / 1 / 2 / 999 / 1000 / 1001 — note values are capped at 1000); rejects letters, decimals and special characters.
- ⚠ Note: choosing Uzbek cities still shows the price only in TJS on Payment. **→ IMP-099** (add currency selection).
- "Continue" is disabled on an empty or invalid price (e.g. 0) and active on a valid value.

## Driver — "Trip comment"
- Free-text comment field; accepts letters, digits, special characters, spaces; can be left empty (boundary check on length).
- "Continue" is active whether the comment is filled or empty.

## Driver — "Review trip"
- Shows From–To, date, time, price per seat, free seats, comment, matching what was entered earlier.
- Meeting/arrival point section appears only when a card other than "No detail" was chosen; the "Passenger options" section appears only when seat checkboxes were set.
- "Publish trip" is active; publishes if authenticated, otherwise shows "Could not publish — user is not authenticated".
- Auth-error popup closes on "OK".

## Passenger flow — "Create request"
- Route fields "From" / "To" use the reusable field block.
- Date field opens a calendar; a date can be chosen and changed; past dates are blocked. **⚠ Found: BUG-056** (empty calendar / no selectable date).
- Time field opens a time picker; hour/minute wheels scroll; time can be changed.
- Passenger counter "−"/"+"; cannot go below 1 or above 4.
- Comment field accepts letters/digits/special characters/spaces (boundary check on length).
- "Create request" is active when "From"/"To" are filled; creates the request if authenticated, otherwise shows the not-authenticated popup (closes on "OK").
