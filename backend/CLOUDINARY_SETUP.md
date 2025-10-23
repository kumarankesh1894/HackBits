# Cloudinary Setup Guide

## Environment Variables Required

Add these environment variables to your `.env` file:

```env
# Cloudinary Configuration
CLOUDINARY_CLOUD_NAME=your_cloud_name
CLOUDINARY_API_KEY=your_api_key
CLOUDINARY_API_SECRET=your_api_secret
```

## How to Get Cloudinary Credentials

1. **Create a Cloudinary Account** (if you don't have one)
   - Go to [cloudinary.com](https://cloudinary.com)
   - Sign up for a free account

2. **Get Your Credentials**:
   - Go to your Cloudinary Dashboard
   - You'll find your credentials in the "Product Environment Credentials" section:
     - **Cloud Name**: Your cloud name
     - **API Key**: Your API key
     - **API Secret**: Your API secret

3. **Set Up Upload Presets** (Optional but recommended):
   - Go to Settings > Upload
   - Create a new upload preset for payment proofs
   - Set folder to `hackathon/payment-proofs`
   - Enable "Auto-generate unique filename"

## Features Included

### Image Optimization
- **Automatic Compression**: Images are compressed using Sharp before upload
- **WebP Format**: Modern, efficient image format
- **Smart Resizing**: Max 1200x1200px while maintaining aspect ratio
- **Quality Optimization**: 80% quality with auto-optimization

### Cloudinary Benefits
- **Global CDN**: Fast image delivery worldwide
- **Automatic Format Selection**: Serves best format based on browser
- **Responsive Images**: Automatic resizing for different devices
- **Image Transformations**: On-the-fly image processing
- **Analytics**: Track image usage and performance

### Upload Configuration
- **Folder Structure**: `hackathon/payment-proofs/`
- **Unique Naming**: `team-{teamId}-{timestamp}-{random}`
- **Tags**: `payment-proof`, `team-{teamId}`
- **Context**: Team ID, original filename, upload timestamp

## Testing the Setup

Once configured, the payment upload will:
1. Compress images to WebP format (80% quality)
2. Resize to max 1200x1200px
3. Upload to Cloudinary with unique naming
4. Store the secure URL in the database
5. Return compression statistics

## Free Tier Limits

Cloudinary's free tier includes:
- 25 GB storage
- 25 GB bandwidth per month
- 25,000 transformations per month
- 1,000 API requests per month

This should be sufficient for most hackathon projects!

## Security Features

- **Secure URLs**: All images use HTTPS
- **Access Control**: Images are private by default
- **Unique Naming**: Prevents unauthorized access
- **Team Association**: Each image is tagged with team ID
