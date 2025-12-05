# Academic Journey Portfolio

[![GitHub Pages](https://img.shields.io/badge/GitHub%20Pages-Active-success?style=flat-square&logo=github)](https://joembolinas.github.io)
![Project Phase](https://img.shields.io/badge/Phase-1%20Documentation-blue?style=flat-square)
![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat-square&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=flat-square&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black)

**A GitHub Pages portfolio system for documenting academic learning and professional growth in Information Technology.**

[About](#about) • [Features](#features) • [Development Standards](#development-standards) • [Project Structure](#project-structure) • [Getting Started](#getting-started)

---

## About

The Academic Journey Portfolio (AJP) is a web-based platform designed to document and showcase academic achievements, course reflections, and technical skills development throughout an IT education journey at MMDC (Malayan Colleges Mindanao).

This portfolio serves as both a learning documentation tool and a professional showcase, demonstrating growth in:

- Technical competencies across multiple programming languages
- Project-based learning outcomes
- Real-world application of IT concepts
- Professional development and soft skills

> [!NOTE]
> **Current Status**: Phase 1 (Documentation & Planning)
> The project is in its initial documentation phase, establishing the foundation for a comprehensive portfolio system.

## Features

### Core Capabilities

- **Course Reflection Documentation**: Structured templates for documenting learning experiences across academic terms
- **Project Showcase**: Highlight practical outputs with descriptions, technologies used, and learning outcomes
- **Skills Tracking**: Document technical skills gained in programming languages, tools, and frameworks
- **Responsive Design**: Mobile-first, accessible web interface following WCAG 2.1 guidelines
- **GitHub Pages Hosting**: Free, reliable hosting with version control integration

### Planned Features

- Interactive project galleries with live demos
- Downloadable portfolio exports
- Progress tracking dashboards
- 

## Development Standards

### Code Quality

#### HTML/CSS

- Semantic HTML5 elements for improved accessibility
- BEM (Block Element Modifier) naming convention for CSS
- WCAG 2.1 Level AA compliance for accessibility

#### JavaScript

- Progressive enhancement approach
- JSDoc comments for all functions
- ES6+ modern JavaScript features

#### Documentation

- Comprehensive inline comments explaining the "why"
- Version tracking in file footers: `{Version} | {Status} | {Last Updated: MMM DD YYYY - HH:MM}`
- ASCII art diagrams for visualizations (Mermaid on request)

### Git Workflow

- **Conventional Commits**: Standardized commit messages following the Conventional Commits specification
- **Descriptive Messages**: Clear explanation of changes and their purpose
- **Issue References**: Link commits to relevant issues for traceability

## Project Structure

```text
joembolinas.github.io/
├── .github/
│   ├── agents/                 # AI agent configurations
│   ├── instructions/           # Development guidelines
│   └── prompt/                 # Prompt templates for automation
├── docs/                       # Documentation (planned)
├── src/                        # Source code (planned)
├── assets/                     # Images, fonts, media (planned)
└── README.md                   # This file
```

### Key Files

| File                                | Description                         |
| ----------------------------------- | ----------------------------------- |
| `README.md`                       | Project overview and documentation  |
| `commit.prompt.md`                | Git commit message automation guide |
| `.github/copilot-instructions.md` | GitHub Copilot custom instructions  |

## Getting Started

### Prerequisites

- Basic understanding of HTML, CSS, and JavaScript
- Git installed on your local machine
- GitHub account
- Code editor (VS Code recommended)

### Local Development

1. **Clone the repository**

   ```bash
   git clone https://github.com/joembolinas/joembolinas.github.io.git
   cd joembolinas.github.io
   ```
2. **Start development**

   - Open the project in your preferred code editor
   - Make changes to HTML/CSS/JavaScript files
   - Test locally using a live server
3. **Commit changes**

   ```bash
   git add .
   git commit -m "feat: add new feature description"
   git push origin main
   ```
4. **View on GitHub Pages**

   - Visit `https://joembolinas.github.io`
   - Changes may take a few minutes to deploy

### Using AI Assistance

This project is configured with custom GitHub Copilot instructions for enhanced development support:

**@mentor agent**: Get educational guidance on concepts, architecture, and best practices

```text
As my mentor, help me understand [concept]
```

For detailed AI assistance guidelines, see [.github/copilot-instructions.md](.github/copilot-instructions.md).

## Course Reflection Framework

Academic reflections in this portfolio follow a structured framework with ten key sections:

### I. Introduction

- Course context and main objectives
- Initial expectations and learning goals
- Personal connection to the IT field

### II. Learning Journey Documentation

- Weekly milestones and progress
- Evolution of understanding
- Connection to practical assignments

### III. Technical Skills Gained

- Programming languages (Java, C++, Python)
- Cloud, networking, cybersecurity concepts
- Tools: SAP, GitHub, Notion, Tableau, Excel, AppScript
- Frameworks: SDLC, REST APIs, IoT, Blockchain

### IV. Projects & Practical Outputs

- Project goals and requirements
- Development process and teamwork
- Challenges and solutions
- Final outcomes and learnings

### V. Course vs Personal Outcomes

- Formal learning objectives met
- Personal growth achieved
- Critical analysis of the experience

### VI. Real-World Connections

- Industry scenario applications
- Workplace skill relevance
- Professional preparation

### VII. Challenges & Growth

- Obstacles encountered
- Problem-solving approaches
- Mindset development

### VIII. MMDC Learning Model

- Self-paced structured learning
- Team collaboration experiences
- Project-based assessment

### IX. Future Application

- Career applications
- Ongoing learning commitments
- Professional development plans

### X. Closing Reflection

- Summary of personal growth
- Key takeaways
- Confidence in IT pathway

## Resources

### Technologies Used

- [GitHub Pages](https://pages.github.com) - Static site hosting
- [HTML5](https://developer.mozilla.org/en-US/docs/Web/HTML) - Markup language
- [CSS3](https://developer.mozilla.org/en-US/docs/Web/CSS) - Styling
- [JavaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript) - Client-side scripting

### Learning Resources

- [BEM Methodology](https://getbem.com) - CSS naming convention
- [WCAG Guidelines](https://www.w3.org/WAI/WCAG21/quickref/) - Accessibility standards
- [Conventional Commits](https://www.conventionalcommits.org) - Commit message format

## Roadmap

- [ ] Phase 1: Documentation & Planning *(Current)*
- [ ] Phase 2: Design & Architecture
- [ ] Phase 3: Core Development
- [ ] Phase 4: Content Migration
- [ ] Phase 5: Testing & Refinement
- [ ] Phase 6: Launch & Deployment

---

*v1.0.0 | Active | Last Updated: Dec 05 2024 - 00:00*
