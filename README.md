# Express.js Route: Missing Error Handling for Invalid User IDs

This repository demonstrates a common error in Express.js route handlers:  lack of error handling for invalid input.  The example shows a route that retrieves a user by ID.  The original code fails to handle cases where the provided ID is not a valid integer, potentially leading to application crashes or unexpected behavior.

The solution demonstrates robust error handling to catch and gracefully manage invalid input, preventing application failures and providing informative error responses to the client.

## Bug

The `bug.js` file contains the flawed code. It attempts to parse the user ID as an integer without validating that the input is indeed an integer.  If a non-integer ID is passed, `parseInt` may return `NaN`, causing unexpected behavior or a crash depending on how the later code handles it. Additionally, even if a `user` is not found the response is a generic 404 without details.

## Solution

The `bugSolution.js` file presents the corrected code with improved error handling. It validates the user ID before attempting to parse it, and returns more informative error responses to the client using proper HTTP status codes.