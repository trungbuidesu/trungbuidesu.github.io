# trungbuidesu.github.io

React TypeScript application hosted on GitHub Pages, built with Vite.

## 🚀 Development

### Prerequisites
- Node.js 20+ 
- npm

### Install dependencies
```bash
npm install
```

### Run development server
```bash
npm run dev
```

The app will be available at `http://localhost:5173`

### Build for production
```bash
npm run build
```

### Preview production build locally
```bash
npm run preview
```

## 📦 Deployment

### Method 1: Automatic Deployment (Recommended)
This project uses GitHub Actions for automatic deployment.

1. Go to your GitHub repository settings
2. Navigate to **Settings** → **Pages**
3. Under **Build and deployment**, select:
   - **Source**: GitHub Actions
4. Push your code to the `main` branch
5. The workflow will automatically build and deploy your site

Your site will be available at: `https://trungbuidesu.github.io`

### Method 2: Manual Deployment using gh-pages
```bash
npm run deploy
```

This will:
1. Build the project (`npm run build`)
2. Deploy the `dist` folder to the `gh-pages` branch

**Note**: If using this method, make sure to set GitHub Pages source to the `gh-pages` branch in your repository settings.

## 🛠️ Tech Stack

- **React** 19.2.0
- **TypeScript** 5.9.3
- **Vite** 7.2.4
- **ESLint** for code linting

## 📝 Project Structure

```
.
├── .github/
│   └── workflows/
│       └── deploy.yml      # GitHub Actions workflow
├── public/                 # Static assets
│   └── .nojekyll          # Prevents Jekyll processing
├── src/                    # Source code
│   ├── App.tsx
│   ├── main.tsx
│   └── ...
├── index.html
├── package.json
├── tsconfig.json
├── vite.config.ts
└── README.md
```

## 🔧 Configuration

### Vite Config
The `vite.config.ts` is configured with:
- `base: '/'` - For GitHub Pages user site (username.github.io)
- If this was a project site, you would use: `base: '/repo-name/'`

### GitHub Actions
The `.github/workflows/deploy.yml` workflow:
- Triggers on push to `main` branch
- Can be manually triggered from the Actions tab
- Builds and deploys to GitHub Pages automatically

## 📄 License

This project is open source and available under the MIT License.
