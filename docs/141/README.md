# Gnucash reports stopped working

There seems to be an issue with Nvidia GPU in flatpak version.
The workaround is

```bash
WEBKIT_DISABLE_COMPOSITING_MODE=1 flatpak run org.gnucash.GnuCash
```

<https://askubuntu.com/questions/1398945/why-have-my-gnucash-reports-stopped-working>
