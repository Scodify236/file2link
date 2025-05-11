# Installation Guide

This guide will help you set up and run the Image Upload application.

## Prerequisites

- Python 3.8 or higher
- pip (Python package installer)
- Internet Archive account with S3 credentials

## Installation Steps

1. Clone the repository:
```bash
git clone <repository-url>
cd python
```

2. Create a virtual environment (recommended):
```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

3. Install the required packages:
```bash
pip install -r requirements.txt
```

4. Configure Internet Archive credentials:
   - Get your S3 credentials from [Internet Archive](https://archive.org/account/s3.php)
   - The credentials are already configured in the application

## Running the Application

1. Start the Flask server:
```bash
python app.py
```

2. Access the application:
   - Open your web browser
   - Navigate to `http://localhost:5000`

## Features

- Modern dark-themed UI
- Image upload to Internet Archive
- Unique filename generation
- Automatic metadata handling
- API endpoint for programmatic access

## API Usage

See [API.md](API.md) for detailed API documentation.

## Troubleshooting

1. If you encounter SSL errors:
   - Make sure you have the latest version of Python
   - Update your pip packages: `pip install --upgrade pip`

2. If uploads fail:
   - Check your Internet Archive credentials
   - Ensure you have a stable internet connection
   - Verify the image file is not corrupted

## Contributing

1. Fork the repository
2. Create a feature branch
3. Commit your changes
4. Push to the branch
5. Create a Pull Request

## License

This project is licensed under the MIT License - see the LICENSE file for details. 