# Contributing to PESU Auth Link Portal

Thank you for your interest in contributing to the **PESU Auth Link Portal**! This document provides guidelines and instructions for setting up your development environment and contributing to the project.

---

<details>
<summary>Table of Contents</summary>

- [Contributing to Auth Link Portal](#contributing-to-auth-link-portal)
- [Getting Started](#getting-started)
- [Development Environment Setup](#development-environment-setup)
    - [Prerequisites](#prerequisites)
    - [Setting Up Your Environment](#setting-up-your-environment)
    - [Set Up Environment Variables](#set-up-environment-variables)
    - [Database Setup](#database-setup)
- [Running the App](#running-the-application)
- [Submitting Changes](#submitting-changes)
    - [Create a Branch](#create-a-branch)
    - [Make and Commit Changes](#make-and-commit-changes)
    - [Push and Open a Pull Request](#push-and-open-a-pull-request)
- [Need Help?](#need-help)
- [Security](#security)
- [Code Style Guide](#code-style-guide)
    - [General Guidelines](#general-guidelines)
- [GitHub Labels](#github-labels)
- [Feature Suggestions](#feature-suggestions)
- [License](#license)

</details>

---

## Getting Started

### Development Workflow

The standard workflow for contributing is as follows:

1. Clone the repository to your local machine, or fork it and then clone your fork.
2. Create a new branch with the format `(discord-username)/feature-description` for your feature or bug fix.
3. Make your changes and commit them with clear, descriptive messages.
4. Push your branch to the repository (or your fork).
5. Create a Pull Request (PR) against the repository's `dev` branch (not `main`).
6. Follow the PR template when creating your pull request.
7. Wait for review and feedback from the maintainers, address any comments or suggestions.
8. Once approved, your changes will be merged into the `dev` branch.

**⚠️ Important**: Direct PRs to `main` will be closed. All contributions must target the `dev` branch.

---

## 🛠️ Development Environment Setup

This section provides instructions for setting up your development environment to work on the PESU Discord Bot project.

### Prerequisites

- Node.js (v20 or higher)
- Git
- MongoDB (local instance or cloud service like MongoDB Atlas)
- Discord Application with OAuth Credentials and Bot Token

### Setting Up Your Environment

#### Using pip

1. **Clone the repository (or your fork) and navigate to the project:**
   ```bash
   # Option 1: Clone the main repository
   git clone https://github.com/pesu-dev/auth-link-portal.git
   cd auth-link-portal
   
   # Option 2: Clone your fork
   git clone https://github.com/your-github-username/auth-link-portal.git
   cd auth-link-portal
   ```

2. **Install dependencies:**
   ```bash
   npm install
   # or
   yarn install
   # or
   pnpm install
   # or
   bun install
   ```

### Set Up Environment Variables

1. **Create a `.env` file in the `src` directory:**
   ```bash
   cp .env.example .env
   ```

2. **Configure your environment variables:**
   Open the `.env` file and add the following variables:
   ```env
   # Discord OAuth
   CLIENT_ID=
   CLIENT_SECRET=
   REDIRECT_URI=http://localhost:3000/auth

   # Discord Bot
   BOT_TOKEN=

   # MongoDB
   MONGO_URI=

   # App Environment
   APP_ENV=dev

   # JWT Session
   JWT_SESSION_SECRET=

   # Backend API
   BACKEND_API_URL=http://localhost:3001/api
   BACKEND_API_TOKEN=
   ```

   Replace the placeholder values with your actual credentials:
   - `CLIENT_ID`, `CLIENT_SECRET`: From your Discord Application (OAuth2)
   - `REDIRECT_URI`: Should match your Discord OAuth2 redirect URI
   - `BOT_TOKEN`: From your Discord Application's Bot section
   - `MONGO_URI`: Your MongoDB connection string
   - `APP_ENV`: Set to `dev` for development
   - `JWT_SESSION_SECRET`: Any strong secret for JWT session encryption
   - `BACKEND_API_URL`: URL for backend API (default: `http://localhost:3001/api`)
   - `BACKEND_API_TOKEN`: Token for backend API authentication

### Database Setup

The app uses MongoDB to store user and verification data.


Ensure you have:
1. A MongoDB instance running (local or cloud)
2. Proper connection string in your `.env` file
3. Appropriate database permissions for read/write operations

---

## 🧰 Running the Application

To run the app locally for development:

```bash
npm run dev
# or
yarn dev
# or
pnpm dev
# or
bun dev
```

The app will start and be available at [http://localhost:3000](http://localhost:3000).


**Note**: Make sure you have set up your Discord Application and MongoDB instance for development testing.


---

## 🚀 Submitting Changes

### 🔀 Create a Branch

Start by creating a new branch following the naming convention:

```bash
git checkout -b your-discord-username/feature-description
```

Replace `your-discord-username` with your actual Discord username and `feature-description` with a brief description of what you're working on.

### ✏️ Make and Commit Changes

After making your changes, commit them with clear messages:

```bash
git add required-files-only
git commit -m "Add new moderation command for timeout management"
```

Use descriptive commit messages that explain what the change does.

### 📤 Push and Open a Pull Request

1. **Push your branch to the repository (or your fork):**
   ```bash
   git push origin your-discord-username/feature-description
   ```

2. **Open a Pull Request on GitHub targeting the `dev` branch.**

3. **Follow the PR template when creating your pull request.**

---

## ❓ Need Help?

If you get stuck or have questions:

1. Check the [README.md](../README.md) for setup and usage info.
2. Review the [project board](https://github.com/orgs/pesu-dev/projects/4/views/11) to see current work and track progress.
3. Reach out to the maintainers on PESU Discord.
   - Use the appropriate development channels for questions.
   - Search for existing discussions before posting.
4. Open a new issue if you're facing something new or need clarification.

---

## 🔐 Security

If you discover a security vulnerability, **please do not open a public issue**.

Instead, report it privately by contacting the maintainers. We take all security concerns seriously and will respond promptly.

**Important**: Never commit sensitive information like bot tokens, database credentials, or API keys to the repository.

---

## ✨ Code Style Guide

To keep the codebase clean and maintainable, please follow these conventions:

### ✅ General Guidelines

- Write clean, readable code with meaningful variable and function names
- Use type hints where appropriate (Python 3.9+ syntax)
- Keep functions focused and modular
- Follow PEP 8 style guidelines
- Use async/await for all Discord.py operations

---

## 🏷️ GitHub Labels

We use GitHub labels to categorize issues and PRs. Here's a quick guide to what they mean:

| Label              | Purpose                                         |
|--------------------|-------------------------------------------------|
| `good first issue` | Beginner-friendly, simple issues to get started |
| `bug`              | Something is broken or not working as intended  |
| `enhancement`      | Proposed improvements or new features           |
| `documentation`    | Docs, comments, or README-related updates       |
| `question`         | Open questions or clarifications                |
| `help wanted`      | Maintainers are seeking help or collaboration   |

When creating or working on an issue/PR, feel free to suggest an appropriate label if not already applied.

---

## 🧩 Feature Suggestions

If you want to propose a new feature:

1. Check if it already exists on the [project board](https://github.com/orgs/pesu-dev/projects/4/views/8)
2. Open a new issue with a clear description
3. Explain the use case and how it benefits the PESU Discord community
4. Consider Discord's rate limits and bot permissions

---

## 📄 License

By contributing to this repository, you agree that your contributions will be licensed under the same license as the project. See [`LICENSE`](../LICENSE) for full license text.