1. Clone sample app
2. Discuss package.json, dependencies, script & demo
3. Framework for creating application in HTML, JS / TS. Core and optional libraries
4. Architecture
  - Modules - Every ng App has least one Module called root module (bootstrapped), ng has its own modular system called ngModules. ng module is a class with @NgModule decorator. NgModule is a decorator 
  - Component - controls the page or section on page.
  - Template - is HTML containing angular template syntaxes. Angular uses template to render component.
  - Metadata - tells angular how to process a class.
  - Databinding - is core to angular. enables to bind component property to and or from component to view. Angular processes all databinding once per JS event cycle, from root component to child.
  - Directive - is class with @Decorator. Component is technically a "directive" with a template. Structural (modify DOM) & attribute (appearance or behaviour of element) directive.
  - Services - includes value, function or feature that app needs.
  - Dependency injection - provides required services to components. Providers enlist the services with injector. Services in root module will have single instance across app, while services in component are created when new instance of component is created.
