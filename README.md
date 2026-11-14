# Media and Typography Lab

This page was used for Module 4 practice to test responsive images, SVG accessibility, typography tokens, fluid sizing, and layout-shift prevention.

## Files

- `index.html`: Page structure, responsive image markup, and decorative SVG.
- `styles.css`: Typography tokens, responsive layouts, and fluid sizing.
- `assets/sprout.svg`: Decorative SVG icon from Lucide.
- `assets/garden-400.jpg`, `assets/garden-800.jpg`, `assets/garden-1200.jpg`: Responsive image variants referenced by the hero image.

## Implementation Notes

### Media Decision

The hero image uses `srcset` and `sizes` to allow the browser to select an appropriate image based on the viewport and rendered image size. The image includes descriptive alternative text and a source attribution in its caption.

### Typography Decision

CSS custom properties define the font family, body and heading sizes, line heights, maximum text measure, and spacing. The main heading uses `clamp()` to scale between `2rem` and `3.5rem` based on the viewport width. A system font stack provides font fallbacks without requiring external font downloads.

### Layout-Shift Prevention

The hero image includes explicit `width` and `height` attributes, along with a CSS `aspect-ratio` of `3 / 2`, to reserve space before the image loads. The SVG also includes explicit dimensions.

### SVG Accessibility

The sprout icon is decorative and uses an empty `alt` attribute so screen readers can ignore it. The surrounding heading provides the relevant section information.

## Testing Notes

- **Narrow viewport:** The hero displays in a single column with the image below the text. Workshop cards stack vertically, and content fits without horizontal overflow.
- **Wide viewport:** The hero displays in two columns with text beside the image. Workshop cards display in multiple columns.
- **200% zoom:** The layout adapts to the reduced available viewport width. Text remains readable, content stays accessible, and no horizontal scrolling is required.
- **Slow network:** The hero image reserves its space before loading. The heading and paragraph remain visible while the image downloads, and the page remains usable. The image eventually displays correctly.
- **Performance:** Achieved a Lighthouse Performance score of 100/100.

## Asset Attribution

- **Hero photograph:** Ngobeni Communications, Unsplash. Attribution is included in the image caption.
- **Sprout SVG:** [Lucide Sprout](https://lucide.dev/icons/sprout), licensed under the [ISC License](https://lucide.dev/license).

## AI Disclosure

I used ChatGPT to review the implementation against the assignment requirements, discuss responsive behavior and accessibility, and help organize the documentation. I implemented the code and performed browser testing to verify the results.
