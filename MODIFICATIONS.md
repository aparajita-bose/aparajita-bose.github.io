
# Modification Notes

## Quickstart

```
docker compose pull
docker compose up
```

For more details, see: https://github.com/alshedivat/al-folio/blob/master/INSTALL.md#local-setup-using-docker-recommended

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

## Obfuscate Email

Email in social icons is added [here](https://github.com/aparajita-bose/aparajita-bose.github.io/blob/master/_includes/social.liquid#L15) and encoded with [jekyll-email-protect](https://github.com/vwochnik/jekyll-email-protect).

Alternative ways:  
* https://spencermortensen.com/articles/email-obfuscation/#text-display
* https://stackoverflow.com/a/11563565

<!-- Feel free to connect with me at: **aparajitabose.cs [at] gmail [dot] com** -->

## Publications

All publications are defined in [papers.bib](./_bibliography/papers.bib).

If you are adding new bibtext, check the following fields:
- Add `selected={true}` to be shown on website
- Add `url={...}` to make it clickable
- Add `inprogress={true}` if the paper needs to be shown under `Publication In-Progress` section

Publications on About page are defined in [about.liquid](https://github.com/aparajita-bose/aparajita-bose.github.io/blob/master/_layouts/about.liquid#L73-L84) and calls [publications_in_progress.liquid](https://github.com/aparajita-bose/aparajita-bose.github.io/blob/master/_includes/publications_in_progress.liquid) to render `Publications In-Progress` and [selected_papers.liquid](https://github.com/aparajita-bose/aparajita-bose.github.io/blob/master/_includes/selected_papers.liquid) to render `Publications` section.