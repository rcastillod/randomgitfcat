<template>
  <div id="app" class="grid">
    <main class="main">
        <div class="container">
          <gifcat></gifcat>
        </div>
    </main>
  </div>
</template>

<script>
import GifCat from '@/components/GifCat.vue'

export default {
  name: 'App',
  data: function() {
    return {}
  },
  components: {
    'gifcat': GifCat
  }
}
</script>

<style>
/* -------------------------------------------------------------------------- */
/*                              CUSTOM PROPERTIES                             */
/* -------------------------------------------------------------------------- */
:root {

    /* Colors */
    --primary-color: 344 92% 59%;
    --primary-color-tint: 354 90% 70%;
    --secondary-color: 223 96% 20%;
    --text-color: 45 44% 89%;
    --white-color: 0 0% 100%;
    --black-color: 0 0% 0%;

    /* Font Familiy */
    --heading-font: 'Poppins', sans-serif;;
    --body-font: 'Poppins', sans-serif;

    /* Font Weights */
    --fw-thin: 100;
    --fw-light: 300;
    --fw-regular: 400;
    --fw-medium: ;
    --fw-semibold: ;
    --fw-bold: 700;
    --fw-black: ; 

}

/* -------------------------------------------------------------------------- */
/*                                    RESET                                   */
/* -------------------------------------------------------------------------- */

/* https://piccalil.li/blog/a-modern-css-reset/ */

/* Box sizing rules */
*,
*::before,
*::after {
    box-sizing: border-box;
}

/* Remove default margin */
body,
h1,
h2,
h3,
h4,
p,
figure,
blockquote,
dl,
dd {
    margin: 0;
}

/* Remove list styles on ul, ol elements with a list role, which suggests default styling will be removed */
ul[role='list'],
ol[role='list'] {
    list-style: none;
}

ul,
ol {
    margin: 0;
    padding: 0;
    list-style-type: none;
}

/* Set core root defaults */
html,
html:focus-within,
body {
    scroll-behavior: smooth;
}

/* Set core body defaults */
body {
    color: hsl( var(--text-color) );
    font-family: var(--body-font);
    height: 100vh;
    text-rendering: optimizeSpeed;
    line-height: 1.5;
}

main {
    position: relative;
    width: 100%
}

section {
    height: 100%;
    padding-block-start: 9.375rem;
}

/* A elements that don't have a class get default styles */
a:not([class]) {
    text-decoration-skip-ink: auto;
}

/* Make images easier to work with */
img,
picture {
    max-width: 100%;
    display: block;
}

/* Inherit fonts for inputs and buttons */
input,
button,
textarea,
select {
    font: inherit;
}

/* Remove all animations, transitions and smooth scroll for people that prefer not to see them */
@media (prefers-reduced-motion: reduce) {
    html:focus-within {
        scroll-behavior: auto;
    }

    *,
    *::before,
    *::after {
        animation-duration: 0.01ms !important;
        animation-iteration-count: 1 !important;
        transition-duration: 0.01ms !important;
        scroll-behavior: auto !important;
    }
}

/* -------------------------------------------------------------------------- */
/*                               UTILITY CLASSESS                             */
/* -------------------------------------------------------------------------- */

/* General */

.flex {
    display: flex;
    gap: var(--gap, 1rem);
}

.direction-column {
    flex-direction: column;
}

.grid {
    display: grid;
    gap: var(--gap, 1rem);
}

.flow > *:where(:not(:first-child)) {
    margin-top: var(--flow-gap, 1rem);
}

.container {
    padding-inline: 2em;
    margin-inline: auto;
    max-width: min(100% - 2rem, 68.75rem);
}

.section-title {
    color: hsl( var(--white-color) );
    font-family: var(--heading-font);
    font-size: 4rem;
    font-weight: var(--fw-bold);
    letter-spacing: .325rem;
    line-height: 1.2;
    max-width: 18ch;
}
.section-title span {
    display: inline-flex;
    align-items: center;
    gap: 0.25em;
    position: relative;
}
.section-title span::after {
    content: '';
    background-color: hsl( var(--white-color) );
    height: 0.4375rem;
    width: 1.175em;
}

.btn {
    font-size: 1rem;
    padding-block: .625em;
    width: 5em;
    text-align: center;
    text-decoration: none;
}

.sr-only {
    position: absolute;
    width: 1px;
    height: 1px;
    padding: 0;
    margin: -1px;
    overflow: hidden;
    clip: rect(0, 0, 0, 0);
    white-space: nowrap;
    border: 0;
}

/* -------------------------------------------------------------------------- */
/*                                 COMPONENT                                  */
/* -------------------------------------------------------------------------- */
body {
  background-image: url(assets/bg-cat.jpg);
  background-size: cover;
  background-repeat: no-repeat;
  background-position: center center;
}
#app {
  height: 100%;
  place-items: center;
}

</style>
