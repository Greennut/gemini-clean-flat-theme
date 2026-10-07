# Gemini Clean Flat UI

[![Install directly with Stylus](https://img.shields.io/badge/Install%20with-Stylus-1185fe?style=for-the-badge&logo=stylus)](https://raw.githubusercontent.com/Greennut/gemini-clean-flat-theme/main/gemini-clean-flat.user.css)

A de-bloated, flat user style for `gemini.google.com`. Strips away excessive Material elevation shadows and aggressive blur effects, restoring structured input boxes, muted query bubbles, and clean code blocks.

面向 `gemini.google.com` 的去装饰化纯平风格用户样式。剥除原生 Material 阴影与模糊光晕，重置输入框、提问气泡与代码块排版。

---

## Features / 设计特性

* **Input Box**: Pure white background, subtle 1px border, zero elevation shadows, and a clean monochrome action button.
* **Message Bubbles**: Muted cool-tinted fill (`#EDF2FA`) without card outlines.
* **Syntax Highlighting**: Soft color palette (purple keywords, light blue functions, muted green strings, slate operators).
* **Code Container**: Clean card layout with `#F1F3F9` background fill and 20px rounded corners.

---

## Installation / 安装使用

### Option 1: One-Click Install (Recommended / 推荐)
Click the badge above if you already have the **Stylus** extension installed.

若已安装 **Stylus** 扩展，直接点击页面顶部蓝色的 **Install with Stylus** 徽标即可自动触发安装。

### Option 2: Manual / 手动安装
1. Install a userstyle manager extension (such as **Stylus**).
2. Create a new style and paste the raw content of `gemini-clean-flat.user.css`.
3. Set the target domain to `gemini.google.com`.

---

## Known Constraints & Help Wanted / 待改进的技术卡点

Contributions and pull requests are welcome. Currently, the code block container exhibits the following DOM layout constraints:

1. **Header Border Edge Alignment**:
   * The `.code-block-decoration` header container is constrained by internal host container paddings. The separator line (`border-bottom: 2px solid #FFFFFF`) currently spans the inner block width rather than extending fully to the 20px card boundaries.
   * Attempting to force full-width stretch via negative margins or absolute positioning easily triggers box-sizing layout shifts across different viewport widths.
2. **Layer Compositing in Mobile WebKit/Blink**:
   * Internal `<pre>` containers may occasionally render a transparent layer depending on shadow DOM encapsulation, exposing the white underlying canvas.

If you are familiar with Angular Web Components and layout tree inheritance, feel free to submit a PR to refine the container inheritance rules.
<img width="1880" height="2644" alt="27114" src="https://github.com/user-attachments/assets/10d203ef-4ab8-4891-a162-a6a81c826147" />
<img width="1880" height="2659" alt="27116" src="https://github.com/user-attachments/assets/6264a311-af19-426d-a559-3e3aff988619" />
