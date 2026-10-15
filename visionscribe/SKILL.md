---
name: visionscribe
description: >
  Generate accessible alt text and image descriptions for uploaded images.
  Use this skill whenever a user uploads an image and asks for alt text,
  image descriptions, accessibility text, or any description intended for
  screen reader users, assistive technology, or WCAG compliance. Also
  trigger when the user asks to make an image accessible, wants to know
  what alt text to use, or uploads an image and asks what it shows in an
  accessibility context. Covers all image types: photos, charts, graphs,
  screenshots, icons, logos, memes, maps, infographics, art, diagrams,
  dashboards, and group photos.
license: MIT
---

# VisionScribe — Accessible Alt Text & Image Description Generator

Generate alt text and image descriptions that are accurate, context-aware,
and ready to paste. The goal is to give non-visual readers the information
they need to understand what an image contributes — nothing more, nothing
less.

## Deciding What Kind of Image It Is

Before writing anything, classify the image:

### Decorative
The image adds visual appeal but no information. Apply the litmus test: if
the image disappeared, would a reader miss something essential? If not,
recommend `alt=""`. Present it as a copyable value:

```
alt=""
```

### Functional
The image is a link or button. Describe the function or destination, not
the appearance. "Search" is correct; "magnifying glass icon" is not.

### Contains Text
Include visible text verbatim when it carries meaning that isn't already
conveyed in surrounding content. If the text is fully redundant with a
caption or adjacent copy, note that and recommend `alt=""`.

When the image contains more text than can reasonably be included in alt
text — dense data tables, multi-panel dashboards, long paragraphs — do
not attempt a full transcription. Summarize the key message instead, and
offer alternate approaches (see below) so the user can choose the
emphasis that fits their context.

### Informative
Describe the meaning and purpose in context, not a literal inventory of
visual elements.

### Complex
Charts, graphs, infographics, maps, data visualizations, and diagrams
need layered treatment:
- Brief alt text with the key takeaway.
- Extended description with important data, labels, structure, or
  relationships.
- When relevant, suggest `<figcaption>`, `aria-describedby`, or a linked
  data table as implementation approaches.

### Composite
Dashboards, multi-panel views, and images that embed many charts, tables,
or data points in a single frame are a special case. Alt text and extended
descriptions cannot make these fully accessible — a screen reader user
would have to sit through a long linear reading with no way to scan, skip,
or interact.

For composite images:
- The brief alt text should name the tool, state the scope, and identify
  the high-level structure (e.g., "five domain columns").
- The extended description should tell the story, not transcribe the data.
  Focus on the 2–4 most important patterns, trends, or outliers — the
  things a person looking at this image would take away. Resist the urge
  to list every metric. If specific numbers matter, they belong in a data
  table, not in prose.
- Always include alternate approaches (see below), because the right
  emphasis depends heavily on how the image is being used.

---

## Writing the Alt Text

### Structure
- Lead with the most important information.
- Emphasize purpose before detail.
- Use spatial order when it helps orientation.
- End alt text with a period.

### Length
- **Simple images:** 1 concise sentence, roughly 15–25 words.
- **Moderate images:** 1–2 sentences.
- **Complex images:** brief alt text plus a separate extended description.
- **Extended descriptions** should stay focused. A few sentences covering
  structure, key takeaways, and notable outliers — not a data dump. If
  you find yourself transcribing every value, stop. Summarize the pattern
  instead, and recommend a data table for the specifics.

### Include
- Who or what is shown.
- What is happening.
- Why it matters in context.
- Visible text, transcribed exactly when relevant.
- Colors, materials, layout, labels, trends, or relationships — but only
  when they carry meaning.

### Avoid
- "Image of," "photo of," "picture of," "graphic of."
- Repeating text already present nearby.
- SEO keywords.
- Vague labels that add no meaning.
- Subjective interpretation unless it serves the purpose.
- Jargon without explanation.
- Irrelevant detail.
- Exhaustive transcription of data-dense content. Summarize patterns;
  suggest structured alternatives for the raw data.

---

## Describing People

- Use specific age terms when relevant: baby, toddler, child, teen, young
  adult, adult, older adult.
- Prioritize actions over appearance unless appearance is the point.
- Mention visible assistive devices or physical characteristics only when
  relevant to context.
- **Identify recognizable public figures by name.** People who rely on alt
  text deserve the same information sighted users get instantly. If a news
  photo shows a senator, the alt text should name the senator. Withholding
  identifiable information about public figures creates an accessibility
  gap — sighted readers get it for free; non-visual readers should too.
  If identification is uncertain, say so (e.g., "a person who appears to
  be [Name]") rather than omitting the name entirely.

---

## Image Type Specifics

**Photographs:** Describe subject, action, setting, and mood when relevant.

**Charts and graphs:** Name the chart type, state the variables, summarize
the main trend, and include key data points or outliers in the extended
description.

**Screenshots:** Focus on what the screenshot demonstrates, not every UI
element. Transcribe key text and describe the relevant state or
interaction.

**Dashboards and multi-panel views:** See the Composite classification
above. Name the product, describe the organizational structure, and
summarize the key takeaways narratively. Do not walk through every widget.

**Art and illustrations:** Describe style only when relevant, then subject,
composition, and notable visual elements.

**Logos:** Use the organization or brand name unless the design itself is
being discussed.

**Memes:** Describe the format, transcribe all visible text exactly, and
briefly explain the visual context so the humor or message lands.

**Icons:** If functional, describe the function. If decorative, recommend
`alt=""`.

**Maps:** State the area shown, explain what the map communicates, and
summarize patterns for data maps.

**Group photos and collages:** State the number of people or images when
useful, describe the overall purpose, and highlight key subjects.

---

## Tailoring to Context

The right alt text depends on where the image lives. When the user
specifies a platform or purpose, adjust emphasis accordingly:

- **Social media:** Concise, focused on the key message.
- **Educational:** Include labels, relationships, sequence, and
  lesson-relevant details.
- **E-commerce:** Highlight product features, colors, materials, scale,
  visible details, and how the product appears in use.
- **News and journalism:** Objective and factual. Describe what is
  happening and who is involved. Name identifiable individuals.
- **Museum and gallery:** Describe medium, style, composition. Use rich
  sensory language. Note artist and title if known.
- **Documentation and technical:** Focus on the state, flow, step,
  architecture, or outcome the reader needs.

When the user does not specify context, default to general-purpose
informative alt text. If context would materially change the emphasis,
provide one recommended version and offer alternate approaches.

---

## Output Format

Every copy-ready text option goes in its own fenced code block using
plain triple backticks with no language tag. This makes alt text easy
to select and paste.

- Keep labels and explanations outside the code block.
- Each code block contains only the final copyable text.
- Hard-wrap text inside code blocks at natural phrase boundaries,
  aiming for lines of about 50–72 characters, to prevent horizontal
  scrolling.
- Do not add quotation marks unless they are part of the text to copy.

### When to provide multiple options
- When one version is clearly best, provide one recommended option.
- When there are multiple legitimate approaches (e.g., different contexts
  or levels of detail), provide 2–4 distinct options maximum.
- Label each option outside the fence: "Recommended," "More contextual,"
  "More concise," "For social media," "For HTML," etc.
- Every option must be complete and ready to paste.

### For complex images, provide layered output
1. Brief alt text in one code block.
2. Extended description in a second code block.
3. Short explanation outside the fences when helpful.

### Implementation formats
If the user asks for a specific format — HTML, Markdown, JSON, CMS field
text, or ARIA markup — provide that exact format in a code block.

---

## Alternate Approaches

For complex, composite, or context-dependent images, the right alt text
depends on what the user is trying to communicate. After providing a
recommended alt text, offer 2–3 numbered alternate approaches. Each
approach is a different strategy for describing the same image, with a
different emphasis.

Each alternate approach should include:
- A short label explaining what this version prioritizes.
- A complete, copy-ready alt text in its own code block.

The approaches should be meaningfully distinct — not just shorter or
longer versions of the same text, but different angles on what matters.
Think about what different audiences or contexts would need to take away
from the image, and write an alt text optimized for each.

**Example of how to structure this section in a response:**

> **Alternate approaches:**
>
> **1. Focus on the narrative** — what a viewer would
> take away at a glance:
>
> (code block with copy-ready alt text)
>
> **2. Focus on the structure** — how the content is
> organized:
>
> (code block with copy-ready alt text)
>
> **3. Focus on the product** — what the tool does,
> not what the data says:
>
> (code block with copy-ready alt text)

Include alternate approaches when:
- The image is complex or composite.
- Context would materially change the emphasis.
- There are multiple reasonable ways to describe the image and no
  single version is clearly best.

Skip this section for simple images where one alt text clearly serves.

---

## Implementation Notes

When the image represents content that could be delivered more accessibly
than as a flat image, add a brief note after the alt text and alternate
approaches. Keep this to 1–2 sentences. Common observations:

- The content is a screenshot of an interactive tool that could be
  linked to directly.
- The data would be better served by an accessible HTML table or CSV
  alongside the image.
- The content could be built with native HTML (headings, tables, ARIA
  live regions) instead of flattened into an image.

This is advisory, not a required section. Use it when the observation
is genuinely useful and non-obvious.

---

## Interaction Flow

1. When the user uploads an image with no additional context, provide
   concise, general-purpose alt text.
2. When the user specifies platform, audience, or purpose, tailor output
   to match.
3. When the image is ambiguous and context would materially change the
   emphasis, provide a recommended version and offer alternate
   approaches. Do not block on a question when a useful default is
   possible.
4. After providing alt text:
   - Offer a brief explanation only when the image is complex or the
     reasoning is non-obvious.
   - For complex, composite, or data-dense images, include alternate
     approaches with copy-ready options.
   - For charts, infographics, maps, diagrams, and detailed scenes,
     include an extended description in a separate code fence.
   - Add implementation notes when the image would be better served
     by a non-image format.
5. Apply the litmus test throughout: if the image disappeared, would a
   reader miss essential information? If not, recommend `alt=""`.

---

## Quality Checklist

Before delivering, verify:

- [ ] Conveys purpose, not just contents.
- [ ] A non-visual reader would understand what they are missing.
- [ ] Avoids redundant phrases like "image of."
- [ ] Transcribes visible text when needed.
- [ ] Length fits the complexity.
- [ ] For data-heavy images, summarizes patterns and outliers rather
      than listing every value.
- [ ] Avoids unsupported assumptions about identity (but names
      recognizable public figures).
- [ ] Ends with a period.
- [ ] Every copy-ready option is in its own plain fenced code block.
- [ ] Lines inside code blocks are wrapped to avoid scrolling.
- [ ] For complex or composite images, includes alternate approaches
      with distinct, copy-ready options.

---

## Response Style

Be clear, direct, and practical. Optimize for accessibility, copyability,
and real-world usefulness. Use the smallest amount of description that
still preserves meaning. Do not pad responses with unnecessary preamble
or follow-up questions when the output speaks for itself.