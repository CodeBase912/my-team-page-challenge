<!-- Please update value in the {}  -->

<h1 align="center">The My Team page challenge</h1>

<div align="center">
   Solution for a challenge from <a href="http://devchallenges.io" target="_blank">Devchallenges.io</a>.
</div>

<div align="center">
  <h3>
    <a href="https://{your-demo-link.your-domain}">
      Demo
    </a>
    <span> | </span>
    <a href="https://{your-url-to-the-solution}">
      Solution
    </a>
    <span> | </span>
    <a href="https://devchallenges.io/challenges/hhmesazsqgKXrTkYkt0U">
      Challenge
    </a>
  </h3>
</div>

<!-- TABLE OF CONTENTS -->

## Table of Contents

- [Table of Contents](#table-of-contents)
- [Overview](#overview)
  - [Built With](#built-with)
- [Experience](#experience)
- [Contact](#contact)

<!-- OVERVIEW -->

## Overview

![screenshot](https://user-images.githubusercontent.com/16707738/92399059-5716eb00-f132-11ea-8b14-bcacdc8ec97b.png)

Challenge:

- Create my team page following the design. The page should be responsive. Fulfill user stories below

User story:

- User see a page following the given design

Another interesting challenge from <a href="http://devchallenges.io" target="_blank">Devchallenges.io</a>. Great for fine-tuning your mobile responsive CSS skills.

### Built With

<!-- This section should list any major frameworks that you built your project using. Here are a few examples.-->

- Semantic HTML markup
- CSS custom properties
- CSS Grid & Flexbox
- <a href="https://en.bem.info/methodology/" target="_blank">BEM</a> naming convention - useful for avoiding conflicting class names

## Experience

I had a lot of fun working on this project, but ran into some slight gotchas when making the page responsive. It was also challenging to see implement the staggered cards feature, since I used CSS `grid-template-columns` for a responsive grid for the cards and the fact that you can't select specific columns within the grid in pure css (this was even worse given that the grid was responsive, i.e. the number of columns in the grid changes with the device width). The problem was having to select the correct column of cards to add a `margin-top` to, to create the staggered card effect.

A solution I came up with was to use the `nth-child` CSS psuedo-selector to select the column of interest within the grid and adjust the selection at each breakpoint. Like so,

```css
.team__member__card:nth-child(3n - 1) {
  margin-top: 100px;
}

...

/* Breakpoint: 865px - this is the point where the grid switches from
                       3 to 2 columns (i.e. switching to a smaller screen)
*/
@media screen and (max-width: 865px) {
  /* Unset the styles of previous selection */
  .team__member__card:nth-child(3n - 1) {
    margin-top: 0px;
  }

  /* Update the selection + add style */
  .team__member__card:nth-child(2n) {
    margin-top: 100px;
  }
}

...
```

This soluiton can get pretty hard to maintain if you have a lot of breakpoints on your page or if you're working on large project. In such cases I would suggest maybe trying a library like <a href="https://sass-lang.com/" target="_blank">Sass</a>, which can help handle such gotchas in a way that's easier to maintain for large projects.

I decided to keep this solution since this is a small project and I didn't want to add Sass just for this one minor issue.

<!-- If you came up with a better soluiton you can let me know by sending me feedback <a href="https://sass-lang.com/" target="_blank">here</a> -->

## Contact

- LinkedIn - <a href="https://www.linkedin.com/in/tshepo-tsilo" target="_blank">https://www.linkedin.com/in/tshepo-tsilo</a>
- Devchallenges.io - <a href="https://devchallenges.io/portfolio/CodeBase912" target="_blank">https://devchallenges.io/portfolio/CodeBase912</a>
