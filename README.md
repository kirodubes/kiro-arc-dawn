<p align="center">
  <img src="kiro.jpg" alt="Kiro" width="220" />
</p>

# kiro-arc-dawn

The **Arc Dawn** GTK theme family — three light/dark variants of the popular [Arc theme](https://github.com/horst3180/arc-theme), packaged for easy installation on Arch / Kiro. Part of the `~/EDU/` learning series.

## What's in this repo

Three theme variants ship under `usr/share/themes/`:

| Variant         | Tone                          | Use when                                |
|-----------------|-------------------------------|-----------------------------------------|
| `Arc-Dawn`      | Light with subtle warm tint   | Daytime use, bright workspaces          |
| `Arc-Dawn-Dark` | Dark window chrome, light app | Mixed-mode preference                   |
| `Arc-Dawn-Darker` | Fully dark                  | Low-light / OLED setups                 |

Each variant covers Cinnamon, GNOME Shell, GTK 2 / 3 / 4, Metacity, Openbox, Plank, Unity, Xfwm4, and (where applicable) Cinnamon and Plasma assets.

## Installation

### From `nemesis_repo` (recommended)

```ini
[nemesis_repo]
SigLevel = Never
Server = https://erikdubois.github.io/$repo/$arch
```

```bash
sudo pacman -Syu
sudo pacman -S kiro-arc-dawn
```

Themes are installed under `/usr/share/themes/Arc-Dawn*` and become selectable in any GTK-based theme switcher.

### Manual

```bash
git clone https://github.com/kirodubes/kiro-arc-dawn.git
cd kiro-arc-dawn
sudo cp -r usr/share/themes/. /usr/share/themes/
```

### Activate

GTK 3 / 4:

```bash
gsettings set org.gnome.desktop.interface gtk-theme "Arc-Dawn-Dark"
```

Or set via your DE's theme settings (Tweaks, KDE Appearance, XFCE Settings → Appearance, etc.).

## Websites

Information : https://erikdubois.be

## Social Media

Youtube : https://www.youtube.com/erikdubois

<!-- KIRO-FUNDING-FOOTER:START — managed by Kiro-HQ/cascade-readme-footer.sh -->
## Help fund Kiro

Everything I build here stays free and open — always. If Kiro or any of these
tools have ever saved you time or taught you something, a small monthly
contribution helps keep the work going. Donations target break-even, nothing
more — the core always stays free for everyone.

- GitHub Sponsors: https://github.com/sponsors/erikdubois
- Patreon: https://www.patreon.com/c/kiroproject
- YouTube memberships: https://www.youtube.com/@ErikDubois/join
- Ko-fi: https://ko-fi.com/erikdubois
- PayPal: https://www.paypal.me/erikdubois
<!-- KIRO-FUNDING-FOOTER:END -->

## License

See [LICENSE](./LICENSE).
