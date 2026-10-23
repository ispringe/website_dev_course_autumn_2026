**Izolde Springe**
Laurea University of Applied Sciences

**Project Report**
Website Development / Berfin Ala-Krekola
23.10.2026

# Website Development Project Report

## Contents

1. General information about the project
2. Techniques used and special features
3. Website design and structure
4. Self-assessment and development of my skills
5. Feedback to the teacher on the course and teaching so far
6. Links
   - 6.1 Website address
   - 6.2 Link to the GitHub repository
   - 6.3 Link to the project video presentation
7. Validation screenshots
8. Sources

---

## 1 General information about the project

My project is **Dirt & Pine**, a website about mountain biking (MTB). It is a guide for riders of every level, from people thinking about their first trail ride to riders who want to try more technical trails. The site explains the different riding styles, how to read trail difficulty signs, what gear is needed, and it lets visitors book a place on a weekly group ride.

The site has five pages:

- **Home**: introduction to mountain biking, why it is worth trying, facts and links to the rest of the site
- **Trails**: the four riding styles, a table of trail difficulty symbols, trail rules and tips for a first ride
- **Gear**: the main bike types, an essential kit checklist and answers to common questions
- **Gallery**: an automatic slideshow and a photo gallery that opens photos in a larger view
- **Join a Ride**: a booking form for group rides and the weekly ride schedule

I chose mountain biking as my topic because it is a great way to explore nature and clear my mind. I wanted to make a site that could encourage other people to try it too.

## 2 Techniques used and special features

The website is built with **HTML5 and CSS3**, plus a small part of the **Bootstrap 5** framework on the Join a Ride page. It uses no JavaScript, so every effect is done with CSS. All pages share one stylesheet, `css/style.css`.

**HTML**

- Semantic page structure: `header`, `nav`, `main`, `section`, `article`, `aside`, `figure`, `figcaption` and `footer`
- A data table with `caption`, `thead`, `tbody` and `scope` attributes on the headings
- A booking form with many input types: text, email, tel, date, select, radio buttons, checkboxes, a range slider and a textarea. It uses `fieldset` and `legend` to group fields and `required` for browser validation.
- A FAQ accordion made with the native `details` and `summary` elements
- A definition list (`dl`) for the ride schedule
- Accessibility features: alt text on every image, a "skip to content" link, `aria-current` to mark the current page in the menu, and labels for every form field

**CSS**

- **Responsive layout** with CSS Grid and Flexbox, and media queries at 800 px and 520 px. Grids use `repeat(auto-fit, minmax(...))` so the number of columns adapts to the screen width without extra media queries.
- **Responsive images** with `max-width: 100%`, `height: auto` and `object-fit: cover`
- **Fluid typography** with `clamp()`, so headings scale smoothly between phone and desktop sizes
- **CSS custom properties** (variables) for the colour palette, fonts and shared values
- **Mobile menu without JavaScript**: a hidden checkbox and the `:checked` selector open the menu, and the hamburger icon animates into an X
- **Pure CSS slideshow** using `@keyframes` and `animation-delay`. It pauses when the mouse is over it.
- **Pure CSS lightbox** using the `:target` selector, with previous and next arrows
- **Hover and focus effects**: cards that lift with a shadow, images that zoom, gallery captions that slide up, navigation underlines that grow, and buttons that move
- **3D flip cards** for the bike types, using `perspective`, `transform-style: preserve-3d` and `backface-visibility`. They also flip with the keyboard.
- **Pseudo-elements** (`::before` and `::after`) for the mountain shape under each banner (`clip-path`), the decorative quote mark, check marks in lists and the trail difficulty symbols
- **CSS counters** to number the benefits and trail rules automatically
- **Custom form controls**: skill level radio buttons styled as pill buttons
- **Accessibility in CSS**: visible focus outlines, and a `prefers-reduced-motion` media query that turns off animations for users who prefer less motion
- **Google Fonts**: Oswald for headings and Source Sans 3 for body text

**Bootstrap**

Bootstrap was part of the course material (Workshop 6), so I used it on the Join a Ride page. I only load the Bootstrap CSS file, not its JavaScript, so the site still works without any scripts.

- **Alert component**: the note under the booking form, which says that no data is sent anywhere, uses Bootstrap's `alert alert-success` classes
- **Progress bar component**: the weekly ride schedule shows how many places are booked on each ride with Bootstrap's `progress` and `progress-bar` classes
- **Utility classes**: `d-flex`, `justify-content-between`, `small`, `mt-2`, `mb-1` and the width classes `w-25`, `w-50` and `w-75`
- **Themed to match the site**: I changed the Bootstrap components' colours to the site's pine and moss colours with Bootstrap's own CSS variables (for example `--bs-progress-bar-bg`), so they do not look like default Bootstrap
- **Cascade layers**: Bootstrap is loaded in `css/bootstrap.css` with `@import ... layer(bootstrap)`. Rules in a cascade layer always lose to normal rules, so my own `style.css` always wins over Bootstrap. This was needed because Bootstrap also has classes called `container`, `btn` and `card`, and without the layer it would have changed my own buttons and cards.

## 3 Website design and structure

I wanted my website to feel adventurous and encouraging, but not overstimulating. The site should make visitors want to get out on the trails, while still being calm and easy to read. That is why I used natural forest colours, plenty of white space and only gentle animations.

The design is inspired by the forest. The colour palette uses dark pine green, moss green, a warm sand colour for backgrounds and a burnt orange accent for buttons and links. Headings use the tall, condensed Oswald font in capital letters, which gives a sporty look, while the body text uses the easy-to-read Source Sans 3.

Every page has the same structure, so the site is easy to use:

1. A sticky header with the logo and the main menu, which stays visible while scrolling. The current page is underlined in the menu.
2. A large banner with a photo, a green overlay and a mountain-shaped bottom edge
3. Content sections that alternate between light and slightly darker backgrounds, so they are easy to tell apart
4. A footer with a short description and links to every page

Users can reach every page from the main menu and from the footer on every page. The home page also has a card for each section of the site, and pages link to each other where it makes sense, for example from the trail tips to the gear page and from the booking form to the trail rules.

On phones, the menu collapses into a hamburger button, grids stack into one column, the form fields fill the full width, and gallery captions are always visible because touch screens have no hover.

**File structure**

```
final-project/
├── index.html      Home
├── trails.html     Trails
├── gear.html       Gear
├── gallery.html    Gallery
├── join.html       Join a Ride
├── css/
│   ├── style.css       Shared stylesheet
│   └── bootstrap.css   Loads Bootstrap 5 (Join a Ride page)
└── images/         Photos
```

## 4 Self-assessment and development of my skills

I am happy with the result. I think I succeeded especially with the visual side of the site: the generated illustrations give every page its own atmosphere, and the 3D flip cards on the Gear page are a fun way to show information.

With more time, I would add a map and a route planning section, so that visitors could find trails near them and plan their own rides.

I have learned a lot since Workshop 1. At the start of the course I knew only the basics of HTML, and now I can build a complete responsive website with my own CSS. I also learned how to use Bootstrap and how to combine it with my own stylesheet.

I would give myself 27/30 points. All the other requirements of the project are satisfied, but doing live video demos is not my comfort zone, so I think the video presentation is the weakest part of my work.

## 5 Feedback to the teacher on the course and teaching so far

The learning material was very useful, and I could go back to it many times while working on the project.

The hardest part for me was the CSS. Getting the layout and the details to look right took a lot of time.

One thing I would change is to add content management techniques to the course. Then not all of the content would have to be written inside the HTML files, which would make bigger websites easier to build and update.

## 6 Links

### 6.1 Website address

https://ispringe.github.io/website_dev_course_autumn_2026/final-project/

### 6.2 Link to the GitHub repository

https://github.com/ispringe/website_dev_course_autumn_2026

### 6.3 Link to the project video presentation

[Add the video link here, for example YouTube or video.laurea.fi.]

## 7 Validation screenshots

[Add screenshots of the results for each page and for the stylesheet.]

- W3C HTML validator (https://validator.w3.org/): index.html, trails.html, gear.html, gallery.html, join.html
- W3C CSS validator (https://jigsaw.w3.org/css-validator/): css/style.css
- HTMLHint
- Stylelint

## 8 Sources

**Printed**

Isaacson, W. 2007. Einstein: His Life and Universe. New York: Simon & Schuster. (Source of the Einstein quote on the home page, from a letter to his son Eduard in 1930.)

**Electronic**

Anthropic. 2026. Claude Code. AI assistant used to generate all 16 images on the website. The images are illustrations drawn with a Python script using the Pillow library, not real photographs. Accessed 23 October 2026. https://www.anthropic.com/claude

Bootstrap. 2026. Bootstrap 5.3 documentation: Alerts, Progress and Utilities. Accessed 23 October 2026. https://getbootstrap.com/docs/5.3/

Google. 2026. Google Fonts: Oswald and Source Sans 3. Accessed 23 October 2026. https://fonts.google.com/

International Mountain Bicycling Association (IMBA). 2026. Rules of the Trail. Accessed 23 October 2026. https://www.imba.com/

Mozilla. 2026. MDN Web Docs: HTML and CSS reference. Accessed 23 October 2026. https://developer.mozilla.org/

W3C. 2026. Markup Validation Service. Accessed 23 October 2026. https://validator.w3.org/

W3C. 2026. CSS Validation Service. Accessed 23 October 2026. https://jigsaw.w3.org/css-validator/

**Unpublished**

Laurea University of Applied Sciences. 2026. Website Development course workshop materials, Workshops 1–6.
