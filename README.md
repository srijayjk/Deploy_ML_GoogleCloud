Handwritten Digit Classifier API
This project provides a simple Flask API for classifying handwritten digits using a pre-trained TensorFlow Keras model.

✨ Features
Handwritten Digit Classification: Classifies grayscale images of handwritten digits (0-9).
Flask API: Exposes a RESTful endpoint for submitting images and receiving predictions.
TensorFlow Keras Model: Utilizes a pre-trained nn.h5 model for predictions.
Image Preprocessing: Automatically transforms input images to the required 28x28 grayscale format.
🛠️ Setup
Prerequisites
Python 3.x
pip


🚀 Usage
Run the Flask application:

Bash

python app.py
The API will become available at http://127.0.0.1:5001.

Send a POST request with an image:
You can use curl or Postman to send your image file.

Example using curl:

Bash

curl -X POST -F "file=@path/to/your/image.png" http://127.0.0.1:5001/
Replace path/to/your/image.png with the actual path to your handwritten digit image. The image should be a grayscale image.

🔌 API Endpoint
POST /
Description: Accepts a handwritten digit image and returns the predicted digit.
Request Body: multipart/form-data with a field named file containing the image.
Responses:
200 OK:
JSON

{"prediction": 7}
(Returns the predicted digit as an integer)
400 Bad Request:
JSON

{"error": "no file"}
(If no file is provided in the request)
500 Internal Server Error:
JSON

{"error": "Error message"}
(For other server-side errors, including issues during image processing or prediction)
GET /
Description: A simple health check endpoint.
Response: 200 OK with the text "OK".
🧠 Model
The nn.h5 model is expected to be a pre-trained TensorFlow Keras model capable of classifying 28x28 grayscale images of handwritten digits into 10 classes (0-9). If you don't have one, you'll need to train or acquire a suitable model.

