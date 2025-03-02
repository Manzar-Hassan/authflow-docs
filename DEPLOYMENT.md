# Deployment Guides

## Frontend Deployment (Vercel)

1. Push your code to GitHub
2. Connect your repository to Vercel
3. Configure build settings:
   ```
   Build Command: npm run build
   Output Directory: .next
   Install Command: npm install
   ```
4. Set environment variables in Vercel dashboard
5. Deploy

## Frontend Deployment (Manual/VPS)

1. Build the application:
   ```bash
   npm run build
   ```
2. Install PM2:
   ```bash
   npm install -g pm2
   ```
3. Start the application:
   ```bash
   pm2 start npm --name "authflow-frontend" -- start
   ```

## Backend Deployment (Ubuntu/Nginx)

1. Set up Ubuntu server
2. Install required packages:
   ```bash
   sudo apt update
   sudo apt install python3-pip python3-venv nginx
   ```

3. Clone repository and set up virtual environment:
   ```bash
   git clone <repository-url>
   cd authflow-backend
   python3 -m venv venv
   source venv/bin/activate
   pip install -r requirements.txt
   ```

4. Configure Gunicorn:
   ```bash
   pip install gunicorn
   gunicorn authflow.wsgi:application --bind 0.0.0.0:8000
   ```

5. Create Nginx configuration:
   ```nginx
   server {
       listen 80;
       server_name your-domain.com;

       location / {
           proxy_pass http://127.0.0.1:8000;
           proxy_set_header Host $host;
           proxy_set_header X-Real-IP $remote_addr;
       }
   }
   ```

6. Set up SSL with Let's Encrypt:
   ```bash
   sudo apt install certbot python3-certbot-nginx
   sudo certbot --nginx -d your-domain.com
   ```

## Package Deployment (npm)

1. Update version in package.json
2. Build the package:
   ```bash
   npm run build
   ```
3. Create npm account if needed:
   ```bash
   npm adduser
   ```
4. Publish package:
   ```bash
   npm publish --access public
   ```