# Tokens in LLMs - PowerPoint Presentation Generator

A Python project that generates professional PowerPoint presentations about tokens in Large Language Models (LLMs) using the `python-pptx` library.

## Overview

This repository demonstrates automated presentation creation with a clean, minimalistic design. The main presentation explains what tokens are, why they matter, and how they work in the context of large language models.

## Generated Presentation

The `tokens_in_llms.pptx` file contains a 10-slide presentation covering:

1. **Title Slide** - Understanding Tokens: The Building Blocks of Large Language Models
2. **What is a Token?** - Basic definition and examples
3. **Why Tokens Matter** - Importance in LLM processing
4. **The Tokenization Process** - Visual flowchart of text-to-embedding conversion
5. **Types of Tokenization** - Word-level, character-level, and subword methods
6. **Subword Tokenization Example** - Practical examples showing token splits
7. **Token Limits & Context Windows** - Understanding model constraints
8. **Practical Implications** - Cost, speed, and usage considerations
9. **Optimizing Token Usage** - Best practices and tips
10. **Key Takeaways** - Summary of main concepts

## Design System

### Color Palette (Black & White Minimalistic)
- **Black** `(0, 0, 0)` - Primary text and accents
- **White** `(255, 255, 255)` - Backgrounds
- **Light Gray** `(240, 240, 240)` - Content boxes
- **Medium Gray** `(128, 128, 128)` - Secondary elements
- **Dark Gray** `(64, 64, 64)` - Body text

### Typography
- Titles: 44-66pt bold
- Content: 20pt
- Small text: 18pt

### Format
- Widescreen 16:9 aspect ratio (16" x 9")

## Installation

```bash
pip install python-pptx pillow
```

Or on macOS:

```bash
pip3 install python-pptx pillow --break-system-packages
```

## Usage

Generate the presentation:

```bash
python tokens_presentation.py
```

This creates `tokens_in_llms.pptx` in the same directory.

## Project Structure

```
.
├── README.md                 # This file
├── tokens_presentation.py    # Main script for tokens presentation
├── tokens_in_llms.pptx       # Generated presentation output
├── complete_pptx_code.py     # Additional presentation example
├── key_lessons.md            # Development notes and lessons learned
└── CLAUDE.md                 # AI assistant instructions
```

## Customization

To modify the presentation, edit `tokens_presentation.py`:

- **Change colors**: Update the color constants at the top of the file
- **Edit content**: Modify the text in `add_standard_slide()` calls
- **Add slides**: Use the `add_standard_slide()` helper or create custom slides

### Helper Function

```python
add_standard_slide(
    "Slide Title",
    [
        "First bullet point",
        "Second bullet point",
        "Third bullet point"
    ]
)
```

## Key Patterns

1. **Blank layout** - Uses `prs.slide_layouts[6]` for full control over elements
2. **Layered design** - Background elements first, then content
3. **Reusable components** - Helper functions for consistent slide structure
4. **Visual elements** - Accent lines, rounded rectangles, and arrows for engagement

## Requirements

- Python 3.7+
- python-pptx
- Pillow (for image support)

## License

MIT License - Feel free to use and modify for your own presentations.

---

Generated with [Claude Code](https://claude.com/claude-code)
