# VisionScribe

Accessible alt text and image description generator for Claude.

Upload any image and get accurate, context-aware alt text and descriptions that follow WCAG best practices. Ready to paste into your code, CMS, or documents.

## What It Does

- **Classifies images** as decorative, functional, informative, complex, or composite before writing anything
- **Produces layered output** for complex images: brief alt text + extended description + alternate approaches
- **Handles data-dense content** by summarizing patterns instead of transcribing every value
- **Identifies public figures by name** so screen reader users get the same information sighted users do
- **Adapts to context** depending on platform and purpose
- **Provides copy-ready output** in fenced code blocks, ready to paste
- **Suggests implementation strategies** like `aria-describedby`, `<figcaption>`, or linked data tables when appropriate

## Installation

### Claude Desktop

1. Open **Customize** (left sidebar)
2. Select **Skills**
3. Click **+**
4. Paste `joedevon/visionscribe`
5. Click **Sync**, then **Install**

### claude.ai (web)

1. Click the green **Code** button on this repo and choose **Download ZIP**
2. On [claude.ai](https://claude.ai), go to **Customize > Skills**
3. Click **+** and upload the ZIP

### Claude Code

Copy the skill folder into your skills directory:

```bash
cp -r visionscribe/ ~/.claude/skills/visionscribe/
```

## Usage

Upload any image to Claude and say:

- `/visionscribe`
- "Write alt text for this image"
- "Describe this image for accessibility"
- "What alt text should I use?"

## How It Works

VisionScribe is a structured prompt that teaches Claude a systematic approach to writing alt text. It draws on WCAG, the W3C Alt Text Decision Tree, and real-world screen reader behavior to produce descriptions that prioritize meaning and purpose over visual inventory.

## Accessibility

Read [ACCESSIBILITY.md](ACCESSIBILITY.md) for what this project aims for and how to report a problem with VisionScribe's output or documentation.

## License

MIT

## Author

[Joe Devon](https://www.linkedin.com/in/joedevon/) - Co-founder of [Global Accessibility Awareness Day (GAAD)](https://accessibility.day) and Chair of the [GAAD Foundation](https://gaad.foundation).
