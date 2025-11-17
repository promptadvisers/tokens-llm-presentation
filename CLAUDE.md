# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a Python-based PowerPoint generation project focused on creating professional educational presentations about AI/ML topics, specifically Language Models and Prompt Engineering. The codebase demonstrates automated presentation creation using the `python-pptx` library.

## Development Commands

### Dependencies
```bash
pip install python-pptx pillow --break-system-packages
```

### Running the Script
```bash
python complete_pptx_code.py
```

## Architecture & Key Patterns

### File Creation Approach
**Critical**: When creating Python script files in similar environments, use bash heredoc instead of direct file creation tools:

```bash
cat > /path/to/script.py << 'EOF'
[Python code here]
EOF
```

This approach avoids failures with large Python scripts that other file creation methods may encounter.

### PowerPoint Design System

The codebase implements a professional design system with:

**Color Palette:**
- `PRIMARY = RGBColor(30, 41, 59)` - Dark slate for main text/elements
- `ACCENT = RGBColor(99, 102, 241)` - Indigo for highlights and accents
- `GRAY = RGBColor(148, 163, 184)` - Slate gray for secondary elements
- `WHITE = RGBColor(255, 255, 255)` - White for backgrounds/contrast

**Typography Hierarchy:**
- Titles: 48pt
- Headers: 36pt
- Content: 20pt
- Small text: 16pt

**Presentation Format:**
- Widescreen: 16:9 aspect ratio
- Slide width: 16 inches
- Slide height: 9 inches

### Slide Creation Patterns

1. **Always use blank layout** (`prs.slide_layouts[6]`) for full control over slide elements

2. **Helper function for standard slides**: The codebase uses `add_standard_slide()` to reduce repetition when creating similar content slides with titles and bullet points

3. **Visual elements** for engagement:
   - Accent lines: 3pt connectors at the top of slides
   - Geometric shapes: Rotated rectangles for visual interest
   - Neural network diagrams: Positioned circles with different fills
   - Architecture diagrams: Stacked rounded rectangles with varying colors

4. **Output location**: Save presentations to `/mnt/user-data/outputs/` directory for proper file access

## Code Structure

- **Initialization**: Set up presentation object with widescreen format and define color constants
- **Slide creation**: Mix of custom-built slides (title, architecture diagrams) and helper function usage
- **Visual components**: Shapes, text frames, and connectors added programmatically
- **Reusable patterns**: Helper functions encapsulate repeated slide structure

## Key Technical Details

### python-pptx Usage Patterns

**Adding shapes:**
```python
shape = slide.shapes.add_shape(MSO_SHAPE.RECTANGLE, x, y, width, height)
shape.fill.solid()
shape.fill.fore_color.rgb = COLOR
shape.rotation = angle
```

**Text formatting:**
```python
text_box = slide.shapes.add_textbox(x, y, width, height)
p = text_box.text_frame.add_paragraph()
p.text = "content"
p.font.size = Pt(size)
p.font.color.rgb = COLOR
```

**Layout structure**: Slides are built layer by layer - background elements first, then content

### Known Limitations & Workarounds

From [key_lessons.md](key_lessons.md):
- `create_file` function fails with large Python scripts
- Reading skill files may give permission errors
- Direct file creation tools sometimes fail
- **Solution**: Use bash heredoc for reliable file creation
