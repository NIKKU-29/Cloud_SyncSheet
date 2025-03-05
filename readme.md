# SheetSync Cloud 📊🚀
## Google Sheets API Integration on Cloudflare Workers

[![Deploy with Workers](https://deploy.workers.cloudflare.com/button)](https://deploy.workers.cloudflare.com/?url=https://github.com/NIKKU-29/sheetsync-cloud)

### 🌟 Project Overview

SheetSync Cloud is a powerful serverless solution that seamlessly connects your applications with Google Sheets using Cloudflare Workers. This lightweight, secure middleware enables effortless data synchronization through a simple API endpoint.

### ✨ Key Features

- **Serverless Architecture**: Leverages Cloudflare Workers for scalable, low-latency operations
- **Secure Authentication**: Uses JWT tokens with Google Sheets Service Account
- **Easy Integration**: Simple POST request interface for appending or editing spreadsheet data
- **Flexible Deployment**: Quick setup with minimal configuration

### 🛠 Prerequisites

Before getting started, ensure you have:

- [Node.js](https://nodejs.org/) (v14+ recommended)
- [Wrangler CLI](https://developers.cloudflare.com/workers/cli-wrangler/install-update)
- A Google Cloud Project with:
  - Sheets API enabled
  - Service Account created
  - Credentials generated

### 🚀 Quick Setup

#### 1. Clone the Repository

```bash
git clone https://github.com/NIKKU-29/sheetsync-cloud.git
cd sheetsync-cloud
```

#### 2. Install Dependencies

```bash
npm install
```

#### 3. Configure Environment Variables

Create a `.env` file with the following configurations:

```env
GOOGLE_SHEETS_SERVICE_ACCOUNT=your-service-account-email@your-project.iam.gserviceaccount.com
GOOGLE_SHEETS_PRIVATE_KEY=your-rsa-public-key-jwk-as-string
GOOGLE_SHEETS_SUBSCRIBERS_ID=your-spreadsheet-id
GOOGLE_SHEETS_SUBSCRIBERS_PAGE=your-subscribers-page
```

> 🔐 **Security Tip**: 
> - Convert your RSA private key to a JWK (JSON Web Key) string
> - Never commit sensitive credentials to version control

#### 4. Generate JWK from Private Key

Your original private key might look like:
```
-----BEGIN PRIVATE KEY-----
Your-Private-Key-Here
-----END PRIVATE KEY-----
```

Use a JWT library or online converter to transform this into a JWK string for the `.env` file.

#### 5. Deploy to Cloudflare Workers

```bash
wrangler publish
```

### 📡 API Usage

#### Making a POST Request

Send data to your deployed worker endpoint:

```bash
curl -X POST \
  -H "Content-Type: application/json" \
  -d '{"data": "your-data-here"}' \
  https://your-cloudflare-worker-url.com/endpoint
```

### 🛡 Security Considerations

- Keep environment variables confidential
- Use Cloudflare Workers' built-in secrets management
- Implement additional authentication if handling sensitive data

### 🤝 Contributing

Contributions are welcome! Please:
- Open issues for bugs or feature requests
- Submit pull requests with clear description of changes
- Follow existing code style and conventions

### 📄 License

This project is open-source and available under the [MIT License](LICENSE).

### 🌈 Getting Help

Encountering issues? Check our [GitHub Issues](https://github.com/NIKKU-29/sheetsync-cloud/issues) or reach out to the community.

---

**Happy Syncing!** 📊✨
