
# Modification Notes

## Project Structure
[_config.yml](./_config.yml) contains base configurations.

`<head>...</head>` is populated by [./_includes/head](./_includes/head.liquid).

**Navigation Bar** is rendered by [./_includes/header.liquid](./_includes/header.liquid).

**About page** is rendered by [./_layouts/about.liquid](./_layouts/about.liquid).


**Footer** is rendered by [./_includes/footer.liquid](./_includes/footer.liquid).

### Pages
Pages are defined in [./_pages/](./_pages/)

Each page has a front matter:
```
---
nav: true # true to show the page on Nav Bar otherwise false
nav_order: 1 # specifies the order in which the page would appear in Nav Bar
...
---
```

### CSS

CSS files are in [./_sass](./_sass).

[./_sass/_base.scss](./_sass/_base.scss) contains base CSS.

[./_sass/_theme.scss](./_sass/_theme.scss) contains theme colors.

## Disabling Dark Mode
Setting `enable_darkmode` in [_config.yml](https://github.com/alshedivat/al-folio/blob/master/_config.yml#L436) to ` false`:
1. Disables Dark Mode.
2. Hides the Light/Dark Mode Toggle Button.

TODO: Modify code to enable Light Mode by default and keep the toggle button.

## Disable/Enable Search (Cmd + K)

Setting `search_enabled` in [_config.yml](https://github.com/alshedivat/al-folio/blob/master/_config.yml#L52) to `true`/`false` will enable/disable the search feature respectively.

## Updating Profile Pic

Uploaded `profile-cropped.jpeg` to [./assets/img/](https://github.com/aparajita-bose/aparajita-bose.github.io/tree/master/assets/img)

Changed `profile.image` to `profile-cropped.jpeg` in `about.md` [here](https://github.com/aparajita-bose/aparajita-bose.github.io/blob/master/_pages/about.md?plain=1#L9).

**Technical Details:** Profile Pic is generated [here](https://github.com/aparajita-bose/aparajita-bose.github.io/blob/master/_layouts/about.liquid#L21-L33) in `about.liquid`.

## Disable Latest Posts Section

Latest Posts section is generated in `about.liquid` [here](https://github.com/aparajita-bose/aparajita-bose.github.io/blob/master/_layouts/about.liquid#L51-L57).

Can be disabled by setting `latest_posts.enabled` to `false` in `_config.yml` [here](https://github.com/aparajita-bose/aparajita-bose.github.io/blob/master/_config.yml#L208).

## Disable News Section

News section is generated in `about.liquid` [here](https://github.com/aparajita-bose/aparajita-bose.github.io/blob/master/_layouts/about.liquid#L43-L49).

Can be disabled by setting `announcements.enabled` to `false` in `_config.yml` [here](https://github.com/aparajita-bose/aparajita-bose.github.io/blob/master/_config.yml#L203).

## Adding CV Icon

https://jpswalsh.github.io/academicons/