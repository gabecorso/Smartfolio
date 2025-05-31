# Smartfolio
Smart Portfolio with easy configuration for multiple users

## Project Overview

This repository contains a configurable portfolio website system designed to showcase diverse professional expertise across multiple role variants. The architecture enables deployment of multiple portfolio versions from a single codebase, each tailored to specific career opportunities while maintaining consistent quality and minimal code duplication.

## Core Architecture Principles

### Configuration-Driven Design

The entire application operates on a configuration-first principle. Each deployment variant reads from a specific configuration that determines content, theming, feature visibility, and navigation structure. This approach ensures that new portfolio variants can be created through configuration changes rather than code modifications.

### Component Modularity

All components are designed with maximum reusability in mind. Components accept configuration props that modify their behavior and appearance, allowing the same component to serve different purposes across portfolio variants. This modularity extends from atomic components like buttons to complex organisms like project showcases.

### Content Flexibility

Content management is decoupled from the application logic. Whether content resides in the repository, external CMS, or cloud storage services like AWS S3, the application maintains a consistent interface for content retrieval. This flexibility allows for future scaling without architectural changes.

## Technical Stack

### Core Technologies
- **Frontend Framework**: React 18 with TypeScript for type safety and enhanced developer experience
- **Styling**: CSS Modules with CSS Variables for theming, ensuring style encapsulation and runtime theme switching
- **Build Tool**: Vite for fast development and optimized production builds
- **Deployment**: Vercel for seamless deployments with environment-specific configurations
- **State Management**: React Context API for configuration and theme management
- **Content Format**: Markdown with frontmatter for rich content authoring

### Development Tools
- **Linting**: ESLint with React and TypeScript configurations
- **Formatting**: Prettier for consistent code style
- **Type Checking**: TypeScript strict mode enabled
- **Testing**: Vitest for unit tests and Playwright for E2E testing

## Project Structure

```
portfolio/
├── src/
│   ├── components/          # Reusable UI components
│   │   ├── common/         # Shared components across all variants
│   │   ├── sections/       # Major page sections
│   │   └── utils/          # Utility components
│   ├── config/             # Configuration management
│   │   ├── types.ts        # Configuration type definitions
│   │   ├── loader.ts       # Configuration loading logic
│   │   └── variants/       # Role-specific configurations
│   ├── content/            # Local content storage (if not using external)
│   │   ├── projects/       # Project case studies
│   │   ├── experience/     # Work experience details
│   │   └── blog/          # Optional blog posts
│   ├── hooks/              # Custom React hooks
│   ├── styles/             # Global styles and theme definitions
│   │   ├── themes/         # Theme configurations
│   │   ├── variables.css   # CSS custom properties
│   │   └── global.css      # Global styles
│   ├── utils/              # Utility functions
│   └── App.tsx             # Main application component
├── public/                 # Static assets
├── config/                 # Build and deployment configurations
└── scripts/                # Build and deployment scripts
```

## Configuration System

### Configuration Schema

Each portfolio variant is defined by a comprehensive configuration object that controls all aspects of the site. The configuration includes metadata, theme settings, navigation structure, content sources, and feature flags.

### Environment Variables

The active configuration is determined by environment variables set during build time. This approach allows for secure API keys and configuration switching without code changes.

### Dynamic Configuration Loading

The application supports runtime configuration switching for development, allowing rapid iteration between portfolio variants without rebuilding.

## Component Architecture

### Atomic Design Principles

Components follow atomic design methodology, building from atoms (buttons, inputs) through molecules (cards, forms) to organisms (navigation, hero sections) and templates (page layouts).

### Prop Interface Consistency

All components maintain consistent prop interfaces with clear separation between data props, configuration props, and event handlers. This consistency simplifies component composition and testing.

### Accessibility First

Every component is built with WCAG 2.1 AA compliance as a baseline requirement. This includes proper semantic HTML, ARIA attributes, keyboard navigation, and screen reader support.

## Content Management Strategy

### Content Structure

Content is structured with clear separation between different types: professional summary, work experience, projects, skills, and achievements. Each content type has a defined schema ensuring consistency across variants.

### External Content Support

The architecture supports external content sources through a content adapter pattern. Whether content comes from markdown files, a headless CMS, or cloud storage, the application interface remains consistent.

### Multilingual Readiness

The content structure supports internationalization, allowing for future expansion into multiple languages without architectural changes.

## Deployment Strategy

### Multi-Environment Support

The deployment configuration supports multiple environments (development, staging, production) with appropriate optimizations for each. Development prioritizes fast refresh and debugging, while production emphasizes performance and SEO.

### Continuous Deployment

GitHub Actions workflows automate testing, building, and deployment processes. Each push to designated branches triggers appropriate deployment pipelines with variant-specific configurations.

### Performance Budget

Each deployment maintains strict performance budgets: initial load under 3 seconds on 3G, Lighthouse scores above 90 for all metrics, and total bundle size under 200KB gzipped.

## Development Workflow

### Local Development Setup

Development environment setup is streamlined with clear prerequisites and automated setup scripts. The development server supports hot module replacement and configuration switching.

### Code Quality Standards

Strict TypeScript configuration ensures type safety throughout the application. Pre-commit hooks enforce linting, formatting, and type checking before code submission.

### Testing Strategy

Comprehensive testing covers unit tests for utilities and hooks, integration tests for components, and end-to-end tests for critical user journeys. Visual regression testing ensures UI consistency across changes.

## Future Extensibility

### Plugin Architecture

The component system is designed to support future plugin development, allowing for feature extensions without modifying core code.

### Theme Marketplace Readiness

The theming system is structured to support future theme distribution, enabling community contributions or commercial theme development.

### Analytics Integration

The architecture includes hooks for analytics integration, supporting variant-specific tracking to measure portfolio effectiveness.

## Getting Started

### Prerequisites

Ensure you have Node.js 18+ and npm 9+ installed. Git is required for version control, and a Vercel account is needed for deployment.

### Initial Setup

Clone the repository and install dependencies using npm. Copy the environment template and configure for your first variant. The development server will guide you through initial configuration.

### Creating Your First Variant

Start with the provided variant template, customize the configuration with your content and preferences, and deploy to Vercel with variant-specific environment variables.

## Contributing Guidelines

This project follows conventional commits for clear change tracking. All code must pass linting and type checking before merge. Component documentation is required for all new components.

## License

This project structure and system is proprietary. Individual portfolio content remains the property of the portfolio owner.
