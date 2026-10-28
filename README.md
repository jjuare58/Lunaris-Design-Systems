# Lunaris Design System Specimen

GIT 337 · Jess Juarez

Design system for **Lunaris Collectibles & Memorabilia**, an active duty service member owned shop in Tacoma, WA that makes laser-engraved trading card binders and custom military gifts.

## Links

- **Repository:** https://github.com/jjuare58/Lunaris-Design-Systems
- **Published page:** https://jjuare58.github.io/Lunaris-Design-Systems/

## Files

- `index.html` – the main page with sections S1–S6
- `styles.css` – contains the reset, tokens, Moonlit theme, and component styles
- `assets/` – contains the logo image
- `screenshots/` – screenshots from my testing

## Notes

- For the color squares in S2, I used the actual color codes because this section is meant to show the colors. The buttons, cards, and forms use tokens instead.

## Test Record

### 1. Responsive (320, 768, 1280px)

- **Expected:** The page should fit different screen sizes without scrolling sideways. The panels should stack on smaller screens and appear next to each other on larger screens.
- **Observed:** I tested all three screen sizes and didn't have any sideways scrolling. At 320px, the panels stacked on top of each other. At 768px and 1280px, they were side by side. I did notice that some code text, like `--space-md`, was splitting in half at 320px.
- **Revision:** I first tried changing `overflow-wrap` to `break-word`, but it didn't fix the issue. I then changed the code style to `white-space: nowrap`, which kept the token names together instead of splitting them.

### 2. Zoom (200%)

- **Expected:** The page should still be readable when zoomed in, without anything getting cut off or overlapping.
- **Observed:** When I zoomed in to 200%, the page changed to one column. I was still able to read everything, and there was no sideways scrolling.
- **Revision:** I didn't need to change anything.

### 3. Keyboard (Tab through the page)

- **Expected:** I should be able to use the Tab key to move through the links, buttons, and form controls. The focus outline should be visible in both themes, and disabled buttons should be skipped.
- **Observed:** I used Tab to go through the entire page and was able to reach everything in order. The black outline in Daylight and gold outline in Moonlit were both easy to see. The disabled buttons were skipped. I also tested the radio buttons with the arrow keys and used Space to select the checkbox.
- **Revision:** I didn't need to change anything.

### 4. Contrast (both themes)

- **Expected:** Text should meet the 4.5:1 contrast requirement, while borders and focus outlines should meet 3:1.
- **Observed:** I used the WebAIM Contrast Checker to test all 10 color pairs in both themes, and they all passed. The text had a contrast ratio of at least 6.8:1, which is above the required 4.5:1. Button text was 8.1:1 in Daylight and 7.9:1 in Moonlit. The focus outlines were 15.4:1 in Daylight and 11.7:1 in Moonlit. The lowest result was the Daylight input border at 4.1:1, which still passed the 3:1 requirement.
- **Revision:** I didn't need to change anything.

### 5. Font fallback (removed Google Fonts link)

- **Expected:** If Google Fonts doesn't load, the headings should use Georgia and the body text should use Arial. The layout should still work.
- **Observed:** I commented out the Google Fonts link to see what would happen. The headings changed to Georgia and the body text changed to Arial. The page still looked fine, and nothing overflowed.
- **Revision:** I didn't need to change the CSS. I added the Google Fonts link back after testing.

### 6. Validation (W3C HTML and CSS validators)

- **Expected:** My HTML and CSS should have no errors.
- **Observed:** I checked both files using the W3C validators. The HTML passed without any errors or warnings. The CSS also had no errors, but it showed 6 warnings related to CSS variables because the validator couldn't check them.
- **Revision:** I didn't need to change anything.

### 7. Publication (private browser window)

- **Expected:** The published page should load correctly, including the styles, fonts, logo, and links.
- **Observed:** Published correctly with all content. 
- **Revision:** none

**Evidence-based revision:** During my responsive testing at 320px, I noticed that token names like `--space-md` were splitting in half. I tried using `overflow-wrap: break-word` first, but it didn't fix the problem. I changed it to `white-space: nowrap`, which kept the token names together. I tested the page again to make sure the text displayed correctly.

## Code Defense

**Reset:**  I kept my reset simple and only changed the browser defaults that might cause issues with my layout. I used box-sizing: border-box to keep padding and borders within the width I set, removed the default body margin, and made sure images fit smaller screens. I also used font: inherit so buttons and inputs would match the rest of the page.

**Tokens:** I used tokens to keep my colors, spacing, fonts, and sizes organized in one place. Instead of typing the same values over and over, I used variables like --color-bg and --space-md. This made it easier to keep everything consistent and make changes without going through each part of my CSS.

**Theme override:** For my Moonlit theme, I used .theme-moonlit to change the color tokens instead of rewriting all my CSS. This allowed me to use the same buttons, cards, and forms for both themes while giving each one different colors. I also used lighter colors for Moonlit so the text and buttons would still be easy to see against the dark background.

**Revision:**  During my responsive testing at 320px, I noticed that some token names, like --space-md, were splitting in half. I first tried using overflow-wrap: break-word, but it didn't fix the issue. I then changed it to white-space: nowrap, which kept the token names together. After making the change, I tested the page again to make sure everything displayed correctly.

## AI Disclosure

I used Chat GPT to help find repeated values, suggest token names, compare different CSS options, and better understand how the code works. AI made suggestions for revision and I reviewed them and made changes based off my design.