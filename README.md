# Vision Tray

Vision Tray is a fully responsive web application that automates food tray billing using computer vision.

Users can capture or upload an image of their food tray, and the system automatically detects food items, calculates quantities, and generates a bill in real time.

The application uses a custom-trained YOLOv8-m model for object detection, integrated with a FastAPI backend and Supabase database for pricing and inventory management.

---

## Installation

### Clone Repository

```bash
git clone https://github.com/RaoGhulam/vision_tray.git
cd vision_tray
```

### Create Virtual Environment

```bash
python -m venv venv
source venv/bin/activate
```

### Install Dependencies

```bash
pip install -r requirements.txt
```

### Run Application

```bash
uvicorn main:app --reload
```

---

## Features

- Upload or capture food tray images
- Real-time food item detection
- Automatic quantity estimation
- Dynamic bill generation
- Admin-controlled pricing via database
- Fully responsive web interface
- CI/CD automated deployment pipeline
- Containerized deployment using Docker
- Cloud-hosted on AWS EC2

---

## Tech Stack

### Backend
- FastAPI

### Frontend
- HTML
- CSS
- JavaScript

### Database
- Supabase

### Computer Vision
- YOLOv8-m (custom trained)

### DevOps & Deployment
- GitHub Actions
- Docker
- Docker Hub
- AWS EC2
- AWS CloudWatch

---

## How It Works

### 1. Image Upload
The user captures or uploads an image of their food tray.

### 2. Object Detection
The image is sent to a custom-trained YOLOv8-m model hosted on Hugging Face Spaces.

The model detects:
- Pizza
- Burger
- Sandwich
- Fries
- Chicken

It returns:
- Detected item names
- Item quantities

### 3. Price Retrieval
Detected items are matched against prices stored in the Supabase database.

Prices are managed by the admin panel.

### 4. Bill Generation
The system calculates the total bill automatically based on:

```text
Total = Item Price × Quantity
```

The final invoice is generated and displayed to the user.

---

## CI/CD Pipeline

The project follows complete CI/CD practices using GitHub Actions.

### Continuous Integration

On every push:

1. Checkout source code
2. Set up Python environment
3. Install dependencies
4. Run test suite using Pytest
5. Generate HTML test report

### Container Build & Push

6. Build Docker image
7. Login to Docker Hub
8. Push image to Docker Hub

### Continuous Deployment

9. SSH into AWS EC2 instance
10. Pull latest Docker image
11. Stop previous container
12. Run updated container
13. Stream logs to AWS CloudWatch

---

## Deployment Infrastructure

### Hosting
AWS EC2

### Containerization
Docker

### Monitoring
AWS CloudWatch Logs

### Registry
Docker Hub

---

## Future Improvements

- Support more food classes
- Improve quantity estimation accuracy
- Add payment gateway integration
- Admin dashboard analytics
- Mobile application support

---

## Use Cases

- University cafeterias
- Food courts
- Smart canteens
- Self-checkout systems
