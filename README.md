# Express.js Route Handler Missing Error Handling for Invalid User ID

This repository demonstrates a common error in Express.js route handlers: missing error handling for invalid input. The example shows a route that fetches a user by ID.  If the ID is not a valid number, the application will crash without proper error handling.

The `bug.js` file contains the erroneous code, while `bugSolution.js` provides a corrected version with appropriate error handling.

## Bug
The original code attempts to parse the user ID as an integer using `parseInt()`. However, it fails to handle the case where the ID is not a valid integer (e.g., a string, null, or undefined). This can lead to unexpected application behavior or crashes.

## Solution
The solution involves adding error handling to gracefully manage invalid input.  The improved code checks if `parseInt(userId)` returns `NaN` before using it to find the user, and returns a 400 Bad Request error if the ID is invalid.