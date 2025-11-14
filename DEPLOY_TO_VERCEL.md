# Deploy to Vercel

## Quick Deploy

1. **Install Vercel CLI** (if not already installed):
   ```bash
   npm install -g vercel
   ```

2. **Login to Vercel**:
   ```bash
   vercel login
   ```

3. **Deploy from this directory**:
   ```bash
   vercel
   ```

4. **Set Environment Variables** in Vercel Dashboard:
   - Go to your project settings on vercel.com
   - Navigate to "Environment Variables"
   - Add these variables:
     - `LINKUP_API_KEY` = your-linkup-api-key
     - `OPENAI_API_KEY` = your-openai-api-key
     - `ANTHROPIC_API_KEY` = your-anthropic-api-key (optional)

5. **Redeploy** after setting environment variables:
   ```bash
   vercel --prod
   ```

## Deploy via Vercel Dashboard

1. Go to https://vercel.com/new
2. Import your GitHub repository: `https://github.com/shauryajain21/linkup-events`
3. Configure project:
   - Framework Preset: Other
   - Build Command: (leave empty)
   - Output Directory: (leave empty)
4. Add Environment Variables (same as above)
5. Click "Deploy"

## Important Notes

- The app uses Flask with the `@vercel/python` builder
- Environment variables MUST be set in Vercel Dashboard for the app to work
- The `vercel.json` file is already configured for Flask
- Runtime is set to Python 3.11 in `runtime.txt`

## Verify Deployment

After deployment, visit your Vercel URL and you should see the Event ICP Matcher interface with:
- Linkup branding
- Mock Cerebral Valley speaker data
- Working ICP analysis (once environment variables are set)

## Troubleshooting

If deployment fails:
1. Check Vercel deployment logs
2. Verify all environment variables are set correctly
3. Ensure `requirements.txt` has all dependencies
4. Check that Python version is compatible (3.11)
