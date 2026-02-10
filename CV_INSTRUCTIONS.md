# CV Page Instructions

Your CV page is powered by two files:

| File | Purpose |
|------|---------|
| `_pages/cv.md` | Page settings (title, nav position, PDF link) |
| `_data/cv.yml` | All CV content (sections, entries, descriptions) |

---

## Quick Start

1. Open `_data/cv.yml` in any text editor
2. Search for `REPLACE` to find all placeholder fields that need your real data
3. Edit the values, save, and push — the site rebuilds automatically

---

## Page Settings (`_pages/cv.md`)

```yaml
title: Curriculum Vitae    # Page title shown in header and browser tab
nav: true                  # Show in navbar (set false to hide)
nav_order: 5               # Position in navbar (lower = more left)
cv_pdf: example_pdf.pdf    # PDF download button (top-right of page)
description:               # Optional subtitle below the title
toc:
  sidebar: left             # Table of contents sidebar (left, right, or remove to disable)
```

### PDF Download Button

The `cv_pdf` field controls the PDF icon in the top-right corner:

- **Local file**: Place your PDF in `assets/pdf/` and set `cv_pdf: your_cv.pdf`
- **External URL**: Set `cv_pdf: https://example.com/your_cv.pdf`
- **Disable**: Remove or comment out the `cv_pdf` line entirely

---

## CV Content (`_data/cv.yml`)

The file is a YAML list of sections. Each section has a `title`, a `type`, and `contents`. There are 4 section types available.

### Section Type: `map`

Key-value table. Good for general info, contact details.

```yaml
- title: General Information
  type: map
  contents:
    - name: Full Name
      value: Andrea Togni
    - name: Email
      value: your@email.com
    - name: Website              # You can also add link buttons:
      links:
        - name: Personal Site
          link: https://atogni.github.io
```

### Section Type: `time_table`

Timeline entries with year badges. Good for education, experience, awards.

```yaml
- title: Experience
  type: time_table
  contents:
    - title: Job Title                        # Bold heading
      institution: University Name, City      # Shown with building icon
      department: Department Name             # Optional, shown with dot icon
      year: 2020 - present                    # Year badge on the left
      location: City, Country                 # Optional, shown with pin icon
      maindescription: A brief summary.       # Optional, paragraph below institution
      description:                            # Optional, bullet list
        - First bullet point
        - Second bullet point
        - title: Nested group title           # Bullets can have sub-bullets
          contents:
            - Sub-item 1
            - Sub-item 2
      linkitems:                              # Optional, action buttons
        - link: https://example.com
          linkname: Website
```

For **awards**, you can use `items` instead of `title`/`institution`:

```yaml
- title: Honors and Awards
  type: time_table
  contents:
    - year: 2024
      items:
        - Best Paper Award, Some Conference
        - Fellowship Name
```

### Section Type: `nested_list`

Titled groups with bullet items. Good for research interests, skills.

```yaml
- title: Research Interests
  type: nested_list
  contents:
    - title: Category Name
      items:
        - Interest or skill 1
        - Interest or skill 2
```

### Section Type: `list`

Simple bullet list. Good for hobbies, miscellaneous.

```yaml
- title: Other Interests
  type: list
  contents:
    - "<u>Hobbies:</u> Hiking, Photography"
    - "<u>Volunteering:</u> Science outreach"
```

---

## Common Operations

### Add a new section

Add a new block anywhere in `_data/cv.yml`. Sections render in the order they appear in the file.

```yaml
- title: My New Section
  type: time_table          # or map, nested_list, list
  contents:
    - title: Entry title
      year: 2025
```

### Reorder sections

Cut and paste section blocks in `_data/cv.yml`. The page renders top-to-bottom in file order.

### Remove a section

Delete the entire block (from `- title:` to the next `- title:`) or comment it out with `#`.

### Use HTML in values

You can use inline HTML anywhere in text values:

```yaml
value: Italian <em>native</em>, English
title: <a href="https://example.com">Linked Title</a>
```

---

## YAML Tips

- **Indentation matters**: Use 2 or 4 spaces consistently (never tabs)
- **Strings with colons**: Wrap in quotes: `"Thesis: My Title Here"`
- **Special characters**: Wrap in quotes if the string contains `:`, `#`, `[`, `]`, `{`, `}`
- **Multi-line strings**: Use `>` or `|` for long text:
  ```yaml
  maindescription: >
    This is a long description that
    spans multiple lines but renders
    as a single paragraph.
  ```
- **Comments**: Lines starting with `#` are ignored — useful for notes or temporarily hiding entries

---

## Placeholder Fields to Replace

All placeholder fields in the current `_data/cv.yml` are marked with `# REPLACE` comments or contain `REPLACE` in the value. Here is the full checklist:

- [ ] **General Information** > Email
- [ ] **Experience** > Research Fellow title, dates, description
- [ ] **Education** > All degree titles, institutions, years, thesis title
- [ ] **Mission Involvement** > BepiColombo and Hera date ranges
- [ ] **Teaching** > Course names and descriptions
- [ ] **Skills** > Programming languages, tools
- [ ] **Honors and Awards** > All award entries
- [ ] **Other Interests** > Hobbies
