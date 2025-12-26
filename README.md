# 🦁 Install Brave Browser on Fedora

Brave is not included in Fedora’s default repositories, so you must add Brave’s official repository before installing it. These steps follow Brave’s official installation instructions.

---

## 1. Add Brave’s signing key

```bash
sudo rpm --import https://brave.com/signing-keys/brave-core.asc
```

---

## 2. Add the Brave repository

```bash
sudo tee /etc/yum.repos.d/brave-browser.repo <<EOF
[brave-browser]
name=Brave Browser
baseurl=https://brave-browser-rpm-release.s3.brave.com/x86_64/
enabled=1
gpgcheck=1
gpgkey=https://brave.com/signing-keys/brave-core.asc
EOF
```

---

## 3. Install Brave

```bash
sudo dnf install brave-browser
```

---

## 4. Launch Brave

```bash
brave-browser
```

---

## Notes

- The package name is **brave-browser**, not `brave`.
- Fedora does not ship Brave due to packaging and licensing choices.
- Using Brave’s official repository ensures you always get the latest stable version.

---

## Optional: Enable DRM (Netflix, Disney+, etc.)

Brave may prompt you to enable Widevine when visiting DRM‑protected sites.  
If not, you can enable it manually:

**Settings → Extensions → Widevine → Enable**

---

## Optional: Hardware Acceleration

If video playback stutters, enable hardware acceleration:

**Settings → System → Use hardware acceleration when available**

---

## Optional: Set Brave as Default Browser

```bash
xdg-settings set default-web-browser brave-browser.desktop
```

---

Happy browsing!
