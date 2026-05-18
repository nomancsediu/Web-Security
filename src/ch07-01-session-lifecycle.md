# Session Lifecycle

A web session has a well-defined lifecycle: creation, maintenance, and destruction. Understanding each phase is essential for implementing secure sessions.

## Session Creation

Sessions are typically created when a user authenticates. The server generates a unique session identifier and stores it as a cookie in the user's browser. The session ID must be unpredictable and sufficiently long to resist brute-force attacks.

## Session Maintenance

During an active session, the server must validate the session ID with each request. Best practices include regenerating the session ID after privilege level changes (such as login) and implementing session timeouts.

## Session Destruction

Sessions should be properly destroyed on logout, including invalidating the session ID on the server side and clearing the session cookie. Simply clearing the client-side cookie is not sufficient.
