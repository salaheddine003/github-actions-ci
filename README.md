# Jest Express API Testing Example

This repository provides a simple example of how to test a Node.js API using [Jest](https://jestjs.io/). The project is structured to demonstrate unit testing for an Express application, covering controllers, services, routers, and server configuration.

## Table of Contents
- [Project Structure](#project-structure)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Running the API](#running-the-api)
- [Testing the Code](#testing-the-code)
- [Generating Coverage Reports](#generating-coverage-reports)
- [Git Hook Scripts](#git-hook-scripts)

## Project Structure

```
.
├── README.md
├── package.json
├── package-lock.json
├── src
│   ├── controller.js
│   ├── index.js
│   ├── router.js
│   └── service.js
└── test
    ├── controller.test.js
    ├── index.test.js
    ├── router.test.js
    └── service.test.js
```

## Prerequisites

- Node.js (v18.17.1 or higher)
- npm (included with Node.js)

To manage Node.js versions, you can use [nvm](https://github.com/nvm-sh/nvm).

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/thamerh/jest-express-api-testing-example.git
   cd jest-express-api-testing-example
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

## Running the API

To start the Express server, run:
```bash
npm start
```

You can test the API endpoint using `curl` or any HTTP client:
```bash
curl http://localhost:3000/posts
```

## Testing the Code

This project uses Jest for testing. To run the tests, use the following command:
```bash
npm test
```

Example output:
```
PASS  test/router.test.js
  should test router
    √ should test get posts (21 ms)

PASS  test/controller.test.js
  should test controller
    √ when #getPost method method succeeds (16 ms)
    √ when #getPost method method fails (1 ms)

PASS  test/service.test.js
  should test Service
    √ when #list method succeeds (17 ms)
    √ when #list method fails (1 ms)

PASS  test/index.test.js (5.998 s)
  should test server configuration
    √ should run the express server (39 ms)

Test Suites: 4 passed, 4 total
Tests:       6 passed, 6 total
Snapshots:   0 total
Time:        7.033 s
```

## Generating Coverage Reports

Jest includes built-in coverage reporting using Istanbul. To generate a coverage report, run:
```bash
npm run coverage
```

This will produce a coverage report in the terminal and generate an HTML report in the `coverage/lcov-report` directory.

Example terminal output:
```
PASS  test/index.test.js
PASS  test/router.test.js
PASS  test/controller.test.js
PASS  test/service.test.js

---------------|---------|----------|---------|---------|-------------------
File           | % Stmts | % Branch | % Funcs | % Lines | Uncovered Line #s 
---------------|---------|----------|---------|---------|-------------------
All files      |   95.83 |      100 |   85.71 |   95.83 |                   
 controller.js |     100 |      100 |     100 |     100 |                   
 index.js      |   83.33 |      100 |       0 |   83.33 | 9                 
 router.js     |     100 |      100 |     100 |     100 |                   
 service.js    |     100 |      100 |     100 |     100 |                   
---------------|---------|----------|---------|---------|-------------------

Test Suites: 4 passed, 4 total
Tests:       7 passed, 7 total
Snapshots:   0 total
Time:        1.459 s
```

## Git Hook Scripts

This project uses [Husky](https://typicode.github.io/husky/#/) to manage Git hooks. A pre-commit hook is configured to run tests before each commit. If the tests fail, the commit will be aborted.

Example output when committing:
```bash
$ git commit -am 'feat: add basic husky support'
> jest test/**.test.js

PASS  test/index.test.js
PASS  test/service.test.js
PASS  test/router.test.js
PASS  test/controller.test.js

Test Suites: 4 passed, 4 total
Tests:       7 passed, 7 total
Snapshots:   0 total
Time:        1.812 s
Ran all test suites matching /test\/controller.test.js|test\/index.test.js|test\/router.test.js|test\/service.test.js/i.
[master 508a8eb] feat: add basic husky support
4 files changed, 16 insertions(+), 3 deletions(-)
create mode 100644 .husky/.gitignore
create mode 100755 .husky/pre-commit
```

---

Feel free to explore the code and adapt it to your needs. If you have any questions or suggestions, please open an issue or submit a pull request. Happy coding! 🚀

## Made By

- [@thamerh](https://github.com/thamerh)