---
description: 'Last updated: 2.0.0 (16/01/2024)'
---

# ✍ Using custom fonts

You may pretty quickly bump up against the fact that Valence will default to using your system's fonts.&#x20;

> This guide assumes you have followed your chosen Discipline library's Getting Started guide.

1. To start, download and save whichever font/s you want to use in your project. In this example we're going to use [Plus Jakarta Sans](https://fonts.google.com/specimen/Plus+Jakarta+Sans), which is available for free on Google Fonts. Relevant files from this font have been saved to the `src/assets/fonts/` folder in our project directory.
2. Then, we're going to define and import the fonts into a `global.css` file, which we will then import. We're going to create the file in `src/assets/css/`, then paste the standard CSS font imports like so:

```css
@font-face {
  font-family: "PlusJakartaSans";
  src: local("PlusJakartaSans-Regular"), 
       url("../fonts/PlusJakartaSans-Regular.ttf") 
       format("truetype");
  font-weight: 400;
  font-style: normal;
}
@font-face {
  font-family: "PlusJakartaSans";
  src: local("PlusJakartaSans-Italic"), 
       url("../fonts/PlusJakartaSans-Italic.ttf") 
       format("truetype");
  font-weight: 400;
  font-style: italic;
}
@font-face {
  font-family: "PlusJakartaSans";
  src: local("PlusJakartaSans-Bold"),
       url("../fonts/PlusJakartaSans-Bold.ttf") 
       format("truetype");
  font-weight: 800;
  font-style: normal;
}
@font-face {
  font-family: "PlusJakartaSans";
  src: local("PlusJakartaSans-BoldItalic"), 
       url("../fonts/PlusJakartaSans-BoldItalic.ttf") 
       format("truetype");
  font-weight: 800;
  font-style: italic;
}


/* The rest of our css from before */
```

3. Then, head back into the root app file (usually `App.tsx` or `App.jsx`) and import the `global.css` file:

```tsx
import "./assets/css/global.css"

// The rest of your code...
```

4. Finally, we can update the `ValenceProvider` to use our new font/s:

```tsx
// Some codefunction App() {
  // Hooks, etc.

  return (
    <>
      <ValenceProvider
        fontFamily={{
          default: "PlusJakartaSans"
        }}
      >
        {/* Your app's contents */}
     </ValenceProvider>
    <>
  )
}
```

That's all there is to it! Valence will default to using this font when it needs a monospace or heading font, however you can supply different fonts to them by updating the `fontFamily` prop of the `ValenceProvider` with references to those fonts.
