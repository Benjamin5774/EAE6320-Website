# EAE 6320 assignment site

Static site, no build step. Live at https://game6320-website.netlify.app/

```
index.html            list of assignments
assets/style.css      the only stylesheet
assignment01/         write-up page, screenshots, game zips
```

## Adding an assignment

1. Make `assignment02/` with an `index.html` (copy `assignment01/index.html` and edit), put screenshots in `assignment02/images/`.
2. Copy the game zip (contents of `$(GameInstallDir)` for the Release x64 build, without `eae6320.log` and without an extra root folder) next to that `index.html`.
3. Add a new `<li>` to the list in `index.html`.

## Deploying

Netlify: open the site's Deploys page and drag this whole folder onto it (or `netlify deploy --prod --dir=.` if the CLI is installed).

Links to give the instructor:

- write-up: `https://game6320-website.netlify.app/assignment01/`
- game zip: `https://game6320-website.netlify.app/assignment01/YangBenjamin_Assignment01_Direct3D_x64.zip`

Open the zip link in a private window once to check that one click downloads it.
