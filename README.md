# Image Resizing API - Overview

It is a NodeJS project that resizes and serves images sent to the API. 

### Requirements

You need `node@^12` and `npm@^6` installed on your system.

### Installation

Install all project dependencies with `npm`:
```bash
npm i
```

Now, Start the application with the predefined scripts:

```bash
npm run dev
# OR
npm run start
```

## API Information

This is a `POST` API that accepts a binary request with an image as the body.

As query parameters, you must give the image's `height` and `width`, to which it will be scaled.

Example:
```bash
curl --location --request POST 'http://localhost:8000/image/?width=320&height=200' \
--header 'Content-Type: image/jpeg' \
--data-binary '@/home/user/Pictures/image.jpg'
```

The scaled image can be downloaded using the filename returned by this API.

Example:
```bash
# Response from API: { "filename": "8fca0300-4fe8-11eb-ba0a-53c1805778e7.jpg" }
curl --location --request GET 'http://localhost:8000/8fca0300-4fe8-11eb-ba0a-53c1805778e7.jpg'
```

## Unit Testing

Inside the `tests` directory, you'll find unit tests.
A preset script may be used to execute the unit tests:
```bash
npm run test
```

## Coding Styles

For `git` hooks, the project utilizes `husky`. Pre-commit hooks are available to execute `eslint` and `prettier` on staged files. The unit tests are conducted using a pre-push hook. The `package.json` file contains the configuration for this.

## Built With

* [NodeJS](https://nodejs.org/en/)
* [Express](https://expressjs.com/)
* [TypeScript](https://www.typescriptlang.org/) 
* [Sharp](https://sharp.pixelplumbing.com/) 
