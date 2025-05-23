### Static html website coding preferences
asisaga.github.io is a static Jekyll website on GitHub Pages.
The structure of the website is documented in website_structure.json. Keep this file updated for any structural changes made in the website.

#### Jekyll Structure & Components
- Use Jekyll with Liquid templating (no themes required)
- Create reusable UI components in `_includes` folder
- Use {% include %} tag with parameterization: `{% include component.html param="value" %}`
- Use semantic HTML5 elements (header, nav, main, section, etc.) for accessibility and SEO
- Follow component-based architecture: isolated, reusable, maintainable elements
- Break complex UI patterns into smaller, reusable partials
- Preserve required Jekyll Markdown header in style.scss
- JavaScript: Place in `/assets/js` folder
- Each Jekyll UI component in `_includes` must have a matching SCSS partial in `/assets/css/components/`
- Each HTML page must have a matching SCSS file in `/assets/css/pages/` directory
- Each HTML element in a Jekyll UI component or HTML page must have exactly one SCSS class in its respective SCSS file

#### SCSS Structure & Components
- Bootstrap v5.3.5 with dependencies in `assets/css/bootstrap`
- Naming: Use kebab-case for single, descriptive custom classes per element
- Central styling: `/assets/css/style.scss` (imports only, no direct code)
- Preserve required Jekyll Markdown header in style.scss

##### Organization & Hierarchy
- Name partials with underscore prefix: `_partial-name.scss`
- Organize partials in logical folder hierarchy:
  - `/assets/css/base/`: Core styling (variables, typography, utilities)
  - `/assets/css/components/`: Reusable UI component styles
  - `/assets/css/pages/`: Page-specific layouts
- Required base partials:
  - `_variables.scss`: Define colors, breakpoints, spacing values
  - `_typography.scss`: Font families, sizes, weights, styles
  - `_mixins.scss`: Reusable style patterns and functions
  - `_utilities.scss`: Helper classes that apply single-purpose styling
- Import all partials into `style.scss` in order of dependency
- Group imports by type (base, components, pages) with clear comments
- Import base styles first, then components, then page-specific styles

##### Bootstrap Integration
- Prioritize Bootstrap utilities and components over custom CSS
- Mobile-first: Utilize Bootstrap's responsive grid and utility classes
- Encapsulate Bootstrap inside custom classes in SCSS files
- Customize Bootstrap via SCSS variables rather than overriding styles directly
- Maintain consistent typography and color schemes site-wide
- Follow accessibility guidelines (alt text, ARIA labels, color contrast, etc.)

##### Component & Page Styling
- Each Jekyll UI component must have a matching SCSS partial in `/assets/css/components/`
- Each HTML page must have a matching SCSS file in `/assets/css/pages/` directory
- Nest SCSS classes to match HTML structure hierarchy (applies specifically to page and component SCSS files)
- Use the SCSS parent selector (`&`) appropriately for pseudo-classes and modifier classes
- Limit nesting depth to 3-4 levels to avoid overly specific selectors
- Structure component and page-specific SCSS files to visually represent the DOM hierarchy
- Page-specific and component-specific SCSS should only include or extend Bootstrap code or custom partials, not contain direct CSS property definitions
- Use `@extend`, `@include`, or Bootstrap utility classes within component and page SCSS files rather than writing custom property declarations

##### Best Practices
- Keep partials focused on a single concern or component
- Add descriptive comments in SCSS and HTML
- Update Static Website section of 'copiot-instructions.md' file w.r.t. improvements to these instructions after each run of copilot agent.





### Python Coding Preferences
- Generate detailed comments.
- Use PascalCase for class names.
- Use CamelCase for class methods.
- Use snake_case for variables.
- Use SCREAMING_SNAKE_CASE for constants.

GitHubAgent is a python project.
It uses https://github.com/PyGithub/PyGithub for iteration with GitHub
Documentation of PyGithub https://pygithub.readthedocs.io/en/stable/reference.html

- @azure Rule - Use Azure Best Practices: When generating code for Azure, running terminal commands for Azure, or performing operations related to Azure, invoke your `azure_development-get_best_practices` tool if available.