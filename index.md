
## Description

Template application consist of various microservices each of them has own README.md, dependencies and .env files

## Install packages.

```bash
$ yarn setup:base
$ yarn setup
```

## Build service and start service.

`cd ./apps/<service-name>`
`yarn build`
`yarn start`

## Start like monolith.
`yarn start-monolith`

## Running the app

```bash
# run api-gateway
$ yarn start:api-gateway

# run auth
$ yarn start:auth

# run delivery
$ yarn start:delivery

$ yarn start:user-management
// Provided Microservices work together
```

## Test

```bash
# unit tests
$ yarn run test

# e2e tests
$ yarn run test:e2e & yarn run test:payment:e2e

# test coverage
$ npm run test:cov
```

**For husky hooks**:
If you have this warning
```
hint: The '.husky/pre-commit' hook was ignored because it's not set as executable.
hint: You can disable this warning with git config advice.ignoredHook false.
```

Try to add change mode for directory husky

```
chmod ug+x .husky/* 
chmod ug+x .git/hooks/* 
```

**Integration test**:
If you want to create integration test, you must create a file ending in *.ispec.ts

**For commitlint**:
You can find all rules this - [@commitlint/config-conventional](https://github.com/conventional-changelog/commitlint/tree/master/%40commitlint/config-conventional)

### Tests work only with these versions libs

```
"@types/jest": "27.0.2"
"ts-jest": "^27.0.3",
"tsconfig-paths": "^3.10.1",
"typescript": "^4.3.5"
```

# Info for deploy

## Structure:

 1. /apps - is folder with microservices
 2. /libs - is folder with shared code.
 3. package.json - file with list of project dependencies, configurations and scripts (presence in each microservice folder)

## Commands:
1. `npm i -g yarn` - install yarn package manager using npm.
2. `yarn setup:base` - install packages in root level
3. `yarn setup` - install packages for each microservices
4. `yarn build` - build some project (execute in root folder of project)
5. `yarn start` - start project from build

## CI/CD must include next steps:
 - run linter:
`yarn lint`

- run tests:
`yarn all:tests`
