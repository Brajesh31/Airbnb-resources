# API and External Service Boundaries

## 1. Current status

There is no API in this repository. The page is delivered as static HTML, CSS, and local media files. It does not make application requests to Airbnb or another accommodation data provider.

There are no:
- REST or GraphQL endpoints;
- API client modules;
- authentication tokens;
- API keys;
- server-side routes;
- webhooks;
- live inventory or availability requests;
- payment provider integrations.

This is an intentional description of the current implementation, not an unfinished API specification.

## 2. What the interface displays

Listing-like content is embedded in the HTML. Labels, prices, distances, dates, and property descriptions are sample content. They are not retrieved from a service, verified against a live source, or suitable for making a booking decision.

Do not describe a displayed price as current or a property as available.

## 3. No credentials required

The current page does not require an API key, access token, client secret, or environment variable. Never add credentials to HTML, CSS, committed JavaScript, README examples, or public repository files.

A browser-delivered secret is not secret. Any credential embedded in static client assets can be inspected by visitors.

## 4. Requirements before adding an API

An API integration would be an architecture change. Before implementation, document:

1. **Use case:** What user problem requires remote data?
2. **Provider:** Who owns the API and what are its terms of use?
3. **Endpoint contract:** Method, path, query parameters, headers, request schema, and response schema.
4. **Authentication:** Credential type, storage location, rotation, and least-privilege scope.
5. **Validation:** How malformed and untrusted values are handled.
6. **Errors:** Timeouts, unavailable service, invalid responses, rate limits, and user-facing fallback.
7. **Privacy:** Data collected, purpose, retention, deletion, and disclosure.
8. **Security:** Transport security, authorization, abuse prevention, logging, and secret management.
9. **Reliability:** Retry rules, caching, rate limits, and provider outage behavior.
10. **Testing:** Unit, integration, contract, and failure-mode tests.
11. **Operations:** Ownership, monitoring, incident response, and provider changes.
12. **Licensing:** Whether the provider permits the intended use and redistribution.

## 5. Browser-to-provider considerations

If a future provider requires a confidential credential, the browser should not receive that credential. A server-side component or trusted serverless function may be required. That would introduce hosting, runtime, security, and deployment responsibilities that do not currently exist.

CORS is not an authentication mechanism and should not be treated as a way to protect an API key.

## 6. API documentation template for a future service

For each endpoint, record:
- purpose and owner;
- HTTP method and path;
- authentication requirements;
- request fields and validation;
- success response and example;
- error responses and status codes;
- pagination and rate limits;
- caching behavior;
- privacy and retention implications;
- versioning and deprecation policy;
- automated test coverage.

Do not add empty endpoint tables or fictional response examples to this repository while no API exists.

## 7. Related documentation

See [Architecture](architecture.md) for the current request lifecycle, [Security](security.md) for credential handling, [Privacy](privacy.md) for data boundaries, and [Database](database.md) for the absence of persistence.
