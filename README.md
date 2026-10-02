# Team Random Spinner

A simple single-page web app for randomly selecting a team member from a spinner wheel. It is built with plain HTML, CSS, and JavaScript in one file, so it does not need npm, a build step, or a backend server.

## Features

- Spin a visual wheel to pick one selected team member.
- Add, edit, and permanently delete members.
- Upload member profile images.
- Include or exclude members from the next spin.
- Cut the winner from the spinner after a result.
- Select all, clear all, or reset the spinner to the original data.
- Edit the page title.
- Save changes in the browser with `localStorage`.
- Responsive layout for desktop and mobile screens.

## Project Structure

```text
.
|-- index.html
`-- README.md
```

## How to Run

Open `index.html` directly in a browser.

You can also serve it with any simple static server if you prefer:

```bash
python3 -m http.server 8000
```

Then visit:

```text
http://localhost:8000
```

## How It Works

The whole app lives in `index.html`:

- The HTML creates the spinner area, member list, edit modal, title modal, and result modal.
- The CSS styles the page, spinner wheel, member rows, modals, responsive layout, and animations.
- The JavaScript manages app state, renders the wheel, handles spinning, saves data, and updates members.

The spinner only uses members where `included` is `true`. When the wheel stops, the script calculates which segment is under the pointer and shows that member in the result popup.

## Data Storage

User changes are saved in browser `localStorage` under this key:

```text
teamSpinnerFullStateV1
```

This means:

- Data stays in the same browser after refresh.
- Data is not shared between different browsers or devices.
- Clearing browser site data will remove saved members and title changes.
- The `Reset` button restores the original title and starter members from the code.

## Customization

Useful places to edit in `index.html`:

- `INITIAL_TITLE`: default page title.
- `INITIAL_MEMBERS`: starter members shown on first load or after reset.
- `PALETTE`: colors used for wheel segments.
- CSS variables in `:root`: main colors for the page.

## Notes for Developers

This project intentionally avoids external dependencies. If the app grows, a good next step would be splitting the single `index.html` file into separate `HTML`, `CSS`, and `JS` files before adding more complex features.
