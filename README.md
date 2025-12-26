# Install-Brave-on-Fedora

1.  Add Brave’s signing key
sudo rpm --import https://brave.com/signing-keys/brave-core.asc

2. Add the Brave repository
sudo tee /etc/yum.repos.d/brave-browser.repo <<EOF
[brave-browser]
name=Brave Browser
baseurl=https://brave-browser-rpm-release.s3.brave.com/x86_64/
enabled=1
gpgcheck=1
gpgkey=https://brave.com/signing-keys/brave-core.asc
EOF

3. Install Brave
sudo dnf install brave-browser

Test it
brave-browser
