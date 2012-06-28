Title: BaseFrontEndArch
Timestamp: 2012-06-07 23:00:17 +0000
Created: 2012-05-15 21:52:38 +0000
Last Accessed: 2012-06-07 23:00:23 +0000
Times Accessed: 10
Tags: 
Metadata: 
# Baseline Front End Architecture Checklist

General high level overview of front end technology considerations while building a Web site or Web application.

    Note this is somewhat out of date.
    Updates coming soon ... 

## General

 * Type of site
 * Technology overview
 * Timeframe

### Backend-View Technology
 * How is the front end rendered?
 * Are there pre-built widgets at work? (see JS below)
   * CMS? Portal? Community software?
 * Will any of the views be rendered on the front end?
 * Will there be control over the markup?

### Legacy Code
 * Is integration necessary?

### Integration Points
 * Servers
 * Domains (multiple domains ultimately)
 * Third Parties
 * Social
 * Widgets

### Post Dev Integration
 * Is our code to be integrated or used by third parties?
 * Coding Guidelines (?)

### i18n Requirements

 * Does the site need to be in multiple languages?
 * What is the plan for how that content will be maintained?

### High Level Location of FE Code
 * JS
 * CSS
 * img

### Browser Specs
 * Degradation Style
 * Backwards Compatibility Policy

### Mobile/Tablet Support
 * Any defined requirements?
 * Was it included in cost?
 * Should there be?

### SEO
 * URL requirements?
 * Deep linking requirements?

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

## Performance Metrics
 * Expectations?
 * Available configurations (web server, etc)

## HTML

### Doctype
 * Integration with server tools (see above)

### Templates / Server Pre-Processing
 * Client side templates?
 * Server side templates?

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

### Style Standards

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
 * (see i18n above)
 * Avoid putting raw strings in JS
 * Where will the strings be sourced from?

### Domains
 * (see integration above)

## Images

### Folders

### Naming Conventions

### Sprites
 * See CSS

### Lossless Optimization

## Continuous Integration

 * Will there be a complex back-end build process required?
 * Should the front end code base be included in this?

### Manual Processing

Front end code builds

 * Locally performed?
 * Automated as part of backend build?
 * Both?

### Build & Deployment

 * Platform considerations
 * Developers desktops, build tools, deployment

### Environments
 * Different settings / files for different environments
 * How many?
 * Where will code have to run?

## Unit Testing

### TDD
 * Jasmine
 * qUnit

### Visual
 * Design
 * CSS

### JSLint / JSHint

## Deployment

### Post launch development

### Hot fixes

### Resources and Concurrent Work

### Long Term Site Development

 * Who will maintain the site's content, and how?
 * Who will own ongoing development of the site?

## Tools
 * Expected IDEs
 * Project File Types
