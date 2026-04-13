# ⌨️ xremap config – XVX SK-80 (Linux)

Configuração de **xremap** para o teclado **XVX SK-80**, corrigindo o comportamento das teclas de função (F1–F12) em ambientes Linux.

---

## 📌 Sobre

Alguns teclados como o XVX SK-80 (identificado no sistema como `"SONiX Gaming Keyboard"`) enviam **teclas multimídia por padrão** ao invés das teclas F1–F12.

Essa configuração faz o remapeamento correto para que:

* F1 → F12 funcionem como esperado
* Atalhos de desenvolvimento e sistema funcionem normalmente
* Experiência consistente em qualquer ambiente (Hyprland, GNOME, etc.)

---

## ⚙️ Configuração

```yaml
modmap:
  - name: F-keys remap
    device:
      only:
        - "SONiX Gaming Keyboard"
    remap:
      KEY_BRIGHTNESSDOWN: F1
      KEY_BRIGHTNESSUP:   F2
      KEY_SCALE:          F3
      KEY_DASHBOARD:      F4
      KEY_KBDILLUMDOWN:   F5
      KEY_KBDILLUMUP:     F6
      KEY_PREVIOUSSONG:   F7
      KEY_PLAYPAUSE:      F8
      KEY_NEXTSONG:       F9
      KEY_MUTE:           F10
      KEY_VOLUMEDOWN:     F11
      KEY_VOLUMEUP:       F12
```

---

## 🚀 Como usar

### 1. Instalar o xremap

Arch Linux:

```bash
sudo pacman -S xremap
```

Ou via cargo:

```bash
cargo install xremap --features wlroots
```

---

### 2. Salvar a configuração

```bash
~/.config/xremap/config.yml
```

---

### 3. Rodar o xremap

```bash
sudo xremap ~/.config/xremap/config.yml
```

> Pode precisar de permissões elevadas dependendo do ambiente.

---

## 🧠 Como funciona

O xremap intercepta os eventos do teclado e converte:

* Teclas multimídia → Teclas de função (F1–F12)

Isso resolve problemas como:

* IDEs não reconhecendo F-keys
* Jogos ignorando comandos
* Atalhos do sistema não funcionando corretamente

---

## 🛠️ Personalização

Para verificar o nome do seu teclado:

```bash
xremap --list-devices
```

E substitua `"SONiX Gaming Keyboard"` pelo nome correto, se necessário.

---

## 💡 Observações

* Funciona melhor em Wayland (wlroots / Hyprland)
* Em X11 pode exigir configurações extras
* Pode ser combinado com outras regras no xremap

