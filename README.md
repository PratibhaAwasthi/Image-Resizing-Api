# Image Resizing API 

## Project Overview: 
The Image-Processing-API is a NodeJS project that resizes and serves images sent to the API. It is an express server which is able to take images located in a folder and create a resized thumb version of it and save it on the disk. Once created a thumb version it just serves the processed image through the API endpoint. 

## Functionality: 
The Image-Processing-API is capable of performing the following functions:

* *Resizing images:* The API can create a thumb version of an image if it does not exist already. This functionality is useful in reducing the page load size by serving images that are properly scaled.

* *Customizing image size:* The API allows you to change the height or width parameters of an image, which triggers the recreation of the image in the specified size. This functionality is particularly useful when you need images of a specific size for your frontend.

* *Serving processed images:* Once an image is processed by the API, it is delivered as a response to the client. This feature enables the frontend to receive optimized images, reducing the load time of the website.


## Architecture: 
The API is built using NodeJS and the Express server. The application uses the Sharp image processing library to resize and process images. The Sharp library is known for being fast and efficient, making it an ideal choice for image processing in a web application. The API uses an MVC (Model-View-Controller) architecture pattern to separate concerns and improve code organization.

## Project Timeline (1 month): 
* Week 1:
Set up NodeJS environment
Install Express and Sharp libraries
Create API endpoint for serving images

* Week 2:
Implement functionality for creating thumb versions of images
Test image processing functionality


* Week 3:
Implement query parameters for specifying image width and height
Test image resizing functionality

* Week 4:
Implement statistics endpoint for API usage tracking
Final testing and debugging of the API

## Motivation: The Image-Processing-API provides developers with an easy-to-use and efficient tool for processing images. With the growing demand for high-quality and fast-loading websites and applications, it is important to have a tool that can optimize images for better performance. By using the Image-Processing-API, developers can ensure that images are processed quickly and efficiently, leading to a better user experience. Additionally, the API can save developers time and effort by automating the process of resizing images, freeing up time to focus on other aspects of the project. Overall, the Image-Processing-API is a valuable tool for developers looking to improve the performance and user experience of their websites or applications.


## Requirements

You need `node@^12` and `npm@^6` installed on your system.

## Installation

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
##Response from API: { "filename": "8fca0300-4fe8-11eb-ba0a-53c1805778e7.jpg" }
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
