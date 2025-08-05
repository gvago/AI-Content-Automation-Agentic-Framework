# Content Creation Ecosystem - API Setup Guide

## Overview
This guide helps you configure all the API keys and services required for your comprehensive content creation ecosystem. The system integrates multiple platforms and services to provide automated content creation, research, and distribution capabilities.

## Quick Setup Checklist

### 1. Environment File Setup
- [ ] Copy `.env.example` to `.env`
- [ ] Configure at minimum: `ANTHROPIC_API_KEY`, `FAL_AI_API_KEY`
- [ ] Add social media API keys for posting capabilities
- [ ] Configure email marketing service of choice
- [ ] Set up research and SEO API keys

### 2. Required API Keys (High Priority)

#### AI & Content Generation
| Service | Required Keys | Purpose | Get Keys From |
|---------|---------------|---------|---------------|
| **Anthropic Claude** | `ANTHROPIC_API_KEY` | Primary AI for content creation | [console.anthropic.com](https://console.anthropic.com/) |
| **FAL.AI** | `FAL_AI_API_KEY` | Image/video generation | [fal.ai](https://fal.ai/) |
| **OpenRouter** | `OPENROUTER_API_KEY` | Alternative LLMs | [openrouter.ai](https://openrouter.ai/) |

#### Social Media Platforms
| Platform | Required Keys | Purpose | Get Keys From |
|----------|---------------|---------|---------------|
| **X (Twitter)** | `TWITTER_API_KEY`<br>`TWITTER_API_SECRET`<br>`TWITTER_ACCESS_TOKEN`<br>`TWITTER_ACCESS_TOKEN_SECRET`<br>`TWITTER_BEARER_TOKEN` | Tweet posting and thread creation | [X API Documentation](http://docs.x.com/x-api/introduction) |
| **LinkedIn** | `LINKEDIN_ACCESS_TOKEN`<br>`LINKEDIN_CLIENT_ID`<br>`LINKEDIN_CLIENT_SECRET` | Professional content posting | [linkedin.com/developers](https://www.linkedin.com/developers/) |

#### Email Marketing (Choose One)
| Service | Required Keys | Purpose | Get Keys From |
|---------|---------------|---------|---------------|
| **Mailchimp** | `MAILCHIMP_API_KEY`<br>`MAILCHIMP_SERVER_PREFIX` | Email campaigns and automation | [mailchimp.com/developer](https://mailchimp.com/developer/) |
| **SendGrid** | `SENDGRID_API_KEY` | Email delivery service | [sendgrid.com](https://sendgrid.com/) |
| **Klaviyo** | `KLAVIYO_API_KEY` | E-commerce email marketing | [klaviyo.com/developers](https://www.klaviyo.com/developers) |

### 3. Research & SEO APIs (Recommended)

| Service | Required Keys | Purpose | Get Keys From |
|---------|---------------|---------|---------------|
| **Google Search** | `GOOGLE_SEARCH_API_KEY`<br>`GOOGLE_CSE_ID` | Web research and trend analysis | [console.cloud.google.com](https://console.cloud.google.com/) |
| **SEMrush** | `SEMRUSH_API_KEY` | SEO research and competitor analysis | [semrush.com/api](https://www.semrush.com/api/) |
| **Ahrefs** | `AHREFS_API_KEY` | Alternative SEO research | [ahrefs.com/api](https://ahrefs.com/api/) |
| **SERP API** | `SERP_API_KEY` | Search results analysis | [serpapi.com](https://serpapi.com/) |

## Detailed Setup Instructions

### Step 1: Create Environment File
```bash
# Copy the example file
cp .env.example .env

# Edit with your preferred editor
nano .env  # or vim, code, etc.
```

### Step 2: Configure Core Services

#### Anthropic Claude (REQUIRED)
1. Visit [console.anthropic.com](https://console.anthropic.com/)
2. Create an account or sign in
3. Navigate to API Keys section
4. Generate a new API key
5. Add to `.env`: `ANTHROPIC_API_KEY=your_key_here`

#### FAL.AI for Visual Content (REQUIRED)
1. Visit [fal.ai](https://fal.ai/)
2. Sign up for an account
3. Go to API settings
4. Generate API key
5. Add to `.env`: `FAL_AI_API_KEY=your_key_here`

#### X (Twitter) API Setup
1. Apply for developer account at [X API Documentation](http://docs.x.com/x-api/introduction)
2. Create a new app in your developer dashboard
3. Generate the following keys (ALL REQUIRED for posting functionality):

   **Consumer Keys (identifies your app):**
   - API Key → `TWITTER_API_KEY`
   - API Secret → `TWITTER_API_SECRET`
   
   **Authentication Tokens (posting capability):**
   - Access Token → `TWITTER_ACCESS_TOKEN`  
   - Access Token Secret → `TWITTER_ACCESS_TOKEN_SECRET`
   
   **Bearer Token (read operations):**
   - Bearer Token → `TWITTER_BEARER_TOKEN`

4. Add all 5 keys to your `.env` file

**Note**: For posting tweets, X API requires OAuth 1.0a authentication (Consumer Keys + Access Tokens). Bearer Token alone cannot post tweets but is useful for reading public data.

#### LinkedIn API Setup
1. Create a LinkedIn App at [linkedin.com/developers](https://www.linkedin.com/developers/)
2. Request necessary permissions for content posting
3. Generate access token through OAuth flow
4. Add credentials to `.env` file

### Step 3: Choose Email Marketing Service

**For Mailchimp:**
1. Get API key from Account → Extras → API keys
2. Find your server prefix (e.g., 'us1', 'us2') in the API key
3. Configure both `MAILCHIMP_API_KEY` and `MAILCHIMP_SERVER_PREFIX`

**For SendGrid:**
1. Create API key in Settings → API Keys
2. Choose "Restricted Access" with Mail Send permissions
3. Configure `SENDGRID_API_KEY`

### Step 4: Setup Research APIs

**Google Search API:**
1. Enable Custom Search API in Google Cloud Console
2. Create a Custom Search Engine at [cse.google.com](https://cse.google.com/)
3. Get both API key and Search Engine ID
4. Configure `GOOGLE_SEARCH_API_KEY` and `GOOGLE_CSE_ID`

**SEO Tools:**
- Choose either SEMrush or Ahrefs based on your existing subscriptions
- Both provide API access with paid accounts

### Step 5: Verify Configuration

After setting up your `.env` file, verify each agent can access its required APIs:

1. **Test API connections** before running campaigns
2. **Check rate limits** for each service
3. **Verify permissions** for posting to social platforms
4. **Test email deliverability** with your chosen service

## Agent-Specific API Requirements

| Agent | Required APIs | Optional APIs |
|-------|---------------|---------------|
| **content-director** | None (orchestrator) | All (for delegation) |
| **content-research-analyst** | Google Search API | SEMrush/Ahrefs, SERP API |
| **x-poster** | Twitter API (all 5 keys) | None |
| **linkedin-content-specialist** | LinkedIn API (3 keys) | None |
| **email-marketing-specialist** | Email service (choose one) | SMTP fallback |
| **long-form-content-writer** | Anthropic API | OpenRouter, Google Search |
| **visual-content-strategist** | FAL.AI API | None |

## Security Best Practices

### Environment Security
- ✅ Never commit `.env` file to version control
- ✅ Use `.env` only in local development
- ✅ Use proper secrets management in production
- ✅ Regularly rotate API keys
- ✅ Monitor API usage and costs

### API Key Management
- Store keys securely and never log them
- Use least-privilege principles for API permissions
- Implement rate limiting and error handling
- Monitor for unauthorized API usage

## Troubleshooting

### Common Issues

**"API Key Invalid" Errors:**
1. Check `.env` file syntax (no spaces around `=`)
2. Verify key is correctly copied (no extra characters)
3. Ensure key has proper permissions
4. Check if key needs activation time

**Rate Limit Errors:**
1. Review API usage limits for each service
2. Implement proper backoff strategies
3. Consider upgrading to higher-tier plans
4. Spread requests across time

**Permission Errors:**
1. Verify OAuth scopes for social media APIs
2. Check app permissions in developer dashboards
3. Ensure tokens haven't expired
4. Re-authenticate if necessary

### Getting Help

1. Check service-specific documentation
2. Review API status pages for outages
3. Test individual API calls outside the system
4. Contact support for service-specific issues

## Cost Management

### Estimated Monthly Costs (Usage-Dependent)
- **Anthropic Claude**: $20-100+ (based on content volume)
- **FAL.AI**: $10-50+ (based on image generation)
- **Twitter API**: $100+ (for posting capabilities)
- **LinkedIn API**: Free tier available
- **Email Services**: $10-50+ (based on list size)
- **Research APIs**: $50-200+ (based on usage)

### Cost Optimization Tips
- Start with free tiers where available
- Monitor usage dashboards regularly
- Set up billing alerts
- Use caching to reduce API calls
- Consider batch processing for efficiency

## Next Steps

After completing the API setup:

1. **Test each agent individually** to verify functionality
2. **Run a small test campaign** with the content-director
3. **Monitor performance and costs** for first week
4. **Scale up usage** as you verify stability
5. **Set up monitoring and alerts** for production use

---

*Last updated: [Current Date]*
*Version: 1.0*