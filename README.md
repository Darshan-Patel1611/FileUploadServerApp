# Node.js File Upload Server Application

This is a Node.js server application that allows users to upload images and videos to the server. It uses Express and the Express File Uploader middleware to handle file uploads. The uploaded files are then stored on Cloudinary, a cloud-based image and video management service. The application also sends an email to the user who uploaded the file, containing a link to the uploaded file.

## Getting Started

To get started with this application, follow these steps:

1. Clone this repository to your local machine.
2. Install the dependencies using npm:

   ```bash
   npm install
   ```

3. Create a `.env` file in the root directory of the project with the following environment variables:

   ```plaintext
   CLOUDINARY_CLOUD_NAME=your_cloudinary_cloud_name
   CLOUDINARY_API_KEY=your_cloudinary_api_key
   CLOUDINARY_API_SECRET=your_cloudinary_api_secret
   EMAIL_USER=your_email_username
   EMAIL_PASS=your_email_password
   ```

4. Run the application using npm:

   ```bash
   npm start
   ```

5. The server should now be running on http://localhost:3000.

## Endpoints

The application defines the following endpoints for file upload:

- `POST /upload/image`: Uploads an image file to the server and stores it on Cloudinary.
- `POST /upload/video`: Uploads a video file to the server and stores it on Cloudinary.
- `POST /upload/reduceSize`: Reduces the size of an uploaded image file and stores it on Cloudinary.

## File Structure

The application consists of the following files:

- `index.js`: Sets up the Express app, connects to the database and Cloudinary, and defines the endpoints for file upload.
- `routes/FileUpload.js`: Defines the routes for file upload, which include `imageUpload`, `videoUpload`, and `imageSizeReducer`.
- `models/File.js`: Defines the schema for the uploaded files and defines a post-save hook that sends an email to the user who uploaded the file.
- `controllers/fileUpload.js`: Contains the logic for handling file uploads, including checking file types, uploading to Cloudinary, and saving the file to the database.

## Dependencies

- Express: Web application framework for Node.js.
- Multer: Middleware for handling file uploads.
- Cloudinary: Cloud-based image and video management service.
- Nodemailer: Module for sending emails.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

