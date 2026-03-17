# Semantic HTML Design Document: Tom's Asphalt Service

This document outlines the architectural decisions and semantic structure used for the website. Using semantic HTML ensures the site is accessible to screen readers, understandable for search engines, and maintainable.

## 1. Primary Structural Elements

The site follows a hierarchical structure, ensuring that content is categorized logically.

### 1.1 Navigation
- Branding & Utility: The \<nav\> element contains the primary logo and site navigation links.
- Accessibility: The \<nav\> tag signals to assistive technologies that this block contains the site's primary navigation.
- Top Bar: A secondary utility \<div\> provides immediate contact information for desktop users.

### 1.2 Main Content
All unique content for the page is wrapped in a \<main\> tag.

- Hero Header: The hero area uses a \<header\> tag and includes the \<h1\>, which acts as the unique identifier for the page's purpose.
- Thematic Sections: Each major block (Services, About, Contact) uses a \<section\> tag with a unique id for document outlining and URL anchoring.
- Content Grouping: Within sections, we use logical grouping to maintain a clear parent-child relationship.

### 1.3 Forms
- Interactive Semantics: The contact area uses a proper \<form\> element.
- Input Accuracy: Uses standard semantic types such as type="tel" and type="text" to ensure the correct virtual keyboard appears on mobile devices.

### 1.4 Footer
- Closing Metadata: Wrapped in a \<footer\> tag, this area contains secondary branding, business credentials, and copyright information.

## 2. Heading Hierarchy

We maintain a strict heading hierarchy to ensure a clear "Table of Contents" for search engines:
- H1: The primary value proposition and page title (Hero).
- H2: Major section titles that define the site's structure (Services, About, Contact).
- H3: Specific sub-features or individual service categories within the grid.

## 3. Accessibility & Interaction

- Interactive Elements: Elements that trigger an interface action, like the mobile menu, use the \<button\> tag.
- Aria Labels: The mobile menu toggle includes aria-label="Toggle navigation" to provide context for icon-only buttons.
- Alternative Text: All critical images use alt attributes to provide descriptions for visually impaired users.

## 4. Visual Semantics (CSS Variables)

The design uses CSS variables to maintain a "Source of Truth" for the brand's visual identity:
- primary-yellow: Matched to the logo stripe (#ffcc00) for all calls-to-action and highlights.
- asphalt-dark: Provides the industrial, high-contrast background necessary for professional readability.
