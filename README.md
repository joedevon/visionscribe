# VisionScribe

Write alt text and image descriptions with Claude or Codex.

Attach an image and tell VisionScribe where you plan to use it. It drafts alt text you can paste into your code, CMS, or documents. For charts and other complex images, it also writes an extended description.

## What it does

- Classifies the image before writing. Decorative images may need empty alt text; buttons and links need text that explains their function.
- Gives complex images brief alt text, an extended description, and alternatives for different uses.
- Summarizes patterns in charts and dashboards instead of listing every value.
- Names people using captions, surrounding text, visible text, file names, or information you provide. It flags missing names and asks you to fill them in.
- Adjusts descriptions for the audience and purpose.
- Puts each text option in a separate code block for copying.
- Suggests captions, linked data tables, or `aria-describedby` when they would help.

## Installation

### Codex

From the repository root, copy the skill into your personal skills directory:

```bash
mkdir -p ~/.agents/skills
cp -R visionscribe ~/.agents/skills/
```

Codex loads skills from `~/.agents/skills`. If VisionScribe does not appear in `/skills`, restart Codex. See the [official Codex skills documentation](https://learn.chatgpt.com/docs/build-skills).

Attach an image and include `$visionscribe` in your prompt. To try the included chart, run this from the repository root:

```bash
codex --image tests/fixtures/library-visitors-chart.png -- '$visionscribe Write alt text for this image.'
```

For a non-interactive run:

```bash
codex exec --sandbox read-only --image tests/fixtures/library-visitors-chart.png -- '$visionscribe Write alt text for this image.'
```

Use `--` to separate the prompt from the image paths, and single quotes so the shell passes `$visionscribe` to Codex unchanged. Replace the chart path with your own image path for other images.

### Pi

Pi discovers skills in `~/.agents/skills/`, the same directory Codex uses. From the repository root:

```bash
mkdir -p ~/.agents/skills
cp -R visionscribe ~/.agents/skills/
```

Attach an image with `@path` and ask for alt text; Pi loads VisionScribe when the request matches. To try the included chart from the repository root:

```bash
pi --print @tests/fixtures/library-visitors-chart.png 'Write alt text for this image.'
```

To force the skill, prefix the prompt with `/skill:visionscribe`. In the interactive terminal, attach an image by typing `@path`, pasting, or dragging it in. VisionScribe needs a model that accepts images, so check the `images` column in `pi --list-models` and choose a model marked `yes`.

### Claude Code

Install VisionScribe as a plugin. In a Claude Code session, run:

```
/plugin install visionscribe --marketplace joedevon/visionscribe
```

This command needs Claude Code 2.1.275 or later. On an older version, add the marketplace first:

```
/plugin marketplace add joedevon/visionscribe
/plugin install visionscribe@visionscribe
```

To update the plugin later, run `/plugin marketplace update visionscribe`.

You can also install the skill by copying its folder into your personal skills directory:

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

1. Click the green **Code** button on this repository and choose **Download ZIP**
2. On [claude.ai](https://claude.ai), go to **Customize > Skills**
3. Click **+** and upload the ZIP

## Usage

In Codex, attach an image and ask `$visionscribe Write alt text for this image.` You can also ask for alt text without naming the skill; Codex selects skills based on their descriptions.

In Claude, upload any image and say:

- `/visionscribe`
- "Write alt text for this image"
- "Describe this image for accessibility"
- "What alt text should I use?"

In Pi, attach an image with `@path`, paste, or drag it in, and ask for alt text. Pi loads VisionScribe when the request matches; force it with `/skill:visionscribe`.

If another skill also uses the name `visionscribe`, call the plugin by its full name, `/visionscribe:visionscribe`.

## How it works

VisionScribe is a set of instructions in [SKILL.md](visionscribe/SKILL.md). It tells the assistant to consider an image's purpose, choose what a reader needs to know, and write a description that fits the context.

The guidance draws on WCAG, the W3C Alt Text Decision Tree, and how people use screen readers. It currently has no bibliography or citations for individual rules.

## Accessibility

Read [ACCESSIBILITY.md](ACCESSIBILITY.md) for the project's accessibility goals and limits. VisionScribe is provided as is, without support.

## License

[MIT](LICENSE)

## Author

[Joe Devon](https://www.linkedin.com/in/joedevon/) co-founded [Global Accessibility Awareness Day](https://accessibility.day) and chairs the [GAAD Foundation](https://gaad.foundation).
