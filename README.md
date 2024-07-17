# Overview
Below are the added configurations choices and explanations.

## Git
`.gitignore`: A gitignore file is included to ensure that files that we don't want to commit are excluded. This includes our .env file, the node_modules directory, and a few other stock values that I have seen suggested in the past, though they might not all be completely necessary. If given more time, I would certainly filter them with more intent.

## Environments
`.env` / `.env.example`: The `.env` file won't be committed, but I added an environment variable file and example file so that the application can swap values for the variables when needed. This helps ensure projects can be ran pointing to other environments, like stg, pre-production, and production for proper development workflows.

## Style Guide/Formatting
`EsLint`: Having a linter helps us avoid smaller mistakes and keeps our code neat. I didn't change any rules given the time constraint, but this is an important piece to be run before committing any code.

`prettier`: Having some sort of formatting tool helps keep all of the code consistent when working with larger teams.

`commit-hook`: I did not have time to implement this, but having a commit hook that runs the linter and formatter before committing. This can help keep teams from missing them and committing unformatted and lint failing code, which is especially problematic if the linter fails when being run in the CI/CD pipeline.

## Tests
`Jest`: Unit and Integration testing using tools like Jest can help create more confidence when developing features and making updates. Jest is usually a great choice for testing in React.

`Cypress`: This is not implemented here, but end to end testing would also be important, though it would likely be in it's own repo.

## CI/CD
`GitHub Actions`: I did not have time to implement this, but having GitHub actions is essential for CI/CD processes. Ideally, we would have a `.yml` with instructions on what the repos to checkout, how to build the application and run the linter, Jest and Cypress tests in the pipeline.

# Getting Started

Be sure to create a `.env` file using the variables in the `.env.example` file.

```bash
npm i
npm start
```

Visit [http://localhost:3000](http://localhost:3000) to see the app running.

You should see a welcome page with 2 links to other pages.

When visiting the links:
* on http://127.0.0.1:3000/appWithoutSSRData you will see 
  - `Error: UseCachingFetch has not been implemented`
* on http://127.0.0.1:3000/appWithSSRData you will see
  - ```{
    "statusCode": 500,
    "error": "Internal Server Error",
    "message": "preloadCachingFetch has not been implemented"
    }

