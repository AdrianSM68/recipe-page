# Recipe page - Style guide

This guide documents the values used in the project's SCSS implementation.

## Layout

The recipe is displayed inside a responsive card centred using Bootstrap's `.container` class and a custom `.recipe-card` class.

- Card width: 100%
- Maximum card width: 736px
- Card padding: 40px, except for the bottom (30px)
- Card border radius: 20px
- Image width: 100% of the available content area
- Image border radius: 10px
- Responsive breakpoint: 736px
- Vertical page padding: `clamp(30px, 8vw, 120px)`

At viewport widths of 736px or less, the card becomes full-width, its border radius is removed and the vertical page padding is set to zero. The card's internal padding remains unchanged.

## Colours

### Main palette

| Colour | Hex | SCSS variable | Usage |
| --- | --- | --- | --- |
| Light beige | `#F3E5D8` | `$bgcolor` | Page background |
| White | `#FFFFFF` | — | Recipe card background |
| Light rose | `#FFF7FC` | `$secondary-color` | Preparation time background |
| Dark charcoal | `#363231` | `$text-color` | Main text |
| Warm grey | `#666462` | `$secondary-text-color` | Description, lists and secondary text |
| Brown | `#855137` | `$primary-hcolor` | Section headings, list markers and nutritional values |
| Dark rose | `#762548` | `$secondary-hcolor` | Preparation heading and list markers |
| Light grey | `#DDDDDD` | — | Section and table row dividers |

## Typography

### Body

- Font family: [Outfit](https://fonts.google.com/specimen/Outfit)
- Font source: local variable TTF file
- Available weights: 100–900
- Font style: normal
- Fallback: sans-serif
- Base font size: inherited (no explicit body font size is set in the custom SCSS)

### Headings

- Font family: [Young Serif](https://fonts.google.com/specimen/Young+Serif)
- Font source: local TTF file
- Declared font weight: 400
- Font style: normal
- Fallback: serif
- Main heading: Young Serif, capitalised using `text-transform: capitalize`
- Section headings: 1.75rem, brown (`#855137`)
- Preparation heading: Outfit, 20px, bold, dark rose (`#762548`)

### Emphasis and list markers

- Important phrases: semantic `<strong>` elements
- Unordered list markers: 0.75rem
- Ordered list markers: bold Outfit
- Nutritional values: bold, brown (`#855137`)
- Nutritional row labels: normal font weight

## Spacing

| Element | Value |
| --- | --- |
| Image bottom margin | 40px |
| Main heading bottom margin | 20px |
| Recipe description bottom margin | 30px |
| Preparation box padding | 25px |
| Preparation box bottom margin | 35px |
| Preparation box border radius | 10px |
| Main section bottom margin | 30px (except the last section) |
| Main section bottom padding | 10px |
| Main section heading bottom padding | 10px |
| List indentation | 20px |
| List item left padding | 20px |
| Main section list item bottom padding | 7px |
| Preparation list item bottom padding | 10px (except the last item) |
| Table cell vertical padding | 13px |

## Borders

- Main sections: 1px solid `#DDDDDD` bottom border, except the last section.
- Nutrition table rows: 1px solid `#DDDDDD` bottom border, except the last row.
- No outer border on the nutrition table.

## Responsive design

```scss
body {
    padding-block: clamp(30px, 8vw, 120px);
}

@media (max-width: 736px) {
    body {
        padding-top: 0;
        padding-bottom: 0;
    }

    .recipe-card {
        min-width: 100%;
        max-width: 100%;
        border-radius: 0;
    }
}
```

The layout relies on a fluid card width, a responsive image and natural text wrapping rather than separate fixed layouts for desktop and mobile.
