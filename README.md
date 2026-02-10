# Insurance Premium Prediction API  
FastAPI • Machine Learning • Docker • Production-ready API

---

## 📌 Overview

This project is a **production-ready FastAPI application** that predicts **insurance premiums** based on user attributes such as age, BMI-related inputs, income, smoking habits, city, and occupation.

The application is:
- Built using **FastAPI**
- Backed by a **trained Machine Learning model**
- Fully **Dockerized**
- Designed for **local development, containerized deployment, and cloud readiness**

---

## 🏗️ Tech Stack

- **Backend Framework**: FastAPI
- **Server**: Uvicorn
- **ML Stack**: Scikit-learn, NumPy, Pandas
- **Data Validation**: Pydantic v2
- **Containerization**: Docker
- **Language**: Python 3.11

---

## 📂 Project Structure

```text
insurance-premium-prediction-fastapi/
│
├── app.py                  # FastAPI application entry point
├── model.pkl               # Trained ML model
├── requirements.txt        # Python dependencies
├── Dockerfile              # Docker build instructions
├── README.md               # Project documentation
└── .gitignore
```
🚀 Running the Application Locally (Without Docker)
1️⃣ Clone the Repository
```
git clone <your-github-repo-url>
cd insurance-premium-prediction-fastapi
```

2️⃣ Create Virtual Environment
```
python3 -m venv venv
source venv/bin/activate   # macOS/Linux
# venv\Scripts\activate    # Windows
```
3️⃣ Install Dependencies
```
pip install --upgrade pip
pip install -r requirements.txt
```

4️⃣ Run the FastAPI Server
```
uvicorn app:app --reload
```

5️⃣ Access the Application

API Base URL:
```
👉 http://127.0.0.1:8000
```

Swagger UI (Recommended):
```
👉 http://127.0.0.1:8000/docs
```

🐳 Running the Application Using Docker 
🔹 Pull Prebuilt Docker Image
```
docker pull raianuj0/insurance-premium-prediction-fastapi
```

🔹 Run the Docker Container
```
docker run -d -p 8000:8000 raianuj0/insurance-premium-prediction-fastapi
```
🔹 Access the Application

API URL:
```
👉 http://localhost:8000
```
Swagger UI:
```
👉 http://localhost:8000/docs
```
🛠️ Build Docker Image Locally

If you want to build the image from source:
```
docker build -t insurance-premium-fastapi .
```

Run the container:
```
docker run -p 8000:8000 insurance-premium-fastapi
```
📦 Dockerfile (Used in This Project)
```
FROM python:3.11-slim

WORKDIR /app

COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

COPY . .

EXPOSE 8000

CMD ["uvicorn", "app:app", "--host", "0.0.0.0", "--port", "8000"]
```
📤 Push Docker Image to Docker Hub
1️⃣ Login to Docker Hub
```
docker login
```
2️⃣ Tag the Image
```
docker tag insurance-premium-fastapi raianuj0/insurance-premium-prediction-fastapi:latest
```
3️⃣ Push the Image
```
docker push raianuj0/insurance-premium-prediction-fastapi:latest
```

📥 Sample API Request

Endpoint

POST /predict

```
Sample Input

{
  "age": 35,
  "weight": 70,
  "height": 1.72,
  "income_lpa": 6,
  "smoker": false,
  "city": "Mumbai",
  "occupation": "private"
}
```

⚠️ Validation Notes

Height is expected in meters

Age must be >= 18

Input validation is handled using Pydantic

Invalid inputs will return:

422 Unprocessable Entity

📈 Future Enhancements

CI/CD pipeline integration

Model versioning

Cloud deployment (AWS / GCP)

Authentication & rate limiting

Logging & monitoring

👤 Author

Anuj Rai
AI / Machine Learning Engineer
Docker • FastAPI • Production ML Systems
