# Plan: Authentication Pages — FigCraft Design (Desktop)

## Overview

Design desktop authentication pages (Login + Signup) in FigCraft via the connected FigCraft MCP server, saved under `design/desktop/`.

## Requirements

1. **Theme**: Indigo
2. **Pages**: Login and Signup (authentication)
3. **Fields**: Both pages ask for **username** and **password**
4. **Recovery phrase**: After signup, the user receives a recovery phrase (e.g., `"Apple Car Cat Mountain"`)

## Indigo Theme Tokens

| Token | Hex |
|---|---|
| Primary | `#3F51B5` (Indigo 500) |
| Primary Dark | `#303F9F` (Indigo 700) |
| Primary Light | `#C5CAE9` (Indigo 100) |
| Surface / Background | `#FFFFFF` |
| App Background | `#F5F6FA` |
| Text Primary | `#212121` |
| Text Secondary | `#757575` |
| Error | `#D32F2F` |
| Focus / Border | `#9FA8DA` (Indigo 200) |

Typography: Inter — headings 24/32, body 14/20, labels 12/16.
Buttons: Indigo 500 fill, white text, corner radius 8, height 44.
Inputs: 1px Indigo 200 border, focus border Indigo 500, height 44, corner radius 8.

## File / Page Structure

Save file: `design/desktop/auth.figcraft`

Pages in the FigCraft document:
- `Login`
- `Signup`
- `Signup — Recovery Phrase` (success state shown after signup)

## Screens

### 1. Login (`Login` page)

Desktop frame: **1440 x 900**, centered auth card **420 x 480**.

Card contents (vertical auto layout, gap 24, padding 40):
- App logo / title (Indigo 700)
- Heading: "Welcome back"
- Label: "Username" + input field (placeholder "Enter your username")
- Label: "Password" + input field (placeholder "Enter your password", type password)
- Primary button: "Log in" (full width)
- Footer link: "Don't have an account? Sign up" (Indigo 500)

### 2. Signup (`Signup` page)

Desktop frame: **1440 x 900**, centered auth card **420 x 560**.

Card contents (vertical auto layout, gap 24, padding 40):
- App logo / title (Indigo 700)
- Heading: "Create your account"
- Label: "Username" + input field (placeholder "Choose a username")
- Label: "Password" + input field (placeholder "Choose a password", type password)
- Primary button: "Sign up" (full width)
- Footer link: "Already have an account? Log in" (Indigo 500)

### 3. Signup Success — Recovery Phrase (`Signup — Recovery Phrase` page)

Desktop frame: **1440 x 900**, centered card **420 x 520**.

Card contents (vertical auto layout, gap 24, padding 40):
- Success icon (Indigo 500)
- Heading: "Your recovery phrase"
- Helper text: "Write this down and keep it safe. You'll need it to recover your account."
- Recovery phrase display box (Indigo 100 background, Indigo 200 border, corner radius 8):
  - 4 word chips or plain text: `Apple Car Cat Mountain` (16/24, medium, letter-spacing wide)
- Button: "I've saved my recovery phrase" (primary, full width)
- Button: "Copy phrase" (text button, Indigo 500)

## Execution Steps (via FigCraft MCP)

1. Create text layer / open new document; save as `design/desktop/auth.figcraft`.
2. Create page `Login`; build 1440x900 frame with indigo app background, then the auth card frame with vertical auto layout (gap 24, padding 40) and the components above.
3. Create page `Signup`; repeat with signup contents.
4. Create page `Signup — Recovery Phrase`; build success card with the recovery phrase box.
5. Reuse styling: inputs as rectangles with border + placeholder text; keep consistent 8px radius and 44px control heights.
6. Verify with `inspect_document` / `screenshot` after each page; fix spacing/alignment issues.
7. Save the file to `design/desktop/auth.figcraft`.

## Acceptance Criteria

- [ ] Indigo palette used consistently (buttons, links, focus borders, phrase box)
- [ ] Login page shows username + password fields
- [ ] Signup page shows username + password fields
- [ ] Recovery phrase screen shows a 4-word phrase (e.g., "Apple Car Cat Mountain") after signup
- [ ] Desktop 1440x900 frames, centered cards, consistent typography and spacing
- [ ] File saved under `design/desktop/auth.figcraft`
