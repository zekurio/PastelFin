# PastelFin Theme

PastelFin is a custom Jellyfin theme built on [KartoffelChipss' NeutralFin](https://github.com/KartoffelChipss/NeutralFin), which in turn builds on [lscambo13's ElegantFin](https://github.com/lscambo13/ElegantFin). It keeps the dark, low-contrast base and adds a pastel lavender accent, set in Google Sans.

The preview images also use the [Jellyfin Lucide](https://github.com/KartoffelChipss/Jellyfin-Lucide) theme for more modern icons.

For this theme to look best, we also recommend enabling backdrops in your Jellyfin settings.

![Movie Pahe Preview](./assets/pastelfin-movie.webp)

## 📦 Install

You can install this theme by pasting the following code into the custom CSS box:

```css
@import url('https://cdn.jsdelivr.net/gh/zekurio/PastelFin@main/theme/pastelfin-minified.css');
```

<details>
  <summary><strong>Detailed steps for server-side implementation (Theme is applied to everyone)</strong></summary>

1. Go to **Settings** → **Administration** tab.
2. Select the **General** tab from the sidebar.
3. Scroll to the **Branding** section.
4. Locate the **Custom CSS** field.
5. Paste your custom CSS into the box.
6. Click **Save** to apply the changes.

</details>

<details>
  <summary><strong>Detailed steps for client-side implementation (Theme is only applied to you)</strong></summary>

1. Go to **Settings** → **Display** tab.
2. Scroll down to find the **Custom CSS** field.
3. Paste your custom CSS into the box.
4. Click **Save** to apply the changes.

</details>

## 🎨 Customization

You can override the following variables in your custom CSS (below the `@import`) to customize the theme:

```css
:root {
    /* Use your instance's splashscreen as the login page background: */
    --loginPageBgUrl: url('/Branding/Splashscreen?format=webp&foregroundLayer=1&quality=33&width=3840&height=2160&blur=2');

    /* Change the login page heading text: */
    --loginPageText: 'Sign in to continue';

    /* Retint the accent. --accentColor carries text, icons, progress bars and
       focus rings; --accentColorStrong fills the surfaces that sit under light
       text (buttons, selected rows), so it should be the darker of the two: */
    --accentColor: #b39ddb;
    --accentColorStrong: #9273c9;
}
```

To go back to NeutralFin's fully neutral look, point both at a grey — for example
`--accentColor: rgb(130, 130, 130)` and `--accentColorStrong: rgb(100, 100, 100)`.

Two further dials, if the accent is stronger than you want:

```css
:root {
    /* Restore upstream's green play buttons: */
    --btnMiniPlayColor: rgb(41, 154, 93);
    --btnMiniPlayBorderColor: rgb(50, 167, 105);

    /* Untint the chrome back to flat grey: */
    --darkerGradientPoint: #131313;
    --lighterGradientPoint: #1e1e1e;
    --headerColor: rgba(40, 40, 40, 0.5);
    --drawerColor: rgba(40, 40, 40, 0.9);
    --borderColor: rgb(71, 71, 71);
    --selectorBackgroundColor: rgb(60, 60, 60);
}
```

## 🔄 Updating

jsDelivr caches each file at its edge for 12 hours, and browsers hold it for 7 days.
A `?v=` query string does **not** bust the jsDelivr cache — it only affects the browser,
since jsDelivr ignores the query string when computing its cache key. To roll out a
change, do both, in this order:

1. Purge the CDN edge first:
   ```bash
   curl "https://purge.jsdelivr.net/gh/zekurio/PastelFin@main/theme/pastelfin-minified.css"
   ```
2. Then bump the query string in your custom CSS box so every client refetches:
   ```css
   @import url('https://cdn.jsdelivr.net/gh/zekurio/PastelFin@main/theme/pastelfin-minified.css?v=2');
   ```

Bumping before purging just refetches the same stale bytes under a new URL.

## 👀 Previews

<details>
    <summary><strong>Movie Page Preview</strong></summary>

![Movie Page Preview 2](./assets/pastelfin-movie2.webp)

</details>

<details>
    <summary><strong>Home Page Preview</strong></summary>

![Home Page Preview](./assets/pastelfin-home.webp)

</details>

<details>
    <summary><strong>Movie List Page Preview</strong></summary>

![Movie List Page Preview](./assets/pastelfin-movies.webp)

</details>

## ⚖️ License and Credits

PastelFin is a modified version of [NeutralFin](https://github.com/KartoffelChipss/NeutralFin) by [KartoffelChipss](https://github.com/KartoffelChipss), which is itself a modified version of the [ElegantFin](https://github.com/lscambo13/ElegantFin) theme by [lscambo13](https://github.com/lscambo13), originally licensed under the [GNU General Public License v2.0](https://www.gnu.org/licenses/old-licenses/gpl-2.0.html).

### Modifications in PastelFin:

- Pastel lavender accent on top of the dark base
- Chrome greys tinted toward the accent hue (app bar, drawer, borders, selectors, page background)
- Play buttons carry the accent instead of upstream's green
- Google Sans as the UI font and Google Sans Code for monospace

### Modifications inherited from NeutralFin, by KartoffelChipss:

- Applied a neutral black and grey color scheme
- Fix media bar plugin container position
- Fix media bar buttons consistency
- Themed login page card (left blue by upstream)
- Minor CSS refinements

This project remains under the **GNU GPL-2.0 license**.  
You are free to use, modify, and redistribute it under the same terms.

> **Disclaimer:** This project is an independent work and is not affiliated with, endorsed by, or officially associated with the Jellyfin project or its developers.

> **Content Disclaimer:** Movie posters and media shown in the previews are for demonstration purposes only. All media content is the property of their respective copyright holders and is not included with this theme.
