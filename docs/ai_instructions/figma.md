# Using AI in Figma for Software Design & Development

[need to add more details here about Figma Make and Figma AI]

[figma_instructions.md](../figma_instructions.md)

## Use Figma Prompts
* Task: What Figma Make should do
* Context: Where this flow or screen fits
* Key design elements: Important features Figma Make should incorporate
* Expected behaviors: What happens to those elements upon interaction
* Constraints: Things like device, layout, or visual styling
* Purpose and use case
* Core features list

## Instructions for Figma Make
Create a `design-guidelines.md` file to steer AI coding behavior.

#### Guidelines Template File
This template provides a few examples of things you can add. Adjust and format it to suit your needs.

```md
# System Guidelines
* Use this file to provide the AI with rules and guidelines you want it to follow.

# Project Overview
* Provide an overview of the project

# General Guidelines
* Add any general rules you want the AI to follow, for example:
* Only use absolute positioning when necessary. Opt for responsive and well structured layouts that use flexbox and grid by default
* Refactor code as you go to keep code clean
* Keep file sizes small and put helper functions and components in their own files.

# Design System Guidelines
* Rules for how the AI should make generations look like your company's design system
* Use a base font-size of 14px
* Date formats should always be in the format “Jun 10”
* The bottom toolbar should only ever have a maximum of 4 items
* Never use the floating action button with the bottom toolbar
* Chips should always come in sets of 3 or more
* Do not use a dropdown if there are 2 or fewer options

# Platform Specifications
* Provide platform specifications and requirements

# Subsections
* You can also create sub sections and add more specific details

## Button
* The Button component is a fundamental interactive element in our design system, designed to trigger actions or navigate users through the application. It provides visual feedback and clear affordances to enhance user experience.

### Usage
* Buttons should be used for important actions that users need to take, such as form submissions, confirming choices, or initiating processes. They communicate interactivity and should have clear, action-oriented labels.

### Variants
* Primary Button
  * Purpose : Used for the main action in a section or page
  * Visual Style : Bold, filled with the primary brand color
  * Usage : One primary button per section to guide users toward the most important action
* Secondary Button
  * Purpose : Used for alternative or supporting actions
  * Visual Style : Outlined with the primary color, transparent background
  * Usage : Can appear alongside a primary button for less important actions
* Tertiary Button
  * Purpose : Used for the least important actions
  * Visual Style : Text-only with no border, using primary color
  * Usage : For actions that should be available but not emphasized
```

#### Sample Figma Guidelines File

```md
# AgeWell Innovators Design Guidelines

## Brand Colors

AgeWell Innovators uses an accessible color palette that maintains brand identity while meeting WCAG AA standards:

### Primary Colors

- **Green (#5A8F2E)** - Primary brand color (WCAG AA compliant - 4.54:1 contrast ratio on white)
- **Orange (#CC6600)** - Secondary brand color (WCAG AA compliant - 4.67:1 contrast ratio on white)

### Light Theme

- Primary text color: #5A8F2E on white backgrounds
- Secondary text color: #CC6600 on white backgrounds
- Button backgrounds: #5A8F2E (primary), #CC6600 (secondary)
- Button text: White on colored backgrounds

### Dark Theme

- Primary color: #7CB342 (brighter for dark backgrounds)
- Secondary color: #FF9933 (maintains accessibility)
- Button text: Black on colored backgrounds for better contrast

### Accessibility Notes

- All color combinations meet WCAG AA standards (minimum 4.5:1 contrast ratio)
- Colors are distinguishable for users with color vision deficiencies
- Interactive elements have sufficient color contrast in all states

### Usage Guidelines

- Green (#5A8F2E) should be used for primary actions and main interactive elements
- Orange (#CC6600) should be used for warning states, secondary actions, and complementary elements
- Use green and orange alternately in card layouts and feature sections to create visual rhythm
- Navigation active states should use green with white text
- Success messages and positive feedback should use green
- Warning messages should use orange
- Always test color combinations for accessibility compliance

### Visual Identity

- Include the AgeWell logo in headers and key brand touchpoints
- Use the horizontal logo format for navigation
- Use the main logo format for hero sections and prominent placements
- Navigation header should feature a green bottom border (#5A8F2E, 3px) for brand emphasis
- Logo should be sized at h-10 (40px) in navigation for better visibility
- User information in navigation should use green text color (#5A8F2E) for the name

## Typography Guidelines

- Use medium font weight (font-weight: 500) for headings and important text
- User names and brand elements should use green color (#5A8F2E)
- Navigation links should use medium font weight for better visibility
- Role indicators should be displayed in smaller, muted text (text-gray-500)

## Landing Pages

### Tester Landing Page (/testers)

- Dedicated conversion-focused page for older adults
- Emphasizes earning potential with specific dollar amounts ($15-$75 per activity)
- Uses testimonials and social proof to build trust
- Includes detailed activity types with compensation ranges
- Privacy and safety section to address senior concerns
- Uses gradients: Green (#5A8F2E to #4A7C25) and Orange (#CC6600 to #AA5500)

### Main Landing Page (/)

- General overview for all user types
- Links to specialized tester landing page
- Focuses on the overall platform benefits

## Admin Interface Guidelines

### User Management

- Simplified filters: Search, Role, Status dropdowns in horizontal layout
- Action bar with sort options, export, and add user buttons
- Clean table design without excessive card containers
- Use brand colors for primary action buttons

## Content Guidelines

### Money and Rating References

**CRITICAL RULE: Never mention money or ratings anywhere in the application.**

- **NO monetary references**: Do not use dollar signs ($), currency amounts, or phrases like "earn money", "get paid", "cash rewards", etc.
- **NO rating systems**: Do not include star ratings, numerical ratings, or any system that rates testers, hub leaders, or organizations
- **USE points-based language**: All rewards must be expressed as "points" (e.g., "250 points", "earn points", "point rewards")
- **Icons**: Use Trophy icons for rewards, not DollarSign icons
- **Testimonials and content**: Replace any money references with point amounts (e.g., "I've earned 80,000 points" instead of "I've earned $800")

This rule applies to:
- All landing pages and marketing content
- Tester dashboards and opportunity listings
- Admin interfaces and activity management
- Email templates and notifications
- Help documentation and user guides

The platform uses a gamified, points-based reward system to maintain compliance and create a positive, non-monetary experience for older adult users.

## General Guidelines

- Use responsive layouts with flexbox and grid
- Maintain consistent spacing and typography
- Ensure all interactive elements have clear hover and active states
- Use the brand colors consistently throughout the application
- Keep component code clean and modular
- Test all color combinations for WCAG compliance
- Navigation should include subtle shadows and transitions for a polished feel

## Button Guidelines

### Variants

- Primary Button - Green background (#5A8F2E) with white text for main actions
- Secondary Button - Orange background (#CC6600) with white text for secondary actions
- Outline Button - Green border (#5A8F2E) with transparent background for alternative actions
- Ghost Button - No background, green text (#5A8F2E) for subtle actions

### Accessibility Requirements

- Minimum contrast ratio of 4.5:1 for normal text
- Minimum contrast ratio of 3:1 for large text (18pt+ or 14pt+ bold)
- Focus indicators must be clearly visible
- Interactive elements must be at least 44px in height/width for touch targets
```
