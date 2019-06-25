## Feature Modules
* In angular every module other than AppModule is Feature Module.
* must declare all the components, directives and pipes
* import commonModule instead of Browser Module.
* Each view(scene) will have its own module.
* Each **View Module** can be lazy loaded(routing).
### Routing Module
* Each module should have its own **routing module**.
* Application is madeup of multiple feature modules.

## Core Module
* where to put all global services?
* services are  app scoped.
* Every lazy module has its own injector.
* keep all global services in core module, and import it only in AppModule.
* 

## Shared Module
* That need to be used across multiple areas(Features) of application.
* services and pipes are more commonly declared in shared module.
* Declare all feature and shared modules in CoreModule.


## APP STRUCTURE
├── APP
│   ├── CORE
│   │   └── COREMODULE
│   │       └── auth-user.md
│   ├── SHARED
│   │   └── SHAREDMODULE
│   │       └── components-pipes-directives.md
│   └── VIEWS
│       ├── CONTACTMODULE
│       ├── DASHBOARDMODULE
│       └── FEATUREMODULE
│           ├── CHILD-FEATURE-MODULES
│           ├── COMPONENTS
│           ├── ROUTINGMODULE
│           └── SERVICES


