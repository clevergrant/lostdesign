# lostdesign

## Project setup
```
yarn install
```

### Compiles and hot-reloads for development
```
yarn serve
```

### Compiles and minifies for production
```
yarn build
```

### Lints and fixes files
```
yarn lint
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).

## Deployment to Netlify

This project is set up for automatic deployments to Netlify.

### Setup Instructions:

1. Push your repository to GitHub.
2. Sign up for a Netlify account if you don't have one already.
3. Create a new site from Git in Netlify:
   - Connect to your GitHub account
   - Select your repository
   - Use the following build settings:
     - Build command: `yarn build`
     - Publish directory: `dist`
4. Click "Deploy site"

Netlify will automatically deploy your site when you push changes to your GitHub repository.

### Manual Deployment:

If you prefer to deploy manually:

```
# Build the project
yarn build

# Deploy using Netlify CLI
netlify deploy --prod
```

Make sure you have installed the Netlify CLI: `npm install -g netlify-cli`
