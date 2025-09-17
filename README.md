# weather-prediction-using-deep learning
AI Weather Prediction Dashboard
Welcome to the AI Weather Prediction Dashboard!
Live Demo: sky-frame.lovable.app
🚀 Overview
This project is an interactive dashboard to predict the next weather radar frame based on incoming radar images. The model takes exactly 4 input radar frames and produces 1 predicted output frame, along with evaluation metrics like SSIM, PSNR, and MSE.
📦 Features
Upload exactly 4 radar image frames
Click “Predict Frame” to get a machine learning prediction
Display of:
Input frames
Predicted output frame
Error heatmap / difference visualization (if available)
Metrics panel showing SSIM, PSNR, MSE
Responsive, clean UI with weather themed styles
Loader/spinner during prediction
Error handling if backend is unreachable
🧰 Tech Stack
Frontend: Lovable / React / Tailwind (or you can specify)
Backend: Python (Flask or FastAPI) with a ConvLSTM-based model for spatio-temporal prediction
Model: Deep Learning (ConvLSTM) trained on radar image sequences
Utilities: OpenCV, imageio, skimage (for metrics), etc.
🔧 Usage
Local Setup
Clone the repository
git clone https://github.com/yourusername/weather-prediction-dashboard.git
cd weather-prediction-dashboard
Install backend dependencies
cd backend
pip install -r requirements.txt
Run the backend server
python app.py
(Optional) Run frontend locally if you have source
cd frontend
npm install
npm run dev
Open the app in your browser, or use the live demo: sky-frame.lovable.app
🔗 API Endpoints
Endpoint	Method	Description
/predict	POST	Send 4 radar frames → returns predicted frame + metrics
/health	GET	Check backend service status
Sample /predict request:
POST /predict
Content-Type: multipart/form-data
files[]: frame1.png  
files[]: frame2.png  
files[]: frame3.png  
files[]: frame4.png  
(optional) files[]: ground_truth.png
Sample /predict response:
{
  "predicted_frame": "base64_string_of_image",
  "metrics": {
    "ssim": 0.87,
    "psnr": 30.5,
    "mse": 0.01
  },
  "heatmap": "base64_string_of_heatmap"  // optional
}
📈 Model & Training
Model architecture is based on ConvLSTM2D + Conv3D
Input: last 4 radar frames
Output: next radar frame
Loss: MSE + SSIM combined
Metrics: SSIM, PSNR, MSE
🔍 Demo & Screenshots
(Here you can insert screenshots or GIFs of the dashboard showing input frames, predicted frame, metrics, etc.)
🛠 Deployment
Frontend deployed at sky-frame.lovable.app
Backend can be deployed on platforms like Heroku, AWS, Google Cloud, or similar.
📄 License
Specify your licensing, e.g.:
MIT License — see LICENSE for details
👍 Contributing
Feel free to open issues
Suggest improvements (UI, model accuracy, dataset)
Pull requests welcome
