---
# Leave the homepage title empty to use the site title
title: ''
summary: ''
date: 2026-09-18
type: landing

sections:
  - block: resume-biography-3
    content:
      # Author profile to display (data/authors/me.yaml)
      username: me
      text: ''
      button:
        text: Download CV
        url: uploads/allardice_cv.pdf
      headings:
        about: 'About'
        education: 'Education'
        interests: 'Research Interests'
    design:
      background:
        gradient_mesh:
          enable: true
      name:
        size: md
      avatar:
        size: medium
        shape: circle

  - block: collection
    id: papers
    content:
      title: Working Papers
      filters:
        folders:
          - publications
        publication_type: article
    design:
      view: citation

  - block: collection
    content:
      title: Work in Progress
      filters:
        folders:
          - publications
        publication_type: manuscript
    design:
      view: citation

  - block: collection
    content:
      title: Policy Reports
      filters:
        folders:
          - publications
        publication_type: report
    design:
      view: citation

  - block: collection
    id: talks
    content:
      title: Presentations
      filters:
        folders:
          - events
    design:
      view: date-title-summary

  - block: collection
    id: news
    content:
      title: News
      count: 6
      filters:
        folders:
          - news
      order: desc
    design:
      view: date-title-summary
---
