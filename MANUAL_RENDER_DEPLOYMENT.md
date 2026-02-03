# 🚀 Manual Render Deployment Guide
## Step-by-Step Instructions

### 📋 What You Need:
- GitHub account (free)
- Render account (free)
- Your AI API files (already prepared)

---

## 🗂️ Files Ready for Deployment

Your folder contains these essential files:
✅ `api_server.py` - Cloud-optimized FastAPI app
✅ `requirements_api.txt` - Python dependencies  
✅ `render.yaml` - Render configuration
✅ `RENDER_GUIDE.md` - Complete deployment guide

---

## 🚀 Step 1: Create GitHub Repository

1. **Go to GitHub**: https://github.com/new
2. **Repository name**: `ai-evaluation-api`
3. **Description**: `AI Reasoning & Evaluation Platform`
4. **Visibility**: Public (easier for free tier)
5. **Don't initialize** with README, .gitignore, or license
6. **Click "Create repository"**

---

## 📤 Step 2: Upload Your Files

### Option A: GitHub Web Interface (Easiest)
1. Click "uploading an existing file" link
2. Drag and drop these files:
   - `api_server.py`
   - `requirements_api.txt`
   - `render.yaml`
3. Add commit message: "Initial AI Evaluation API deployment"
4. Click "Commit changes"

### Option B: GitHub Desktop (If available)
1. Install GitHub Desktop
2. Clone your empty repository
3. Copy your files into the repository folder
4. Commit and push

---

## 🔗 Step 3: Connect to Render

1. **Go to Render**: https://render.com
2. **Sign Up** with your GitHub account
3. **Authorize** Render to access your repositories
4. **Click "New +"** → **"Web Service"**

---

## ⚙️ Step 4: Configure Your Web Service

1. **Connect Repository**:
   - Choose your `ai-evaluation-api` repository
   - Select branch: `main`
   - Click "Connect"

2. **Render Auto-Detection**:
   - Render should detect your `render.yaml`
   - If not, configure manually:
     - **Name**: `ai-evaluation-api`
     - **Runtime**: `Python 3`
     - **Build Command**: `pip install -r requirements_api.txt`
     - **Start Command**: `uvicorn api_server:app --host 0.0.0.0 --port $PORT`

3. **Environment Variables**:
   - `PORT`: `10000`
   - `PYTHON_VERSION`: `3.9`

4. **Health Check**:
   - Path: `/health`
   - Auto-check interval: 30s

---

## 🚀 Step 5: Deploy!

1. **Click "Create Web Service"**
2. **Wait for deployment** (2-3 minutes)
3. **Monitor progress** in Render dashboard
4. **Success!** Your API is live

---

## 🌐 Your Live API URLs

Once deployed, your API will be available at:

### **Interactive Documentation**:
```
https://ai-evaluation-api.onrender.com/docs
```

### **Health Check**:
```
https://ai-evaluation-api.onrender.com/health
```

### **API Endpoints**:
```
https://ai-evaluation-api.onrender.com/evaluate
https://ai-evaluation-api.onrender.com/compare
https://ai-evaluation-api.onrender.com/info
https://ai-evaluation-api.onrender.com/stats
```

---

## 🧪 Test Your Deployed API

### Quick Health Test:
```bash
curl https://ai-evaluation-api.onrender.com/health
```

### Test Answer Evaluation:
```bash
curl -X POST "https://ai-evaluation-api.onrender.com/evaluate" \
  -H "Content-Type: application/json" \
  -d '{
    "problem": "What is the best way to learn programming?",
    "answer": "Start with Python because it's beginner-friendly and has great documentation."
  }'
```

### Test Multi-Answer Comparison:
```bash
curl -X POST "https://ai-evaluation-api.onrender.com/compare" \
  -H "Content-Type: application/json" \
  -d '{
    "problem": "Explain machine learning simply",
    "answers": [
      {"content": "ML is like teaching computers to recognize patterns from examples.", "id": "ans1"},
      {"content": "Machine learning analyzes data to find patterns and make predictions.", "id": "ans2"}
    ]
  }'
```

---

## 🎯 Success Indicators

✅ **Green status** in Render dashboard
✅ **Health check passes** (status 200)
✅ **API docs load** in browser
✅ **Test requests work** correctly

---

## 🔧 Troubleshooting

### If Build Fails:
1. Check build logs in Render
2. Verify `requirements_api.txt` is correct
3. Make sure `api_server.py` has no syntax errors

### If Health Check Fails:
1. Wait 2-3 minutes for full startup
2. Check service logs
3. Verify health endpoint path: `/health`

### If API is Slow:
1. Free tier has limited resources
2. Consider upgrading ($7/month)
3. Optimize code for performance

---

## 📈 Free Tier Limits

- **750 hours/month** (enough for 24/7)
- **512MB RAM**
- **Shared CPU**
- **10GB bandwidth**
- **Automatic HTTPS**
- **Custom domains** (paid tier)

---

## 🎉 You're Global!

Your AI Evaluation API is now:
✅ **Accessible from anywhere**
✅ **HTTPS secured**
✅ **24/7 available**
✅ **Ready for users**

### Share this link with anyone:
```
https://ai-evaluation-api.onrender.com/docs
```

---

## 🔄 Updates & Maintenance

### To Update Your API:
1. Make changes to your code
2. Upload updated files to GitHub
3. Render auto-redeploys
4. New version live in 2-3 minutes

### Monitor Performance:
- Check Render dashboard
- Monitor response times
- Track usage statistics
- Upgrade when needed

---

**🚀 Your AI Evaluation API is now deployed globally on Render!**
