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

  - block: markdown
    id: teaching
    content:
      title: Teaching
      subtitle: ''
      text: |-
        ### Claude Code for Academic Researchers

        *A hands-on methods workshop in AI-assisted research.*

        A workshop (about 60–70% exercises) on using agentic coding tools across the empirical research
        pipeline: data cleaning and merging, estimation and robustness checks, code auditing, version control
        with Git, LaTeX in VS Code, and extending the agent with custom skills, subagents, hooks, and MCP
        connections. The capstone is a replication of a published empirical paper. Designed for graduate
        students, postdocs, and faculty across the social sciences.

        **Editions**

        - Universitat Autònoma de Barcelona, staff training programme, October 28 – November 4, 2026 (upcoming)
        - [IBEI Graduate Summer School](https://www.ibei.org/en/agentic-coding-for-academic-researchers_439728), June 8–12, 2026
        - Universitat de Barcelona, Department of Economics, June 1–8, 2026
        - Universitat de Barcelona, Department of Political Science, March 8–28, 2026

        [Syllabus (PDF)](uploads/claude_code_workshop_syllabus.pdf) · [Course materials on GitHub](https://github.com/bradyallardice/claude-code-workshop)
    design:
      columns: '1'

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
      # 0 = show all. A limit adds a "See all" button, which has no page to link to
      # because news items are not rendered as separate pages.
      count: 0
      filters:
        folders:
          - news
      order: desc
    design:
      view: date-title-summary
---
