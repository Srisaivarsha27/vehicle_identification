# 🚗 Vehicle Identification System

A full-stack project to detect and log vehicle license plates using **YOLOv8** and **EasyOCR**. Built with a React frontend and a FastAPI + SQLite backend, this project was created as a hands-on exploration of image processing and pretrained model integration.

---

## 🧠 Features

- 📷 Detects license plates from uploaded images using a pretrained YOLOv8 model
- 🔠 Extracts text using EasyOCR
- 🗂️ Saves detection data into a SQLite database with details like filename, coordinates, and timestamp
- 💻 Frontend built with React + Vite for easy uploads and results display

---

## 🛠️ Tech Stack

| Layer      | Tech Used                             |
|------------|----------------------------------------|
| Frontend   | React (Vite, JSX, Hooks)               |
| Backend    | FastAPI, SQLAlchemy, SQLite            |
| Detection  | Ultralytics YOLOv8, EasyOCR            |

---

## 📁 Folder Structure

```

vehicle\_identification/
├── backend/
│   ├── app.py                  # FastAPI app
│   ├── database.py             # SQLAlchemy DB config
│   ├── models.py               # DB table model for vehicle logs
│   ├── requirements.txt        # Backend dependencies
│   ├── yolo\_easyocr.py         # Detection + OCR logic
│   └── captured/               # Saved plate images from detections
├── frontend/
│   ├── src/
│   │   ├── components/         # UploadForm (if modularized)
│   │   ├── App.jsx             # Main React component
│   │   ├── index.jsx           # Entry point
│   │   └── styles.css          # Basic styling
│   ├── index.html              # HTML template
│   ├── package.json            # Frontend dependencies
│   ├── vite.config.js          # Vite config
│   └── .gitignore
├── .gitignore
├── README.md                   # You’re reading it!

````

---

## 🚀 Running the Project

### Backend

1. Navigate to backend:

````bash
   cd backend
````

2. Create virtual environment and install dependencies:

   ```bash
   python -m venv env
   env\Scripts\activate  # On Windows
   pip install -r requirements.txt
   ```

3. Start FastAPI server:

   ```bash
   uvicorn app:app --reload
   ```

---

### Frontend

1. Navigate to frontend:

   ```bash
   cd frontend
   ```

2. Install dependencies and run dev server:

   ```bash
   npm install
   npm run dev
   ```

---

## 🧪 How It Works

* Upload an image from the frontend.
* `yolo_easyocr.py` runs YOLOv8 to detect license plate regions.
* EasyOCR extracts license numbers from those regions.
* Cropped plate images are saved to `backend/captured/`
* Final license text is returned and stored in SQLite (`fleet_logs.db`).

---

## 🖼️ Example Output

```json
{
  "license_plate": "TN 07 AB 1234"
}
```

> Cropped images are saved in the `captured/` folder with timestamped filenames.

---

## 🎯 Purpose

This project was built for learning and exploration:

* 📚 Practice integrating pretrained models
* 🧠 Learn basic OCR with YOLO
* ⚙️ Build a working full-stack app

---

## 🙌 Acknowledgements

* [Ultralytics YOLOv8](https://github.com/ultralytics/ultralytics)
* [EasyOCR](https://github.com/JaidedAI/EasyOCR)

---

## 🌟 Author

Made with patience, pixels, and Python
by [Srisaivarshini B](https://github.com/Srisaivarsha27)

