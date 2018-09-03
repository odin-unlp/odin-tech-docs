# Utils

- [nodemon](https://github.com/remy/nodemon)
> Tool to autoreload controllers, models, services and locales when changed.
> This tool is to help with situations where you are rapidly prototyping/tinkering with app code and don't want to have to keep quitting/restarting Sails to see your changes. It is not intended to be used in a production environment.

# API

- [generator-sails-rest-api](https://github.com/ghaiklor/generator-sails-rest-api)
> Yeoman generator for scaffolding Sails REST API with predefined features.

- [shortid](https://github.com/dylang/shortid)
> Short id generator. Url-friendly. Non-predictable. Cluster-compatible.

- [sails-hook-blueprint-count](https://github.com/kristian-ackar/sails-hook-blueprint-count)
> Adds blueprint api method to count records in database.

- [node-rss](https://github.com/dylang/node-rss)
> RSS feed generator. Add RSS feeds to any project. Supports enclosures and GeoRSS.

# Models

- [sails-hook-validation](https://github.com/lykmapipo/sails-hook-validation)
> Custom validation error messages for sails model with i18n support.

- [sails-hook-model-extra](https://github.com/lykmapipo/sails-hook-model-extra)
> Additional model methods for sails.
> The following methods will be added to all models once hook is installed.

```javascript
countAndFind(criteria, callback)
countAndSearch(searchTerm, callback)
first(howMany, callback)
last(howMany, callback)
search(searchTerm, callback)
softDelete(criteria, callback)
```

# Security

- [sails-permissions](https://github.com/langateam/sails-permissions)
> Comprehensive user permissions and entitlements system for sails.js and Waterline. Supports user authentication with passport.js, role-based permissioning, object ownership, and row-level security.

- [sails-hook-allowed-hosts](https://github.com/elssar/sails-hook-allowed-hosts)
> Sails hook to ensure requests can only come in from a whitelisted set of hosts.
    Works with both hosts and IP adresses.

# Seeding

- [sails-hook-fixtures](https://github.com/arryon/sails-hook-fixtures)
> Installable hook that injects fixtures into your sails ORM at runtime. With associations!

# Logging

- [sails-hook-events](https://github.com/Dreamscapes/sails-hook-events)
> Use events to manage and observe Waterline models' lifecycle
> This hook allows you to use event-driven programming when working with your Waterline models. It adds new events emitted from your Sails.js instance that you can subscribe to and perform actions when such an event is emitted.

- [winston](https://github.com/winstonjs/winston)
> A multi-transport async logging library for node.js.

- [sails-hook-winston](https://github.com/Kikobeats/sails-hook-winston)
> Integrates winston logging system with your Sails application.

# Plugins

- [marlinspike](https://github.com/tjwebb/marlinspike)
> Superpowers for your Sails.js Hooks.
> Makes it easy to build and maintain Sails Hooks as separate projects.
> Magically extend Sails apps with additional Model, Controllers, Services.

# Analytics

- [sails-hook-apianalytics](https://github.com/mikermcneil/sails-hook-apianalytics)
> A Sails hook for logging detailed request metadata and monitoring your API.

For more info about used packages lookup the package.json file inside project
