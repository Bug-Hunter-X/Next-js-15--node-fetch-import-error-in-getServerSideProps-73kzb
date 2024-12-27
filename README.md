# Next.js 15: node-fetch import error in getServerSideProps

This repository demonstrates a common error encountered when using `node-fetch` within the `getServerSideProps` function in Next.js 15.  The problem stems from attempting to use a Node.js-specific module in a context designed for the browser. 

## Bug Description

The `about.js` file attempts to fetch data from an external API using `node-fetch`. This works in a Node.js environment, but Next.js's `getServerSideProps` runs on the server, but uses a different runtime environment. Importing node-fetch directly here causes the error.  The error message will usually indicate that `node-fetch` cannot be found or is not compatible with the serverless function context.

## Solution

The solution is provided in `aboutSolution.js`, which uses the built-in `fetch` API available in the Next.js environment.  This avoids the incompatibility issues.