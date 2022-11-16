
The more our tests resmble the way our software is used, the more confidence they'll give.

Utilities are included in this project based on the following guiding principles:

1. If it relates to rendering components, then it should deal with DOM nodes rather than component instances, and it should not encourage dealing with component instances.
2. It should be generally useful for testing the application components in the way the user would use it. We are making some trade-offs here because we're using a computer and often a simulated browser environment, but in general, utilities should encourage tests that use the components the way they're intended to be used.
3. Utility implementations and APIs should be simple and flexible.
