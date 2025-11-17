# Rishikesh Bhyri - Personal Portfolio

This is my personal portfolio website built with Jekyll and the Minimal Mistakes theme.

## Features

### Light/Dark Theme Toggle
- **Toggle Button**: Located in the navigation bar (masthead) with sun/moon icons
- **Persistent Preference**: Theme choice is saved in localStorage and remembered across sessions
- **Smooth Transitions**: All elements transition smoothly between light and dark themes
- **Mobile Responsive**: Theme toggle works seamlessly on mobile devices
- **Accessibility**: Proper ARIA labels and keyboard navigation support

#### Theme Colors
- **Light Theme**: Clean white background with dark text and subtle borders
- **Dark Theme**: Dark background (#1a1a1a) with light text and enhanced contrast
- **Code Highlighting**: Syntax highlighting adapts to both themes
- **Navigation**: Mobile menu and dropdowns adapt to theme changes

#### Implementation Details
- CSS variables for consistent theming across all components
- JavaScript handles theme switching and localStorage persistence
- Responsive design ensures the toggle works on all screen sizes
- Follows the project's coding standards with proper comments and documentation

## Getting Started

1. Clone the repository
2. Install dependencies: `bundle install`
3. Run locally: `bundle exec jekyll serve`
4. Visit `http://localhost:4000`

## Customization

The theme toggle can be customized by modifying:
- `_sass/theme/_default.scss` - Theme color variables
- `_sass/layout/_masthead.scss` - Toggle button styles
- `assets/js/_main.js` - Toggle functionality
- `_includes/masthead.html` - Toggle button HTML

## License

This project is licensed under the MIT License.
