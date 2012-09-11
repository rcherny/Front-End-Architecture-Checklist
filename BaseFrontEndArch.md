---
layout: main
title: Baseline Front End Architecture - The Checklist
---

# Baseline Front End Architecture Checklist

This document is a living document that is still going through revisions.

## General

General high level overview of front end technology considerations while building a Web site or Web application.

### Getting Started
 * Type of site
    * Marketing
    * Content
    * Content Management
    * Application / Content mix
    * Single page app
    * Offline
    * Mobile, etc.
 * Size of site
 * Target audience
    * Technology assumptions
    * Browsers
    * JavaScript
    * Accessibility, etc.
 * Technology platform(s)
 * Timeframe
 * Development / PM methodology
    * Initial estimates
    * Staffing expectations
 * Be prepared with site framework, build tools, etc. (more below)
    * Time required for initial set up is often overlooked
 * Expected Deliverables and Tasks
    * Build kits
    * Working site
    * Integration Consulting
    * Actual Integration

### Backend: View Rendering Technology
 * How is the front end to be rendered with this technology?
 * Who does the integration with the back end?
 * Are there "Products" or "frameworks" involved that claim all they need is a "theme" applied?
 * Are there pre-built widgets at work? (see JS below)
    * CMS?
    * Portal?
    * Community software?
    * Sharepoint?
 * Will any of the views be rendered on the front end?
 * Will there be control over the markup?
 * Have this technology been worked on before?
 * Is prototyping of design integration required?

### Legacy Code
 * Is integration with legacy code bases necessary?
 * Will any code being created have to be "portable" or "shared"?

### Key Integration Points
 * Servers
 * Domains (multiple domains ultimately)
 * Third Parties
 * Social
 * Widgets
 * Other Applications
 * Coding Guidelines

### Browser Specs
 * Degradation Style
 * Backwards Compatibility Policy

### Mobile/Tablet Support
 * Any defined requirements?
 * Was it included in cost?
 * Should there be?
 * Separate site? 
 * Responsive Site?
 * Required Platforms
 * Testing Suites

### SEO
 * URL requirements
 * Deep linking requirements

### Content Delivery Services (CDN)
 * Will a CDN be used in the final environment?
 * Will this impact cached code / updated code?

### Translation / Localization / i18n Requirements
 * Does the site need to be in multiple languages?
 * What is the plan for how that content will be maintained?
 * Consider localization impact on CSS/JS (see below)
 * Will translations be handled "on the fly" or will users be "redirected" to unique sites?


## Process

### Requirements Definition
 * Expected deliverables to Front end developers
 * Expected deliverables from Front end developers
 * Front end developer Design Review
   * Feedback on designs prior to client sign-off
   * Can the process be iterative with design?
   * Will there be prototypes or proofs of concepts?
 * Backend data / services
    * Mock data / Stubs / sample data
    * Timeframe vs. front end development?
 * Wireframes
 * All applicable widget "states"
   * Errors
   * Warnings
   * Hide/show
 * Designs

### Schedule
 * Were there assumptions as to when front end code would be integrated?
   * Before (or after) xyz?

### Critical Elements
 * Must define global styles in design as early as possible
 * Must understand environments for usage of front end code as early as possible
 * Must understand and define browser fall-back/behavior as early as possible

## Environments

### Servers
 * Local Development 
 * Shared Development Servers
 * Staging Servers
 * QA Servers

### Developers
 * What types of environments will developers have access to?
 * How will shared code and parallel development be managed?
 * Will there be full local environments available?

### Tools
 * Expected IDEs
 * Project File Types

### Builds
 * Please see Continuous Integration
 * Please see Builds and Deployments


## Baseline Front End Architecture
 * Are there coding standards or guidelines to be followed?
 * Having a clear approach, structure, system, or "approach" is critical.
 * Where does new code get added?
   * How is it executed?
   * How is it included?
   * More info under each particular technology
 * JS
    * Will usage of specific Libraries and Frameworks be required, or helpful?
    * Folder structure
 * CSS
    * Will usage of specific Libraries and Frameworks be required, or helpful?
    * Folder structure
 * Img
   * Does the client "care" about things like transparent PNG images in older versions of IE?
   * Folder structure
 * Will content management come into play?
   * Will authors need to "format" HTML and CSS in certain cases?
   * What about application of CSS and HTML to uploaded assets?
   * Rich text editors?

## HTML

### Doctypes and Rendering Modes
 * Integration with server tools, products, software (see above)
 * MSIE Rendering modes
    * Does the server environment specify a rendering mode for IE?
    * Are they on the compatibility list from Microsoft?
    * Can HTTP headers be set from the server?

### Templates / Server Pre-Processing
 * Client side templates?
 * Server side templates?
 * Pre-compilation?
 * Relationship to Builds and Dependency Managment (see other topics)

### HTML5 Tag Usage
 * Polyfills needed, what types?
 * Does it address the IE printing issues?

### Grid System
 * See CSS
 * See Mobile


## Cascading Style Sheets

Having a "System" is critical.

### Division of Concerns
 * Site Design
 * Brand
 * Page or Section Specific code

### CSS Frameworks
 * Will a pre-built framework help?
 * What about a Grid system?

### Hacks vs. CSS3 vs. IE
 * What type of approach is being used?
 * Can older browsers just "not see" these effects?
 * Do we need polyfills for everything?
 * Should the design change?

### Fonts & Typography
 * Strategy / Content management/entry
 * Cross Domain Concerns

### Server Pre-Processing Tools
 * Dynamic CSS libraries?
 * Developer environments?
 * Build environments?
 * Extent of use? (a lot, a little, etc.)
 * Best practices ... 

### Output
 * All CSS at all times?
 * Dependency Management
 * How are &lt;link&gt; tags rendered / HTML updated?
 * Is there a Cache and Cache-busting strategy?

### Printing Requirements
 * Do particular pages need to be printed?
 * What level of detail?
 * Are there exceptions?

### Folder Structure
 * Core Styles
 * Site Sections

### Naming Conventions
 * Files
 * Selectors

### Sprites
 * Creation and Dev
 * Maintenance


## JavaScript

Having a "System" (i.e. architecture) is critical.

Bottom line, it has been said the best way to build a large scale JavaScript application is to NOT build a large scale application.

From "[Large Scale JS Applications](http://addyosmani.com/largescalejavascript/)":

> We want a loosely coupled architecture with functionality broken down into independent modules with ideally no inter-module dependencies. Modules speak to the rest of the application when something interesting happens and an intermediate layer interprets and reacts to these messages.

### Namespaces
 * Is the global scope an issue?
 * What namespace structure will be used?

### Globals / Exports
 * Will a dependency management tool impact the way the code should be written?
 * Will style preference impact the way the code should be written?

### Code Style Standards
 * Are there coding guidelines in place?
 * Style guidelines?

### Code Growth

Before arbitrarily adding code, libraries, new modules, consider:

 * Is there a module that does this already?
 * Which script file should this functionality exist within? 
 * Should this feature be abstracted so that other modules can use this code? (e.g. Modals, tooltips, validation)
    * Bottom line, is this code core business logic, or for widgets, controls, re-usable logic, presentation layer?
 * How should we link to this script?
 * What dependencies will exist?

#### Adding New Code
 * When new code is added, is it obvious where it will be added?
 * Can it leverage code that exists already?
 * Is an MVC pattern the best approach, or something else?

### Dependency Management
 * How large will this app get?
 * Where will it be handled?
   * Manually
   * Part of the code
   * Client side
   * Part of builds
   * Server side
 * See build process
   * Part of build process
   * Manually managed
 * Strict dependency management? 
   * per page
   * per site section
   * for all pages

### Libraries / Frameworks
 * What functional requirements drive the assumed or required library usage?
 * What are the longer term conditions that this code will need to deal with?

### Plugins / Widgets
 * Specific UI requirements
 * Mobile users?
 * Richness of API or footprint
 * Bundled widgets?
   * Usually from backend server technology
 * Translations

### Translations in JS
 * (please see Translations / Localization / i18n)
 * Raw string usage in JS
 * Where will the strings be sourced from?
 * How will they be delivered to the front end vs. the build process?

### Domains
 * (see integration above)
 * Any cross domain considerations?
 * CORS
 * Backwards compatible libraries


## Images

### Folder Structure

### Naming Conventions

### Sprites
 * See CSS (above)

### Lossless Optimization
 * Manually done
 * Build time
 * Real time


## Continuous Integration
 * Will there be a complex back-end build process required?
 * Should the front end code base be included in this?

### Front End Code Builds
 * Minification and Concatenation of CSS
   * Will there be any preprocessing?
 * Minification and Concatenation of JS
 * Locally performed?
 * Automated as part of backend build?
 * Both?
 * Cache strategy, or Cache busting strategy?
 * How will files be updated to point to built file versions?

### Build & Deployment
 * Platform considerations
 * Developers desktops, build tools, deployment
 * Testing in builds (see Unit Testing below)

### Environments
 * Different settings / files for different environments
 * How many?
 * Where will code have to run?
 * Different types of developers, testing, continuous integration, etc.


## Unit Testing

### TDD
 * Is this a requirement?
 * Is there time?
 * What patterns should be followed by coders to facilitate this?
 * Will tests be done locally, as part of the builds, or other?

### Content & Visuals
 * How will visual design be QA'd?
 * Content?
 * Translations?
 * Browser testing?
 * Mobile devices?


## Deployment
 * Launch day considerations
 * Testing
 * Support
 * Hot fixes / patches


## Post Launch Development
 * Post-launch day Hot Fixes
 * Parallel tracks
   * Version Control
   * New feature work
 * Resources and priorities
 * Client involvement

### Long Term Site Development
 * Who will maintain the site's content, and how?
 * Who will own ongoing development of the site?



