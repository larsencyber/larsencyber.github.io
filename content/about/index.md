---
title: About Me
type: landing

design:
  # Default section spacing
  spacing: "1rem"

# Note: `username` refers to the user's folder name in `content/authors/`

# Page sections
sections:
  - block: biography
    content:
      username: admin
      # Show a call-to-action button under your biography? (optional)
      #button:
        #text: Download Résumé
        #url: uploads/resume.pdf
    design:
      banner:
        # Upload your cover image to the `assets/media/` folder and reference it here
        filename: banner-perth-1.jpg
      biography:
        # Customize the style of your biography text
        style: 'text-align: justify; font-size: 1em;'
  - block: experience
    content:
      username: admin
    design:
      # Hugo date format
      date_format: 'January 2006'
      # Education or Experience section first?
      is_education_first: false
  - block: skills
    content:
      title: Skills
      username: admin
  - block: awards
    content:
      title: Industry Participation
      username: admin
---