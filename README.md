
# Fait
Standardized Handler Composition

## Where did this come from?
Developers start as rebels, they don't understand what they see or what they are told and so they rebel and make something new that already existed at one tenth the quality -- typical junior developer. Medium experience and many senior developers are conformist. They have learned that doing it themselves was dumb and now they follow the getting started guide like its gospel. The next level of experience -- often referred to as senior but this is typically beyond the typical senior developer bar -- reverts back to rebeliousness. Senior engineers (no longer referred to as developers at this level) see the pros and cons to the common design patterns and getting started guides, they understand the downside of using a library as instructed, and they have the capacity and ability to implement systems, tools, and patterns in near-hack formats that bring improved usefulness and stability to all involved.

## What is Fait?

FAIT (VC)

1. Framework Agnostic. Handlers should have no knowledge of, and have no care or interest, in the tooling or frameworkds that support request delivery at lower layers. This means the components that make up a handler should not know that node express is delivering the request and the response.

2. Isolation. The business logic should be both isolated and easily found. In an API every endpoint contains business logic. In most cases this business logic is strung together along with request parsing, validation, marshalling. These things belong in modules, easily available for reuse, so that all that is left is in fact the actual business logic.

3. Testability. Your handler -- namely your business logic -- should be testable. Your business logic should be easily testable without running or executing any of the isolated modules that handle standard request/response work. Your handler should accept all outside resources that maintain their own state as arguments so testing is a simple matter of mocking objects and calling functions.

4. Visibility. The entirety of a handler should be visible in a single location (i.e. request and response types, requiered argment, routes, method, business logic, auth reqs., argument validation -- everything that someone who may want to make a request to the handler would want or need to know to do so.) A simple glance at a single file should tell this person all they need to know about that handler or endpoint.

5. Composable. The coponents that make up handlers should provide the ability to be mindlessley interchanged, repositioned, and reconfigured into different handlers with different behaviors.


## Scaling across large projects

family -> unit -> handler