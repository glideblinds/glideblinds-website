# Google Places API Integration Setup Guide

## 🚀 **What We've Implemented**

Your contact form now uses **Google Places API** for professional address autocomplete instead of the static database. This provides:

- ✅ **Real-time address suggestions** from Google's global database
- ✅ **Accurate postal codes** and street addresses
- ✅ **Professional appearance** similar to AddressComplete
- ✅ **Canada-focused results** (restricted to Canadian addresses)
- ✅ **Custom styling** that matches your website design

## 🔑 **Step 1: Get Your Google API Key**

### 1. Go to Google Cloud Console
- Visit: [https://console.cloud.google.com/](https://console.cloud.google.com/)
- Sign in with your Google account

### 2. Create a New Project (or select existing)
- Click on the project dropdown at the top
- Click "New Project"
- Name it: `GlideBlinds-Website`
- Click "Create"

### 3. Enable the Places API
- In the left sidebar, click "APIs & Services" → "Library"
- Search for "Places API"
- Click on "Places API"
- Click "Enable"

### 4. Create API Credentials
- Go to "APIs & Services" → "Credentials"
- Click "Create Credentials" → "API Key"
- Copy your new API key

### 5. Restrict the API Key (Recommended)
- Click on your new API key
- Under "Application restrictions", select "HTTP referrers (web sites)"
- Add your domain: `*.glideblinds.ca/*` and `*.glideblinds.com/*`
- Under "API restrictions", select "Restrict key"
- Choose "Places API" from the dropdown
- Click "Save"

## 🔧 **Step 2: Update Your Website**

### Replace the API Key in `contact.html`
Find this line in your HTML file:
```html
<script src="https://maps.googleapis.com/maps/api/js?key=YOUR_GOOGLE_API_KEY&libraries=places"></script>
```

Replace `YOUR_GOOGLE_API_KEY` with your actual API key:
```html
<script src="https://maps.googleapis.com/maps/api/js?key=AIzaSyB1234567890abcdefghijklmnopqrstuvwxyz&libraries=places"></script>
```

## 🎯 **Step 3: Test the Integration**

### 1. Open your contact page
### 2. Click on any address input field
### 3. Start typing an address (e.g., "123 Bank Street")
### 4. You should see Google's autocomplete suggestions appear

## 💰 **Pricing Information**

### Google Places API Costs (as of 2024):
- **Free Tier**: $200 credit per month
- **Places Autocomplete**: $2.83 per 1,000 requests
- **Typical Usage**: 100-500 requests per month for a small business
- **Estimated Cost**: $0.28 - $1.42 per month

### To Monitor Usage:
1. Go to Google Cloud Console
2. Click "Billing" in the left sidebar
3. Set up billing alerts at $50, $100, $200 thresholds

## 🎨 **Customization Options**

### Change Country Restriction
Currently set to Canada only. To allow other countries:
```javascript
componentRestrictions: { country: ['ca', 'us'] } // Canada + USA
```

### Change Address Types
Currently set to full addresses. Other options:
```javascript
types: ['geocode'] // Cities, neighborhoods, etc.
types: ['establishment'] // Businesses, points of interest
types: ['(cities)'] // Cities only
```

### Custom Styling
The CSS automatically styles the Google Places dropdown to match your website's yellow theme.

## 🚨 **Important Security Notes**

### 1. **Never expose your API key** in public repositories
### 2. **Use HTTP referrer restrictions** to limit usage to your domain
### 3. **Monitor your usage** to avoid unexpected charges
### 4. **Set up billing alerts** to stay informed

## 🔍 **Troubleshooting**

### Issue: "Google Maps API error: RefererNotAllowedMapError"
**Solution**: Add your domain to the API key restrictions

### Issue: "Google Maps API error: ApiNotActivatedMapError"
**Solution**: Enable the Places API in Google Cloud Console

### Issue: No autocomplete suggestions appear
**Solution**: Check browser console for JavaScript errors

### Issue: Autocomplete works but styling looks wrong
**Solution**: Ensure the CSS is properly loaded and not overridden

## 📱 **Mobile Responsiveness**

The Google Places autocomplete is fully responsive and works on:
- ✅ Desktop computers
- ✅ Tablets
- ✅ Mobile phones
- ✅ All modern browsers

## 🎉 **Benefits of This Implementation**

1. **Professional Appearance** - Looks like AddressComplete
2. **Global Accuracy** - Uses Google's verified address database
3. **Real-time Updates** - Always current with latest addresses
4. **Cost-effective** - Very affordable for small business usage
5. **Customizable** - Easy to modify styling and behavior
6. **Reliable** - Google's infrastructure ensures 99.9% uptime

## 📞 **Need Help?**

If you encounter any issues:
1. Check the browser console for error messages
2. Verify your API key is correct
3. Ensure the Places API is enabled
4. Check your domain restrictions
5. Monitor your API usage in Google Cloud Console

---

**Your website now has enterprise-level address autocomplete functionality!** 🎯
