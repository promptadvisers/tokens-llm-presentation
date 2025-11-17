# Key Lessons: PowerPoint Creation with Python

Key Lessons Learned (Critical for AI Agents)
What Failed & Why:

create_file function - Fails with large Python scripts
Reading skill files - /mnt/skills/public/pptx/SKILL.md gives permission errors
Direct file creation - Sometimes the file creation tools fail

What Worked:
bash# The winning approach - use bash heredoc for file creation
cat > /home/claude/create_ppt.py << 'EOF'
[Python code here]
EOF

# Then run it
python /home/claude/create_ppt.py
Complete Recreation Process
Step 1: Dependencies
bashpip install python-pptx pillow --break-system-packages
Step 2: Core Design System
python# Professional color palette
PRIMARY = RGBColor(30, 41, 59)      # Dark slate
ACCENT = RGBColor(99, 102, 241)     # Indigo
GRAY = RGBColor(148, 163, 184)      # Slate gray
WHITE = RGBColor(255, 255, 255)     # White

# Widescreen format
prs.slide_width = Inches(16)
prs.slide_height = Inches(9)

# Typography hierarchy
# Titles: 48pt
# Headers: 36pt
# Content: 20pt
# Small: 16pt
Step 3: Key Patterns
Creating slides:
pythonslide = prs.slides.add_slide(prs.slide_layouts[6])  # Always use blank layout
Adding visual interest:

Accent lines: 3pt connectors at top
Geometric shapes: Rotated rectangles
Neural networks: Positioned circles
Architecture: Stacked rounded rectangles

Critical success factor:
python# ALWAYS save to this directory
prs.save("/mnt/user-data/outputs/filename.pptx")
The Complete Formula

Install dependencies with --break-system-packages
Use bash heredoc for creating Python files (not create_file)
Define colors/fonts upfront for consistency
Use blank layout (index 6) for full control
Create helper functions for repeated slide types
Add visual elements (shapes, diagrams) for engagement
Save to outputs directory for user access

The complete working code in complete_pptx_code.py implements all of this and creates:

Title slide with diagonal accent
Content slides with neural network visualization
Transformer architecture diagram
Two-column comparison slide
10 total slides with consistent design

This approach avoids all the pitfalls I encountered and produces a professional, visually appealing presentation that balances aesthetics with information density - perfect for your educational content about AI and automation!