# Links

## Backend

### Utils

- [sails-hook-autoreload](https://github.com/sgress454/sails-hook-autoreload)
> Sails JS hook to autoreload controllers, models, services and locales when changed.
> This hook is to help with situations where you are rapidly prototyping/tinkering with app code and don't want to have to keep quitting/restarting Sails to see your changes. It is not intended to be used in a production environment.

### API

- [generator-sails-rest-api](https://github.com/ghaiklor/generator-sails-rest-api)
> Yeoman generator for scaffolding Sails REST API with predefined features.
    
- [shortid](https://github.com/dylang/shortid)
> Short id generator. Url-friendly. Non-predictable. Cluster-compatible.

- [sails-hook-pagify](https://github.com/colintoh/sails-hook-pagify)
> Generate pagination data and metadata for Sails JS projects.

- [sails-hook-blueprint-count](https://github.com/kristian-ackar/sails-hook-blueprint-count)
> Adds blueprint api method to count records in database.

- [sails-hook-query-builder](https://github.com/caljrimmer/sails-hook-query-builder)
> Sails hook for creating waterline queries from request queries.
> Query builder adds a static method to all models in a sails app that allows creates a query which will paginate, search and sort.

- [node-rss](https://github.com/dylang/node-rss)
> RSS feed generator. Add RSS feeds to any project. Supports enclosures and GeoRSS.

### Models

- [sails-hook-validation](https://github.com/lykmapipo/sails-hook-validation)
> Custom validation error messages for sails model with i18n support.

- [sails-hook-model-extra](https://github.com/lykmapipo/sails-hook-model-extra)
> Additional model methods for sails.
> The following methods will be added to all models once hook is installed.
>
> `countAndFind(criteria, callback)`
> `countAndSearch(searchTerm, callback)`
> `first(howMany, callback)`
> `last(howMany, callback)`
> `search(searchTerm, callback)`
> `softDelete(criteria, callback)`

### Security

- [sails-hook-allowed-hosts](https://github.com/elssar/sails-hook-allowed-hosts)
> Sails hook to ensure requests can only come in from a whitelisted set of hosts.
    Works with both hosts and IP adresses.

### Seeding

- [sails-hook-fixtures](https://github.com/arryon/sails-hook-fixtures)
> Installable hook that injects fixtures into your sails ORM at runtime. With associations!

### Logging

- [sails-hook-events](https://github.com/Dreamscapes/sails-hook-events)
> Use events to manage and observe Waterline models' lifecycle
> This hook allows you to use event-driven programming when working with your Waterline models. It adds new events emitted from your Sails.js instance that you can subscribe to and perform actions when such an event is emitted.

- [sails-hook-winston](https://github.com/Kikobeats/sails-hook-winston)
> Integrates winston logging system with your Sails application.
    
### Plugins
- [marlinspike](https://github.com/tjwebb/marlinspike)
> Superpowers for your Sails.js Hooks.
> Makes it easy to build and maintain Sails Hooks as separate projects.
> Magically extend Sails apps with additional Model, Controllers, Services.

### Analytics

- [sails-hook-apianalytics](https://github.com/mikermcneil/sails-hook-apianalytics)
> A Sails hook for logging detailed request metadata and monitoring your API.
    
## Frontend

### SDK

- [sails.io.js](https://github.com/balderdashy/sails.io.js)
> Browser SDK for communicating w/ Sails via sockets.
> The sails.io.js client comes automatically installed in new Sails projects, but there is nothing project-specific about the client SDK. You can just as easily copy and paste it yourself, get it from Bower, or just link a script tag directly to a hosted CDN.