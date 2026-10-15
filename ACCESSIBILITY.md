# Accessibility

VisionScribe exists so that people who can't see an image still get what it says. Screen reader users, people with low vision, and anyone whose images fail to load depend on alt text and image descriptions. When those are missing or vague, they lose information everyone else gets. Accessibility is the whole purpose of this project, so it applies to what VisionScribe writes and to how people use and contribute to it.

This document covers what the project aims for and how to report a problem.

## What we aim for

- **Useful output.** Alt text and descriptions should convey an image's purpose in context, following WCAG and the W3C alt text decision tree, rather than listing what is visible.
- **Accessible documentation.** The README and this file should work with assistive technology, with real headings, descriptive link text, and text alternatives for any images.
- **Open participation.** People with disabilities, including people who use assistive technology, should be able to install the skill, report problems, and contribute changes.

VisionScribe drafts alt text. It does not make a page accessible or compliant on its own. A person who knows where the image will appear should review the result before publishing it.

## Report a problem

[Open an issue](https://github.com/joedevon/visionscribe/issues/new) and describe what went wrong. A maintainer will add the `accessibility` label.

Two kinds of reports help most:

- **Output problems.** The alt text is wrong, misleading, too long, or misses important text or context from the image.
- **Access problems.** You could not complete the installation steps or documentation with your assistive technology.

Where you can, include the image or a description of it, where the alt text was going to be used, what VisionScribe produced, which AI tool you used, and any assistive technology involved. Leave out personal or confidential images.
