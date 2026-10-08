# Changelog

## 2026.10.08

### What Changed
- GTK4 apps no longer turn see-through or blank with an Arc-Dawn theme on GTK 4.24. Since gtk4 4.24.1, an app that
  changes the theme or dark mode while running lost the whole Arc stylesheet: ATT showed text over the wallpaper and
  Font Manager an empty white window. The GTK4 part of Arc-Dawn, Arc-Dawn-Dark and Arc-Dawn-Darker now ships as
  plain CSS files, which GTK always loads.

### Technical Details
- Each theme's `gtk-4.0/gtk.css` and `gtk-dark.css` were one-line `@import url("resource:///org/gnome/arc-theme/…")`
  into `gtk.gresource`. GTK 4.24.1 does not register that gresource on a runtime theme reload, so the import failed
  ("The resource at /org/gnome/arc-theme/gtk-main-dark.css does not exist") and nothing was styled. Choosing the
  theme at startup still worked, which is why most apps looked fine.
- The CSS each file imported was extracted with `gresource extract` into `gtk.css` / `gtk-dark.css`, and the 168
  images into `gtk-4.0/assets/`. The CSS already uses relative `url("assets/…")`, so no URL rewrite was needed.
  `gtk.gresource` is removed. GTK3, GTK2 and the other theme parts are unchanged.
- Tested with the repo themes linked into `~/.local/share/themes`: runtime switches to Arc-Dawn, Arc-Dawn-Dark and
  Arc-Dawn-Darker load without parser errors, and Font Manager renders fully themed.
- kiro-arc-themes-generator can also build Dawn and still produces the gresource layout; it needs the same
  post-processing step before it regenerates this package.

### Files Modified
- usr/share/themes/Arc-Dawn/gtk-4.0/ (gtk.css, gtk-dark.css, assets/ added, gtk.gresource removed)
- usr/share/themes/Arc-Dawn-Dark/gtk-4.0/ (same)
- usr/share/themes/Arc-Dawn-Darker/gtk-4.0/ (same)

## 2026.05.21

### What Changed
- Initial markdown scaffold added per the ecosystem MD-scaffold rule ([HQ/CLAUDE.md](/home/erik/Insync/Kiro/Kiro-HQ/CLAUDE.md#required-markdown-scaffold-every-repo)).
- Stubs created for `CHANGELOG.md`, `CLAUDE.md`, `IDEAS.md`, `TODO.md` (whichever were missing).
- README rewritten with real install/usage content (replaced earlier one-line stub) where applicable.

### Files Modified
- CHANGELOG.md (created)
- CLAUDE.md (created where missing)
- IDEAS.md (created where missing)
- TODO.md (created where missing)
- README.md (rewritten where it was a stub)
