# Express.js Route Handler Missing Error Handling for Invalid User IDs

This repository demonstrates a common error in Express.js route handlers: the lack of error handling for invalid input.  The `bug.js` file shows a route that attempts to parse a user ID as an integer without checking for potential errors (e.g., non-numeric IDs). This can lead to crashes or unexpected behavior.

The `bugSolution.js` file provides a corrected version with proper error handling, demonstrating how to prevent these issues and gracefully handle invalid input.

## How to Reproduce the Bug

1. Clone this repository.
2. Run `npm install` to install the dependencies.
3. Run `node bug.js`.
4. Send a request to `/users/abc` (or any non-numeric ID). You will see an error, such as `NaN` related error.

## How the Solution Works

The solution adds error handling to validate that the `userId` is a number before using it.  It uses `isNaN` function to check whether the value is a number. If it's not, it sends a 400 Bad Request response. If it's valid, it proceeds with the rest of the logic, improving the robustness of the application.
