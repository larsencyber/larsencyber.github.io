---
title: About Me
toc: true
reading_time: false
pager: false
---

sections:
  - block: resume-biography
    content:
      # The user's folder name in `content/authors/`
      username: admin
      # Show a call-to-action button under your biography? (optional)
      # To link to a file, upload it to your `static/uploads/` folder
      button:
        text: Download Résumé
        url: uploads/resume.pdf
    design:
      banner:
        # Upload a cover image to `assets/media/` folder and reference its filename here (optional)
        filename: ''
      biography:
        # Customize the CSS style of your biography text (optional)
        style: ''
    - block: resume-experience
    content:
      # The user's folder name in `content/authors/`
      username: admin
    design:
      # Hugo date format
      date_format: 'January 2006'
      # Education or Experience section first?
      is_education_first: false
   - block: resume-skills
    content:
      title: Skills & Hobbies
      # Note: `username` refers to the user's folder name in `content/authors/`
      username: admin
    - block: resume-awards
    content:
      title: Awards
      # Note: `username` refers to the user's folder name in `content/authors/`
      username: admin