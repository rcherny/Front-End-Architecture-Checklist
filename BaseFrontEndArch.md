
# Baseline Front End Architecture Checklist

  Note this is somewhat out of date.
  Updates coming soon ... a certain work in progress.

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

### Translation / Localization / i18n Requirements

    (Should probably move this section)

 * Does the site need to be in multiple languages?
 * What is the plan for how that content will be maintained?
 * Consider localization impact on CSS/JS

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


## Process

### Requirements Definition
 * Deliverables to iDevs
 * Backend data / services
    * Mock data / Stubs / sample data
    * Timeframe?
 * Wireframes
 * All applicable widget "states"
 * Designs

### Schedule
 * Were there assumptions as to when front end code would be integrated?
    * Before (or after) xyz?

### Critical Aspects
 * Must define global styles
 * Must define 


## Environments

### Servers

 * Local Development 
 * Shared Development Servers
 * Staging Servers
 * QA Servers

### Builds

 * Please see Continuous Integration
 * Please see Builds and Deployments

## Baseline Front End Architecture
 * JS
    * Libraries and Frameworks
 * CSS
    * Libraries and Frameworks
 * Img

## HTML

### Doctypes and Rendering Modes
 * Integration with server tools (see above)
 * MSIE Rendering modes
    * Does the server environment specify a rendering mode for IE?
    * Are they on the compatibility list from Microsoft?

### Templates / Server Pre-Processing
 * Client side templates?
 * Server side templates?
 * Relationship to Builds and Dependency Managment (see other topics)

### HTML5 Tag Usage
 * Modernizr / Shiv

### Grid System
 * See CSS
 * See Mobile


## Cascading Style Sheets

### Division of Concerns
 * Site Design
 * Brand
 * Page or Section Specific code

### Frameworks
 * Bootstrap
 * Grids
 * Resets
 * Normalize
 * SMACSS
 * OOCSS

### Hacks vs. CSS3 vs. IE

### Fonts & Typography
 * Strategy
 * Cross Domain Concerns

### Server Pre-Processing Tools
 * SASS
 * LESS

### Output
 * All CSS at all times?
 * Dependency Management
 * How are &lt;link&gt; tags rendered?

### Printing Requirements

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

  This is a huge topic. Many, many more notes to come.

Bottom line, it has been said the best way to build a large scale JavaScript application is to NOT build a large scale application.
(**attribution needed**)

From "[Large Scale JS Applications](http://addyosmani.com/largescalejavascript/)":

> We want a loosely coupled architecture with functionality broken down into independent modules with ideally no inter-module dependencies. Modules speak to the rest of the application when something interesting happens and an intermediate layer interprets and reacts to these messages.

### Namespaces
 * What namespace structure will be used?

### Globals / Exports
 * Will a dependency management tool impact the way the code should be written?
 * Will style preference impact the way the code should be written?

### Code Style Standards
 * Are there coding guidelines in place?
 * Style guidelines?

### Pattern Usage
[JavaScript Patterns](http://addyosmani.com/resources/essentialjsdesignpatterns/book/)

 * Module Pattern (e.g. Simple, or Revealing)
 * Singletons
 * Observers / Publish-Subscribe
 * Mediators
 * Facades
 * Command Pattern
 * Factory
 * Mixin
 * Decorator

### Patterns of Scale
 * MVC
 * MVP
 * MVVM

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
 * Tools
   * Async Loaders 
     * RequireJS
     * Curl.js
     * Yepnope.js
     * Head.js
     * Lab.js
   * CommonJS / AMD

### Libraries / Frameworks
 * jQuery / jQuery UI
 * MVC Frameworks
    * Backbone.js
    * Spine.js
    * JavascriptMVC
    * AngularJS
    * YUILibrary
    * Ext.js
    * Dojo
    * Closure
    * Ember.js
 * Server Side (e.g. Node.js)

### Plugins / Widgets
 * Specific UI requirements
 * Richness of API or footprint
 * Bundled widgets?
   * Usually from backend server technology
 * Translations

### Translations in JS
 * (please see Translations / Localization / i18n above)
 * Avoid putting raw strings in JS
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

### Build & Deployment
 * Platform considerations
 * Developers desktops, build tools, deployment
 * Testing in builds (see Unit Testing below)

### Environments
 * Different settings / files for different environments
 * How many?
 * Where will code have to run?


## Unit Testing

### TDD
 * Jasmine
 * QUnit
 * Other...

### Visual
 * Design
 * CSS

### JSLint / JSHint
 * See Builds (above)


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


## Tools
 * Expected IDEs
 * Project File Types


