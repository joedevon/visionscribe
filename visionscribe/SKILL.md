---
name: visionscribe
description: >
  Write good alt text and image descriptions using the best advice of
  accessibility experts. Use when someone shares an image and asks for alt
  text, an image description, or how to make the image accessible to screen
  reader users.
license: MIT
---

# VisionScribe

Write alt text and image descriptions that explain what an image contributes
in context. Give readers who cannot see the image the information they need.
Make the text ready to copy.

## Classify the image

Before writing anything, classify the image:

### Decorative

The image adds visual appeal but no information. If it disappeared, would
a reader miss something essential? If not, recommend `alt=""`:

```
alt=""
```

### Functional

The image is a link or button. Describe the function or destination, not
the appearance. "Search" is correct; "magnifying glass icon" is not.

### Contains text

Include visible text verbatim when it carries meaning that isn't already
conveyed in surrounding content. If the text is fully redundant with a
caption or adjacent copy, note that and recommend `alt=""`.

For dense tables, dashboards, or long paragraphs, summarize the main
message instead of transcribing everything. Offer alternate approaches
so the user can choose the emphasis that fits the context.

### Informative

Explain what the image communicates and why it is there.

### Complex

For charts, graphs, infographics, maps, data visualizations, and diagrams,
provide:

- Brief alt text with the key takeaway.
- Extended description with important data, labels, structure, or
  relationships.
- When relevant, suggest `<figcaption>`, `aria-describedby`, or a linked
  data table to accompany the image.

### Composite

Dashboards and other images with many charts, tables, or panels need more
than a long description. A screen reader user needs ways to scan, skip,
and interact with the content. Alt text alone cannot provide those.

For composite images:

- The brief alt text should name the tool, state what it covers, and
  describe its structure, such as "five domain columns".
- The extended description should explain the two to four most important
  patterns, trends, or outliers. Put detailed values in a data table
  rather than listing every metric in prose.
- Always include alternate approaches, because the right
  emphasis depends heavily on how the image is being used.

---

## Write the alt text

### Structure

- Lead with the most important information.
- Explain the purpose before adding detail.
- Use spatial order when it helps orientation.
- End alt text with a period.

### Length

- For simple images, write one sentence, roughly 15 to 25 words.
- For moderately complex images, write one or two sentences.
- For complex images, write brief alt text and a separate extended
  description.
- Keep extended descriptions to a few sentences about the structure,
  main findings, and notable outliers. Summarize patterns and recommend
  a data table for detailed values.

### Include

- Who or what is shown.
- What is happening.
- Why it matters in context.
- Visible text, transcribed exactly when relevant.
- Colors, materials, layout, labels, trends, or relationships when they
  carry meaning.

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

## Describe people

- Use specific age terms when relevant: baby, toddler, child, teen, young
  adult, adult, older adult.
- Prioritize actions over appearance unless appearance is the point.
- Mention visible assistive devices or physical characteristics only when
  relevant to context.
- Name people a sighted reader would recognize. A news photo of a
  senator should name the senator. Many AI models will not identify
  people from their faces. Find the name from context:
  - Use a name from the caption, the surrounding text, visible text in the
    image, such as a name tag, an on-screen caption, or a jersey, or the
    file name.
  - If none of those gives a name, ask the user who is pictured. Still
    provide alt text now, with a `[Name]` placeholder they can fill in.
  - Never drop a name silently. If you could not name someone a sighted
    reader would likely recognize, say so outside the code block.

---

## Guidance by image type

**Photographs:** Describe subject, action, setting, and mood when relevant.

**Charts and graphs:** Name the chart type, state the variables, summarize
the main trend, and include key data points or outliers in the extended
description.

**Screenshots:** Focus on what the screenshot demonstrates, not every UI
element. Transcribe key text and describe the relevant state or
interaction.

**Dashboards and multi-panel views:** See the Composite classification
above. Name the product, describe the organizational structure, and
explain the main findings. Do not walk through every widget.

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

## Adjust for context

Adjust the emphasis to the platform and purpose the user gives:

- **Social media:** Concise, focused on the key message.
- **Educational:** Include labels, relationships, sequence, and
  lesson-relevant details.
- **E-commerce:** Highlight product features, colors, materials, scale,
  visible details, and how the product appears in use.
- **News and journalism:** Objective and factual. Describe what is
  happening and who is involved. Name the people shown, using the caption
  or article text.
- **Museum and gallery:** Describe medium, style, and composition. Use
  sensory detail. Note artist and title if known.
- **Documentation and technical:** Focus on the state, flow, step,
  architecture, or outcome the reader needs.

When the user gives no context, write general-purpose informative alt
text. If context would change the emphasis,
provide one recommended version and offer alternate approaches.

---

## Format the output

Put each text option in its own fenced code block. Use plain triple
backticks with no language tag so the user can select and paste the text.

- Keep labels and explanations outside the code block.
- Each code block contains only the final copyable text.
- Hard-wrap text inside code blocks at natural phrase boundaries,
  aiming for lines of about 50 to 72 characters, to prevent horizontal
  scrolling.
- Do not add quotation marks unless they are part of the text to copy.

### When to provide multiple options

- When one version is clearly best, provide one recommended option.
- When different contexts or levels of detail call for different
  descriptions, provide two to four distinct options at most.
- Label each option outside the fence: "Recommended," "More contextual,"
  "More concise," "For social media," "For HTML," etc.
- Every option must be complete and ready to paste.

### For complex images

1. Brief alt text in one code block.
2. Extended description in a second code block.
3. Short explanation outside the fences when helpful.

### Implementation formats

If the user asks for HTML, Markdown, JSON, CMS field text, or ARIA markup,
provide that format in a code block.

---

## Offer alternate approaches

For complex or composite images, or when context changes what matters,
give recommended alt text followed by two or three numbered alternatives.
Each alternative should emphasize something different about the image.

Each alternate approach should include:

- A short label explaining what this version prioritizes.
- A complete, copy-ready alt text in its own code block.

Choose alternatives based on what different audiences need to know.
Changing only the length does not make an alternative useful.

Example structure:

> **Alternate approaches:**
>
> **1. Main finding**
>
> (code block with copy-ready alt text)
>
> **2. Organization of the content**
>
> (code block with copy-ready alt text)
>
> **3. Purpose of the tool**
>
> (code block with copy-ready alt text)

Include alternate approaches when:

- The image is complex or composite.
- Context would materially change the emphasis.
- There are multiple reasonable ways to describe the image and no
  single version is clearly best.

Skip this section for simple images where one alt text clearly serves.

---

## Add implementation notes

If readers would benefit from another way to access the content, add one
or two sentences after the descriptions. For example:

- The content is a screenshot of an interactive tool that could be
  linked to directly.
- The data would be better served by an accessible HTML table or CSV
  alongside the image.
- The content could use HTML headings, tables, or ARIA live regions
  instead of an image.

Include this note only when it gives the user a useful next step.

---

## Respond to the user

1. When the user uploads an image with no additional context, provide
   concise, general-purpose alt text.
2. When the user specifies platform, audience, or purpose, tailor output
   to match.
3. When the image is ambiguous and context would change the
   emphasis, provide a recommended version and offer alternate
   approaches. Do not block on a question when a useful default is
   possible.
4. After providing alt text:
   - Offer a brief explanation only when the image is complex or the
     reasoning needs explanation.
   - For complex, composite, or data-dense images, include alternate
     approaches with copy-ready options.
   - For charts, infographics, maps, diagrams, and detailed scenes,
     include an extended description in a separate code fence.
   - Add implementation notes when the image would be better served
     by a non-image format.
5. Apply the litmus test throughout: if the image disappeared, would a
   reader miss essential information? If not, recommend `alt=""`.

---

## Check the result

Before delivering, verify:

- [ ] Conveys purpose, not just contents.
- [ ] A non-visual reader would understand what they are missing.
- [ ] Avoids redundant phrases like "image of."
- [ ] Transcribes visible text when needed.
- [ ] Length fits the complexity.
- [ ] For data-heavy images, summarizes patterns and outliers rather
      than listing every value.
- [ ] Avoids unsupported assumptions about identity, but names people
      when the context gives their names, or flags the missing name.
- [ ] Ends with a period.
- [ ] Every copy-ready option is in its own plain fenced code block.
- [ ] Lines inside code blocks are wrapped to avoid scrolling.
- [ ] For complex or composite images, includes alternate approaches
      with distinct, copy-ready options.

---

## Writing style

Use plain language and keep descriptions as short as the meaning allows.
Start with the description. Add explanations or follow-up questions only
when they help the user.
