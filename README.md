![hacs_badge](https://img.shields.io/badge/HACS-Custom-orange.svg)
# SmartHRT Card

**Read this in other languages:** [Français](README.fr.md) | [English](README.md)

---

🙏 **Acknowledgments to @CorentinBarban**: author of the [SmartHRT fork](https://github.com/CorentinBarban/SmartHRT) for which this card is designed.

A custom Lovelace card for Home Assistant, specifically designed to control and monitor heating recovery (boost) cycles.

🛠️ **Prerequisite**: Install [SmartHRT](https://github.com/CorentinBarban/SmartHRT) first.

## 📸 Screenshots

| Main Interface | Expert Mode (RCth Analysis) |
| -------- | -------- |
| ![Main Interface](images/smarthrt_front.jpg) | ![Expert Mode](images/smarthrt_back.jpg) |

## ✨ Features

* **Intuitive Control**: Touch-friendly arc interface to adjust the target temperature setpoint.
* **Safety Lock**: Prevents accidental changes on the touchscreen.
* **Status Display**: Clear visualization of current state (heating, recovery, lag, etc.) and time remaining until the next recovery cycle.
* **Integrated Expert Mode**: Native generation of a scatter plot to analyze RCth history vs. wind speed, directly on the card.
* **Dark/Light Mode**: Automatically adapts to your Home Assistant dashboard theme.

## 📥 Installation via HACS

This card is designed to be easily installed via [![hacs_badge](https://img.shields.io/badge/HACS-Custom-orange.svg)](https://github.com/hacs/integration).

1. Open **HACS** in Home Assistant.
2. Go to the top-right menu (three dots) and select **Custom repositories**.
3. Add the URL of this repository: `https://github.com/ebozonne/smartHRT-card`
4. Choose the category **Lovelace** (or Dashboard) and click **Add**.
5. Search for "SmartHRT Card" in HACS and click **Download**.
6. Refresh your browser when prompted by HACS.

> [!IMPORTANT]
> If you install the card **manually** (copying to `/config/www/`), make sure to place the **`translations/`** folder next to `smarthrt-card.js`. Without this folder, entity keys for different languages will not load.

### Changelog

**1.0.2** — Automatic selection of entity suffixes based on the Home Assistant interface language (`translations/*.json` files, fallback to English). Machine state labels use SmartHRT's built-in translations by language.

## ⚙️ Configuration (YAML)

Once installed, you can add the card to your dashboard using the manual (YAML) editor.

**Example:**
```yaml
grid_options:
  columns: 6
type: custom:smarthrt-card
prefix: bathroom
name: 🛁 Bathroom
```

### Available YAML Parameters:

| Parameter | Example | Description |
| -------- | -------- | -------- |
| `prefix:` | `living_room` | **REQUIRED**: The SmartHRT instance name (e.g., salon, bedroom) |
| `name:` | `My Living Room` | **OPTIONAL**: The title displayed on the card |
| `min_temp:` | `13` | **OPTIONAL**: Minimum temperature on the arc (Default: 13) |
| `max_temp:` | `26` | **OPTIONAL**: Maximum temperature on the arc (Default: 26) |
