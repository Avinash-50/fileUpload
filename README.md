# File Upload API

## Overview
This project provides an Express.js-based backend API for handling file uploads, including images and videos. The API supports local file storage and integration with Cloudinary for cloud-based storage.

## Features
- Upload files to the local server
- Upload images and videos to Cloudinary
- Reduce image file size before uploading
- Validate file formats before uploading

## Technologies Used
- Node.js
- Express.js
- Cloudinary (for cloud storage)
- MongoDB (for database storage)
- Multer / express-fileupload (for handling file uploads)

## Installation
1. Clone the repository:
   ```sh
   git clone <repository-url>
   ```
2. Navigate to the project directory:
   ```sh
   cd file-upload-api
   ```
3. Install dependencies:
   ```sh
   npm install
   ```
4. Set up environment variables:
   - Create a `.env` file in the root directory
   - Add the following variables:
     ```env
     CLOUDINARY_CLOUD_NAME=<your-cloud-name>
     CLOUDINARY_API_KEY=<your-api-key>
     CLOUDINARY_API_SECRET=<your-api-secret>
     MONGO_URI=<your-mongodb-connection-string>
     ```

## API Endpoints

### Upload a File to Local Server
- **Endpoint:** `POST /api/files/localFileUpload`
- **Description:** Uploads a file to the local server.
- **Request Body:** `multipart/form-data`
  - `file`: File to be uploaded
- **Response:**
  ```json
  {
    "success": true,
    "message": "Local File Uploaded Successfully"
  }
  ```

### Upload an Image to Cloudinary
- **Endpoint:** `POST /api/files/imageUpload`
- **Description:** Uploads an image file to Cloudinary.
- **Request Body:** `multipart/form-data`
  - `imageFile`: Image file to be uploaded
  - `name`, `tags`, `email`
- **Response:**
  ```json
  {
    "success": true,
    "imageUrl": "<uploaded-image-url>",
    "message": "Image Successfully Uploaded"
  }
  ```

### Upload a Video to Cloudinary
- **Endpoint:** `POST /api/files/videoUpload`
- **Description:** Uploads a video file to Cloudinary.
- **Request Body:** `multipart/form-data`
  - `videoFile`: Video file to be uploaded
  - `name`, `tags`, `email`
- **Response:**
  ```json
  {
    "success": true,
    "imageUrl": "<uploaded-video-url>",
    "message": "Video Successfully Uploaded"
  }
  ```

### Reduce Image Size and Upload
- **Endpoint:** `POST /api/files/imageSizeReducer`
- **Description:** Reduces image size before uploading it to Cloudinary.
- **Request Body:** `multipart/form-data`
  - `imageFile`: Image file to be compressed and uploaded
  - `name`, `tags`, `email`
- **Response:**
  ```json
  {
    "success": true,
    "imageUrl": "<compressed-image-url>",
    "message": "Image Successfully Uploaded"
  }
  ```

## Running the Project
1. Start the server:
   ```sh
   npm start
   ```
2. The API will be running on `http://localhost:5000` (or as per environment setup).

## License
This project is open-source and available under the MIT License.

