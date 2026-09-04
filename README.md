<p align="center">
  <img src="./assets/pastelfin-movie.webp" alt="PastelFin" width="800" />
</p>

<hr />

A Jellyfin theme that combines the layout of
[NeutralFin](https://github.com/KartoffelChipss/NeutralFin) with the
[Catppuccin Frappé](https://github.com/catppuccin/jellyfin) palette, a blue
accent, and Google Sans. NeutralFin itself builds on
[ElegantFin](https://github.com/lscambo13/ElegantFin).

Looks best with backdrops enabled in your Jellyfin settings. The previews also
use [Jellyfin Lucide](https://github.com/KartoffelChipss/Jellyfin-Lucide) for
its icons.

### Install

Paste this into a **Custom CSS** field:

```css
@import url('https://cdn.jsdelivr.net/gh/zekurio/PastelFin@main/theme/pastelfin-minified.css');
```

Server-wide, for every user: **Settings** → **Administration** → **General** →
**Branding** → **Custom CSS**, then save. For your account only: **Settings** →
**Display** → **Custom CSS**, then save.

### Customization

Override any variable below the `@import`. The theme exposes every Frappé
palette color by name. `--accentColor` controls links, progress bars, focus
rings, selected controls, and play buttons. Blue is the default.

```css
:root {
    /* Any Frappé accent works, such as var(--mauve) or var(--green) */
    --accentColor: var(--blue);
    --accentForegroundColor: var(--base);

    /* Use your instance's splashscreen as the login background */
    --loginPageBgUrl: url('/Branding/Splashscreen?format=webp&foregroundLayer=1&quality=33&width=3840&height=2160&blur=2');
    --loginPageText: 'Sign in to continue';
    --loginPageBrandText: 'My Jellyfin';
}
```

### Updating

jsDelivr caches the file at its edge for 12 hours and browsers hold it for 7
days. A `?v=` query string does **not** bust the CDN cache, only the browser
one. Purge first, then bump:

```bash
curl "https://purge.jsdelivr.net/gh/zekurio/PastelFin@main/theme/pastelfin-minified.css"
```

```css
@import url('https://cdn.jsdelivr.net/gh/zekurio/PastelFin@main/theme/pastelfin-minified.css?v=2');
```

Bumping before purging just refetches the same stale bytes under a new URL.

### Previews

<details>
  <summary><strong>Home</strong></summary>

![Home](./assets/pastelfin-home.webp)

</details>

<details>
  <summary><strong>Movie</strong></summary>

![Movie](./assets/pastelfin-movie2.webp)

</details>

<details>
  <summary><strong>Movie list</strong></summary>

![Movie list](./assets/pastelfin-movies.webp)

</details>

<details>
  <summary><strong>Dashboard</strong></summary>

![Dashboard](./assets/pastelfin-dashboard.webp)

</details>

### Credits

PastelFin applies Catppuccin Frappé colors to NeutralFin's layout, uses blue as
the default accent, and swaps the type stack to Google Sans and Google Sans
Code. The palette follows the recolor-only
[Catppuccin Jellyfin theme](https://github.com/catppuccin/jellyfin).

NeutralFin by [KartoffelChipss](https://github.com/KartoffelChipss) contributed
the base layout, themed login card, media bar fixes, and other CSS refinements
on top of ElegantFin by [lscambo13](https://github.com/lscambo13).

Not affiliated with or endorsed by the Jellyfin project. Media shown in the
previews belongs to its respective copyright holders and ships with nothing
here.

### License

[GPL-2.0](LICENSE)
