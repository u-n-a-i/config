<div align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="./img/config-header-oscuro.avif">
    <source media="(prefers-color-scheme: light)" srcset="./img/config-header-claro.avif">
    <img alt="config header" src="./img/config-header-oscuro.avif" width="100%">
  </picture>
</div>

<br/>

<p align="center">
  <img src="https://img.shields.io/github/last-commit/u-n-a-i/youtube-clean?style=flat-pill&label=%C3%9Altimo%20commit&color=0078D4" alt="Último commit"/>
  <img src="https://img.shields.io/badge/Licencia-WTFPL-800020?style=flat-pill" alt="Licencia: WTFPL"/>
</p>


## Windows + Debian (WSL)

Checklist para reconstruir mi entorno de trabajo híbrido:
herramientas nativas en Windows 11 y toolchain en Debian vía WSL2.

## 0. Base

- [ ] Windows actualizado
- [ ] WSL2 instalado y actualizado (`wsl --update`)
- [ ] Debian instalado como distro WSL (`wsl --install -d Debian`)
- [ ] Usuario por defecto configurado en WSL
- [ ] Terminal (Windows Terminal) + perfil Debian

## 1. Windows (nativo)

- [ ] Navegadores: [Firefox](https://www.firefox.com/es-ES/) / [LibreWolf](https://librewolf.net/) / [Brave](https://brave.com/es/)
- [ ] [VS Code (con extensión WSL + Perfiles por lenguaje/entorno)](https://code.visualstudio.com/)
- [ ] [Obsidian](https://obsidian.md/)
- [ ] Git for Windows (con Git Credential Manager) | Opcional
- [ ] [Beekeeper Studio](https://www.beekeeperstudio.io/)
- [ ] [Bruno](https://www.usebruno.com/)


## 2. Debian (WSL)

- [ ] `apt update && apt upgrade`
- [ ] Paquetes básicos (`curl`, `git`, `build-essential`, `unzip`, `zsh`)
- [ ] Fuentes (Console Code para terminal)
- [ ] DNS / VPN (según cómo los gestiones: Windows o WSL)
- [ ] Git (`user.name`, `user.email`, rama principal, SSH)
  - [ ] sudo apt install git
  - [ ] git config --global user.name "Tu Nombre"
  - [ ] git config --global user.email "email noreply de GitHub"
  - [ ] git config --global init.defaultBranch main
  - [ ] Configurar SSH
- [ ] [Java](https://adoptium.net/es/installation/linux#_deb_installation_on_debian_or_ubuntu) + [Maven](https://maven.apache.org/install.html)
- [ ] [Node.js (nvm + pnpm)](https://nodejs.org/es/download)
- [ ] [Python (pyenv o uv)](https://docs.python.org/3/using/unix.html)
- [ ] [Docker (Docker Desktop con integración WSL, o Docker Engine dentro de WSL)](https://docs.docker.com/engine/install/debian/)
- [ ] [OpenCode](https://opencode.ai/es) | [Codex](https://openai.com/es-ES/codex/) | [Claude Code](https://code.claude.com/docs/en/quickstart)

## 3. Integración Windows ↔ WSL

- [ ] Rutas: usar `/mnt/c/...` solo cuando haga falta (evitar trabajar ahí por rendimiento)
- [ ] SSH agent compartido (Windows ssh-agent + `SSH_AUTH_SOCK` en WSL, o `keychain`)
- [ ] Git credential manager compartido
- [ ] VS Code: abrir carpetas WSL con `code .` desde WSL
- [ ] Docker: decidir Docker Desktop vs Docker Engine en WSL (no ambos)
- [ ] Copiar/pegar y portapapeles entre Windows y WSL
- [ ] Backup de dotfiles (`.zshrc`, `.gitconfig`, `settings.json` de VS Code)

## 4. Verificación

- [ ] `wsl --list --verbose` muestra Debian en VERSION 2
- [ ] `code --version` funciona desde WSL
- [ ] `git config --global --list` correcto
- [ ] `ssh -T git@github.com` autentica
- [ ] `node -v`, `pnpm -v`, `java -version`, `mvn -v`, `python --version`, `docker --version`