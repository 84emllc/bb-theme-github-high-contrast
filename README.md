# bb-theme-github-high-contrast

A custom theme for bb based on the GitHub high contrast palette, with color-coded sidebar thread indicators.

## What it does

- Sets the bb palette (canvas, ink, primary, semantic colors) for light and dark mode.
- Uses the `github-light-high-contrast` and `github-dark-high-contrast` code themes for diffs and file previews.
- Gives every sidebar thread indicator its own color. Stock bb renders most of them in muted grey.
- Removes the opacity mask from animated indicators so they always render at full color.
- Enlarges the unread-success dot from 5px to 8px and thickens the working spinner stroke from 1.5 to 2.5.

## Indicator colors

`--primary` and every indicator color measure at least 11:1 contrast against the canvas (`#ffffff` light, `#000000` dark), computed with the WCAG 2.x relative luminance formula. Other palette tokens are not held to that floor.

| State | Light | Dark |
|---|---|---|
| Thread failed, queued message failed | `#7a0d18` | `#ffa4a2` |
| Needs user input | `#573400` | `#f0b72f` |
| Message waiting to send | `#642b00` | `#ffa95c` |
| Thread working | `#023787` | `#84c1ff` |
| Workflow, background agent, background command | `#4a218e` | `#d3acff` |
| Plan mode, goal | `#044343` | `#39d0d0` |
| Unread thread succeeded | `#034619` | `#2cd854` |
| Unsubmitted draft | foreground | foreground |

The colors live in the `--ind-*` custom properties in `theme.css`.

## Install

1. Run `bb theme dir` to print the custom theme directory.
2. Clone this repo into that directory as `github-high-contrast`:

   ```bash
   git clone git@github.com:84emllc/bb-theme-github-high-contrast.git "$(bb theme dir)/github-high-contrast"
   ```

3. Activate it:

   ```bash
   bb theme set github-high-contrast
   ```

After editing `theme.css`, run `bb theme set github-high-contrast` again to re-apply.

## Known limitations

- The indicator rules select on bb's internal `aria-label` strings (for example `Thread needs user input`). A bb update that renames those labels will silently drop the colors until the selectors are updated.
- At 11:1 on a white canvas, the light mode indicator colors are all close to black, so hues are harder to tell apart than in dark mode. Icon shape still distinguishes the states.
- Contrast is measured against the plain canvas. A selected sidebar row carries a primary tint, so contrast there is lower.
- Animated indicators no longer shimmer, because the shine effect is an opacity mask. The working spinner still rotates.
- An idle draft icon can render without an `aria-label`, in which case it keeps the stock color.
