# IoC vs DI vs ServiceLocator  
* Short Stack answer: [Link](https://stackoverflow.com/a/6551303/6708274)  
* [Other link](https://gridwizard.wordpress.com/2014/05/28/dependency-injection-vs-service-locator/)  
* Short answer:
	* IoC vs DI (Dependency Injection)? IoC is the general concept where control of flow is *Inverted* from client code to framework, which “Does something for the client”.
	* SL (Service Locator) and DI (Dependency Injection) are two design patterns stem off from IoC.
* In case of DI (Dependency Injection), the application framework returns to client pre-configured dependencies. Dependencies are configured by way of Constructor|Setter|Method “Injection” – Injection is just a big word for simply “Setting member variables” via Constructor|Setter|Method.
* In case of SL (Service Locator), the application framework, containing all services instances, returns relevant Service instance by looking up a map, with a *key* specified by client. Service Locator which is basically a map.