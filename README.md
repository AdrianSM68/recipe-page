# Frontend Mentor - Recipe page solution

This is my solution to the [Recipe page challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/recipe-page-KiTsR8QQKm). The goal of this project is to build a responsive recipe page while practising HTML, CSS, Sass and Bootstrap.

## Overview

The project presents a simple omelette recipe, including an image, a short description, preparation times, ingredients, step-by-step instructions and a nutritional information table.

The layout uses a centred white card with a maximum width of 736px. On smaller screens, the card occupies the full available width and its rounded corners are removed.

## My process

### Built with

- Semantic HTML5 markup
- CSS3
- Sass (SCSS syntax)
- Bootstrap
- Local fonts with `@font-face`
- Responsive design with `clamp()` and a media query
- CSS pseudo-classes and pseudo-elements

### What I learned

During this project, I improved my ability to organise SCSS using variables and nested selectors. I also practised combining Bootstrap's container class with custom styles to achieve the intended layout.

One of the most useful techniques was using `clamp()` to adapt the vertical spacing to the viewport width. This allowed me to replace several media queries with a single fluid CSS declaration:

```scss
padding-block: clamp(30px, 8vw, 120px);
```

I also learned how to customise list markers independently of the list text using the `::marker` pseudo-element:

```scss
&::marker {
    color: $primary-hcolor;
    font-size: 0.75rem;
}
```

Another important part of the project was improving HTML semantics and accessibility by using a consistent heading hierarchy, `<strong>` elements and row headers with `scope="row"` in the nutrition table. I also configured the weight range of the Outfit variable font to make better use of its typography.

### Continued development

In future projects, I would like to continue exploring fluid responsive layouts, improve the organisation and reusability of my Sass styles, and make more extensive use of Bootstrap's layout system and utility classes in more complex websites.

## Running the project locally

1. Download or clone the repository.
2. Keep the Bootstrap, image and font assets in their corresponding folders.
3. If you modify the SCSS source, compile it to `css/styles.css` before opening the page.
4. Open `index.html` in a web browser.

The page is static and does not require a backend.

## Style guide

The colours, typography and layout specifications used in this implementation are documented in [style-guide.md](style-guide.md).
