# Course website (static HTML)

This folder is a plain static site for the EAE 6320 assignment write-ups. No build step, no
JavaScript framework: just HTML, one CSS file, images and ZIP files.

```
Web/
  index.html                 home page - list of assignments
  assets/style.css           the only stylesheet
  assignment01/
    index.html               Assignment 01 write-up
    images/                  screenshots used by the write-up
    YangBenjamin_Assignment01_Direct3D_x64.zip   one-click download of the game
    YangBenjamin_Assignment01_OpenGL_x86.zip
  _template/index.html       copy this for each new assignment
```

## Adding a new assignment

1. Copy `_template/` to `assignment02/` (etc.), edit the text, put screenshots in `assignment02/images/`.
2. Copy the game ZIP (contents of `$(GameInstallDir)` for the **Release x64** build, without `eae6320.log`,
   without an extra root folder) next to the new `index.html`.
3. In `index.html` (the home page) copy the commented-out `<li>` block, fill it in, and remove the `todo` class.

## Publishing on the CADE web server (University of Utah)

CADE gives every account a personal site at `https://home.cade.utah.edu/~<uNID>/` (some setups
use `https://www.eng.utah.edu/~<uNID>/`; the instructions page linked from the assignment says
which one applies). The site is served from `~/public_html` on the CADE Linux machines.

From PowerShell on your PC (replace `u1234567` with your uNID):

```bash
scp -r "C:\Users\13441\OneDrive\Desktop\eng2\A1_new\Web\*" u1234567@lab1-1.eng.utah.edu:~/public_html/
```

Then, once, make the files readable by the web server:

```bash
ssh u1234567@lab1-1.eng.utah.edu "chmod 711 ~ && chmod -R a+rX ~/public_html"
```

Any `lab1-*.eng.utah.edu` machine works. After that, the direct links to use in Canvas are:

* write-up: `https://home.cade.utah.edu/~u1234567/assignment01/index.html`
* game ZIP:  `https://home.cade.utah.edu/~u1234567/assignment01/YangBenjamin_Assignment01_Direct3D_x64.zip`

Open the ZIP link once in a private browser window to confirm that a single click downloads the file.

## Previewing locally

Just double-click `index.html`. Everything uses relative links, so it works from the file system
and from the web server alike.
