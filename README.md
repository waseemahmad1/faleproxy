# Faleproxy

A Node.js web application that fetches a URL, replaces every instance of "Yale" with "Fale" in the document, and displays the modified content.

## Features

- Simple and intuitive user interface
- Fetches web content from any URL
- Replaces all instances of "Yale" with "Fale" (case-insensitive)
- Displays the modified content in an iframe
- Shows original URL and page title in an info bar

## Installation

1. Clone this repository
2. Navigate to the project directory
3. Install dependencies:

```bash
npm install
```

## Usage

1. Start the server:

```bash
npm start
```

2. Open a browser and go to `http://localhost:3001`
3. Enter a URL in the input field (e.g., https://www.yale.edu)
4. Click "Fetch & Replace" to see the modified content

## Development

To run with auto-restart on file changes:

```bash
npm run dev
```

## Testing

The application includes a comprehensive test suite:

- **Unit tests**: Test the Yale-to-Fale replacement logic
- **API tests**: Test the application endpoints
- **Integration tests**: Test the entire application workflow

### Running Tests

```bash
# Run all tests
npm test

# Run tests in watch mode during development
npm run test:watch

# Run tests with coverage for CI/CD
npm run test:ci
```

## CI/CD Pipeline

The repository includes a comprehensive GitHub Actions workflow configuration in `.github/workflows/ci.yml` that:

1. **Tests on every push**: Runs tests on pushes to main/master branches and on pull requests
2. **Multi-version testing**: Tests the application on multiple Node.js versions (18.x, 20.x)
3. **Coverage reports**: Generates and uploads test coverage reports
4. **Preview deployments**: Automatically deploys feature branches to Vercel preview environment
5. **Production deployments**: Automatically deploys to Vercel production ONLY when:
   - Pushing to main/master branch
   - **AND tests pass successfully**

### Setting up CI/CD (Required for HW9)

**Step 1: Enable GitHub Actions**
- GitHub Actions are disabled by default on forks
- Go to `https://github.com/USERNAME/faleproxy/actions`
- Click "I understand my workflows, go ahead and enable them"

**Step 2: Set up Vercel Secrets**

You need to add three secrets to your GitHub repository:

1. **VERCEL_TOKEN**: 
   - Go to https://vercel.com/account/tokens
   - Create a new token
   - Add it as a GitHub secret

2. **VERCEL_ORG_ID**:
   - Found in Vercel account settings
   - Or run `vercel link` and check `.vercel/project.json`

3. **VERCEL_PROJECT_ID**:
   - Found in Vercel project settings
   - Or run `vercel link` and check `.vercel/project.json`

Add these secrets at: `https://github.com/USERNAME/faleproxy/settings/secrets/actions`

**Step 3: Verify Workflow**
- Push changes to a feature branch → Preview deployment
- Merge to main → Production deployment (only if tests pass)
- Tests fail → No production deployment ✅

### HW9 Documentation

For detailed HW9 setup instructions, see:
- `HW9_SETUP_GUIDE.md` - Complete step-by-step setup guide
- `HW9_SUBMISSION_TEMPLATE.md` - Submission template with all required information

## Technologies Used

- Node.js
- Express - Web server framework
- Axios - HTTP client for fetching web pages
- Cheerio - HTML parsing and manipulation
- Vanilla JavaScript for frontend functionality
- Jest, Supertest, and Nock for testing
# CI/CD configured and ready

