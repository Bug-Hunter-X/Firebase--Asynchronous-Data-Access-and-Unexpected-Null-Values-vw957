# Firebase Asynchronous Data Access and Unexpected Null Values

This repository demonstrates a common error in Firebase applications: accessing properties of a Firestore document snapshot before the snapshot is fully populated. This can lead to unexpected errors and crashes, especially when dealing with asynchronous operations.

The `bug.js` file shows the erroneous code, which attempts to access a property that might not yet exist. The `bugSolution.js` file demonstrates the corrected code, which includes checks for null or undefined values before accessing the property.

## Reproduction Steps

1. Clone the repository.
2. Install the Firebase SDK: `npm install firebase`
3. Configure your Firebase project.
4. Run `node bug.js` (this will throw an error)
5. Run `node bugSolution.js` (this will handle the potential error gracefully)

## Solution

Always check for null or undefined values before accessing properties of a Firestore document snapshot.  The solution involves using optional chaining or nullish coalescing operators to gracefully handle these scenarios.