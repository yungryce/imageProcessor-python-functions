<p align="center">
  <img src="https://img.shields.io/badge/Azure_Functions-2.0+-0062AD?logo=microsoftazure" alt="Azure Functions">
  <img src="https://img.shields.io/badge/Python-3.10+-3776AB?logo=python" alt="Python">
  <img src="https://img.shields.io/badge/Pillow-Image_Processing-orange" alt="Pillow">
  <img src="https://img.shields.io/badge/Status-Active-success" alt="Status">
</p>

<div align="center">
  <h1>🖼️ Image Processor Function App</h1>
  <p><em>Serverless Image Upload, Compression & Storage System</em></p>
</div>

---

## 📋 Table of Contents
- [📖 Overview](#-overview)
- [🎯 Learning Objectives](#-learning-objectives)
- [🛠️ Tech Stack](#️-tech-stack)
- [📁 Project Structure](#-project-structure)
- [🚀 Getting Started](#-getting-started)
- [💡 Usage](#-usage)
- [🏆 Key Features](#-key-features)
- [📚 Resources](#-resources)
- [👥 Contributors](#-contributors)

## 📖 Overview

This serverless Azure Function App provides a comprehensive solution for image upload, compression, and storage using Azure Blob Storage. The system automatically compresses uploaded images to optimize storage costs while maintaining visual quality, demonstrating advanced cloud-native patterns for media processing applications.

Built with modern serverless architecture principles, this application showcases efficient image processing workflows, automatic scaling, and cost-effective storage management. The system handles various image formats, implements intelligent compression algorithms, and provides RESTful APIs for seamless integration with web and mobile applications.

## 🎯 Learning Objectives

Through this project, you will master:

- **Serverless Image Processing**: Build and deploy Azure Functions for media handling
- **Cloud Storage Integration**: Implement Azure Blob Storage for scalable file management
- **Image Compression Algorithms**: Apply Pillow library for intelligent image optimization
- **RESTful API Design**: Create endpoints for upload, retrieval, and listing operations
- **Error Handling**: Implement robust validation and exception management
- **Performance Optimization**: Balance file size reduction with visual quality preservation
- **CI/CD Automation**: Deploy serverless applications with GitHub Actions

## 🛠️ Tech Stack

**Core Technologies:**
- **Azure Functions**: Serverless compute platform for event-driven processing
- **Python 3.10+**: Primary programming language with advanced image processing
- **Azure Blob Storage**: Scalable cloud storage for image files and media assets

**Development Tools:**
- **Pillow (PIL)**: Advanced Python imaging library for compression and manipulation
- **Azure Storage SDK**: Comprehensive blob storage client library
- **GitHub Actions**: Automated CI/CD pipeline for serverless deployment
- **Azure Functions Core Tools**: Local development and testing environment

## 📁 Project Structure

```
imageProcessor-FA/
├── function_app.py          # Main Azure Function with HTTP endpoints
├── host.json               # Function app runtime configuration
├── requirements.txt        # Python dependencies and imaging libraries
├── .github/
│   └── workflows/          # CI/CD pipeline automation
├── ARCHITECTURE.md         # System design and processing workflow
├── SKILLS-INDEX.md        # Technical skills and competencies catalog
└── README.md              # Project documentation
```

## 🚀 Getting Started

### Prerequisites

- **Azure Account**: Active Azure subscription with Functions service enabled
- **Python 3.10+**: Local development environment with pip package manager
- **Azure Functions Core Tools**: For local testing and deployment
- **Azure Storage Account**: Blob storage for image file management
- **Git**: Version control system for code management

### Installation

1. **Clone the repository**:
   ```bash
   git clone <repository-url>
   cd imageProcessor-FA
   ```

2. **Install dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

3. **Configure environment variables**:
   ```bash
   # Create local.settings.json for local development
   {
     "IsEncrypted": false,
     "Values": {
       "AzureWebJobsStorage": "your-storage-connection-string",
       "FUNCTIONS_WORKER_RUNTIME": "python"
     }
   }
   ```

### Running the Project

1. **Local Development**:
   ```bash
   func start
   ```

2. **Deploy to Azure**:
   ```bash
   func azure functionapp publish <your-function-app-name>
   ```

3. **Test Image Upload**:
   ```bash
   curl -X POST "http://localhost:7071/api/upload-image" \
        -F "file=@your-image.jpg"
## 💡 Usage

### Image Upload API

**Upload and compress images with automatic optimization:**

```bash
# Upload image via HTTP POST
curl -X POST "http://localhost:7071/api/upload-image" \
     -F "file=@path/to/your/image.jpg"

# Response: Success message with compressed image details
```

**Endpoint Details:**
- **URL**: `/upload-image`
- **Method**: `POST`
- **Content-Type**: `multipart/form-data`
- **File Parameter**: `file`
- **Max Size**: 10MB (before compression)
- **Supported Formats**: JPEG, PNG, GIF, TIFF, BMP

### Image Retrieval API

**Fetch stored images from blob storage:**

```bash
# Get specific image
curl "http://localhost:7071/api/get-image/your-image.jpg"

# List all available images
curl "http://localhost:7071/api/list-images"
```

### Compression Logic

The system intelligently compresses images using the following algorithm:
- **Target Size**: 20KB maximum per image
- **Quality Adjustment**: Iterative quality reduction (95% → 90% → 85%...)
- **Minimum Quality**: 10% (prevents over-compression)
- **Format Preservation**: Maintains original image format when possible

## 🏆 Key Features

- **Intelligent Image Compression**: Automatic size optimization while preserving visual quality
- **Multi-Format Support**: Handles JPEG, PNG, GIF, TIFF, and BMP image formats
- **Scalable Storage**: Azure Blob Storage integration for unlimited capacity
- **RESTful API Design**: Clean HTTP endpoints for upload, retrieval, and listing
- **Automatic Container Management**: Creates storage containers dynamically as needed
- **Error Handling & Validation**: Comprehensive input validation and exception management
- **MIME Type Detection**: Proper content-type headers for image serving
- **CI/CD Integration**: Automated deployment with GitHub Actions
- **Performance Monitoring**: Built-in logging and Azure monitoring integration
- **Cost Optimization**: Efficient compression reduces storage costs significantly

## 📚 Resources

- [Azure Functions Documentation](https://docs.microsoft.com/azure/azure-functions/)
- [Azure Blob Storage Guide](https://docs.microsoft.com/azure/storage/blobs/)
- [Pillow (PIL) Documentation](https://pillow.readthedocs.io/)
- [Python Azure SDK](https://docs.microsoft.com/python/api/overview/azure/)
- [GitHub Actions for Azure](https://docs.microsoft.com/azure/developer/github/github-actions)
- [SKILLS-INDEX.md](./SKILLS-INDEX.md) - Detailed technical skills catalog
- [ARCHITECTURE.md](./ARCHITECTURE.md) - System design and processing workflow

## 👥 Contributors

**Chigbu Joshua**
- 📧 Email: [chigbujoshua@yahoo.com](mailto:chigbujoshua@yahoo.com)
- 🐙 GitHub: [@yungryce](https://github.com/yungryce)
- 🎯 Role: Primary Author, Project Maintainer

*This project demonstrates advanced serverless image processing and cloud storage integration patterns for modern web applications.*