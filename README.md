# Phishing Response System

A web application to streamline the response and documentation of phishing emails for security operations teams. This system integrates with Microsoft Defender for Endpoint, Jira, and Zscaler to provide a unified interface for managing phishing incidents.

## Features

- 🔍 Search and view suspicious emails from Microsoft Defender
- 📝 Create Jira tickets directly from selected emails
- 🌐 Submit malicious URLs to Zscaler for categorization
- 🔐 Secure authentication and authorization
- 📊 Dashboard for tracking incident response
- 🔄 Real-time status updates

## Architecture

The application consists of three main components:

1. **Frontend**: React-based single-page application
2. **Backend**: Python FastAPI server
3. **External Services**: Microsoft Defender, Jira, and Zscaler APIs

### Tech Stack

- Frontend:
  - React
  - Tailwind CSS
  - shadcn/ui components
  - Lucide icons

- Backend:
  - Python 3.8+
  - FastAPI
  - httpx for async HTTP requests
  - Pydantic for data validation

## Prerequisites

- Python 3.8 or higher
- Node.js 14 or higher
- Microsoft Defender for Endpoint subscription
- Jira account with API access
- Zscaler subscription with API access

## Installation

### Backend Setup

1. Create a virtual environment:
```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

2. Install dependencies:
```bash
pip install -r requirements.txt
```

3. Configure environment variables:
```bash
cp .env.example .env
# Edit .env with your API credentials and configuration
```

### Frontend Setup

1. Install dependencies:
```bash
cd frontend
npm install
```

2. Configure environment:
```bash
cp .env.example .env.local
# Edit .env.local with your configuration
```

## Configuration

Create a `.env` file with the following variables:

```env
# Backend Configuration
DEFENDER_TENANT_ID=your_tenant_id
DEFENDER_CLIENT_ID=your_client_id
DEFENDER_CLIENT_SECRET=your_client_secret

JIRA_URL=https://your-domain.atlassian.net
JIRA_EMAIL=your-email@domain.com
JIRA_API_TOKEN=your-api-token

ZSCALER_KEY=your-zscaler-key
ZSCALER_USERNAME=your-username

# Frontend Configuration
REACT_APP_API_URL=http://localhost:8000
```

## Running the Application

### Backend

```bash
cd backend
uvicorn main:app --reload
```

The API will be available at `http://localhost:8000`

### Frontend

```bash
cd frontend
npm run dev
```

The application will be available at `http://localhost:3000`

## API Documentation

Once the backend is running, view the API documentation at:
- Swagger UI: `http://localhost:8000/docs`
- ReDoc: `http://localhost:8000/redoc`

## Usage

1. **Authentication**
   - Log in using your organizational credentials
   - The system will handle API authentication for all integrated services

2. **Searching Emails**
   - Use the search bar to query suspicious emails
   - Results will display relevant email details

3. **Creating Tickets**
   - Select one or more emails from the results
   - Fill in the ticket details
   - Submit to create a Jira ticket

4. **URL Categorization**
   - Submit suspicious URLs through the interface
   - URLs will be automatically categorized in Zscaler

## Security Considerations

- All API credentials are stored securely using environment variables
- Authentication is required for all API endpoints
- HTTPS is enforced for all external API communications
- Rate limiting is implemented on all endpoints
- Input validation is performed on both frontend and backend

## Development

### Running Tests

Backend tests:
```bash
pytest
```

Frontend tests:
```bash
npm test
```

### Code Style

- Backend follows PEP 8 guidelines
- Frontend follows ESLint configuration

## Contributing

1. Fork the repository
2. Create a feature branch
3. Commit your changes
4. Push to the branch
5. Create a Pull Request

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Support

For support, please contact your security operations team or create an issue in the repository.

## Acknowledgments

- [shadcn/ui](https://ui.shadcn.com) for React components
- [FastAPI](https://fastapi.tiangolo.com/) for the backend framework
- [Microsoft Defender](https://www.microsoft.com/en-us/security/business/threat-protection/microsoft-defender-endpoint) for email security
- [Jira](https://www.atlassian.com/software/jira) for ticket management
- [Zscaler](https://www.zscaler.com/) for URL categorization