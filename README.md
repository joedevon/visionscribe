# VisionScribe

Accessible alt text and image description generator for Claude.

Upload any image and get accurate, context-aware alt text and descriptions, written with the best advice of accessibility experts. Ready to paste into your code, CMS, or documents.

## What It Does

- **Classifies images** as decorative, functional, informative, complex, or composite before writing anything
- **Produces layered output** for complex images: brief alt text + extended description + alternate approaches
- **Handles data-dense content** by summarizing patterns instead of transcribing every value
- **Names the people in a photo** from the caption, the surrounding text, or what you tell it, so screen reader users get the same information sighted users do. It flags a missing name instead of dropping it
- **Adapts to context** depending on platform and purpose
- **Provides copy-ready output** in fenced code blocks, ready to paste
- **Suggests implementation strategies** like `aria-describedby`, `<figcaption>`, or linked data tables when appropriate

## Installation

### Claude Code

Install VisionScribe as a plugin. In a Claude Code session, run:

```
/plugin install visionscribe --marketplace joedevon/visionscribe
```

That one-step form needs Claude Code 2.1.275 or later. On an older version, add the marketplace first:

```
/plugin marketplace add joedevon/visionscribe
/plugin install visionscribe@visionscribe
```

To get a newer version later, run `/plugin marketplace update visionscribe`.

You can also copy the skill folder into your personal skills directory instead:

```bash
cp -r visionscribe/ ~/.claude/skills/visionscribe/
```

### Claude Desktop

1. Open **Customize** (left sidebar)
2. Select **Skills**
3. Click **+**
4. Paste `joedevon/visionscribe`
5. Click **Sync**, then **Install**

### claude.ai (web)

To install it as a plugin, go to **Customize > Plugins**, choose **Add**, then **Add marketplace**, and enter `joedevon/visionscribe`.

To upload it as a skill instead:

1. Click the green **Code** button on this repo and choose **Download ZIP**
2. On [claude.ai](https://claude.ai), go to **Customize > Skills**
3. Click **+** and upload the ZIP

## Usage

Upload any image to Claude and say:

- `/visionscribe`
- "Write alt text for this image"
- "Describe this image for accessibility"
- "What alt text should I use?"

If another skill also uses the name `visionscribe`, call the plugin by its full name, `/visionscribe:visionscribe`.

## How It Works

VisionScribe is a structured prompt that teaches Claude a systematic approach to writing alt text. It draws on WCAG, the W3C Alt Text Decision Tree, and real-world screen reader behavior to produce descriptions that prioritize meaning and purpose over visual inventory.

## Accessibility

Read [ACCESSIBILITY.md](ACCESSIBILITY.md) for what this project aims for. VisionScribe is provided as is, without support.

## License

[MIT](LICENSE)

## Author

[Joe Devon](https://www.linkedin.com/in/joedevon/) - Co-founder of [Global Accessibility Awareness Day (GAAD)](https://accessibility.day) and Chair of the [GAAD Foundation](https://gaad.foundation).
