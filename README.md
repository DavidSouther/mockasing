# Mockasing

Extensions to Angular Mocks.

## API

### **render**(*html*, *data*, *parent*)

Returns a rendered Angular Element, compiled from `html`, rendered with
`data`, and appended to `parent`.

### **renderElement**(*tag*, *data*, *attributes*, *transclude*, *parent*)

Utility to create `html` from the `tag`, `attributes`, and `transclude` before
rendering with `render`. If `parent` is present and is an `angular.element`, the
template will be appended as a child. Useful for testing directives like
`ng-repeat`, where otherwise the returned element would be just the first
comment in the rendered repeater.

### **mockBackend**(*backendData*, *afterEach*)

Pre-load backend data to $httpBackend. Keys in *backendData* are string API
paths, whose values are either string JSON response data or an object with
`{status: StatusCode, body: data }` where StatusCode is the desired HTTP status
code, body is either a string JSON or an object to be JSON strifigied, and the
default status is `200`. If `afterEach` is provided, will register
`$httpBackend.verifyNoOutstandingExpectation` and
`$httpBackend.verifyNoOutstandingRequest` in that function.

## Changelog

* **0.1.2** *2014-01-09* Bumped all children.
* **0.1.1** *2015-01-09* Moved httpBackend to mockBackend.
* **0.0.3** *2014-10-10* Added httpBackend helper.
* **0.0.2** *2014-10-09* Publishing Snafu.
* **0.0.1** *2014-10-09* Render functionality.
