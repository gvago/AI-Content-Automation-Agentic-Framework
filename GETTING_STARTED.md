# Getting Started with Your Content Creation Ecosystem

Welcome to your comprehensive AI-powered content creation framework! This guide will get you up and running in under 30 minutes.

## 🚀 Quick Start (5 Minutes)

### Step 1: Basic Setup
```bash
# 1. Copy the environment template
cp .env.example .env

# 2. Add your essential API keys (minimum required)
# Edit .env and add at minimum:
ANTHROPIC_API_KEY=your_anthropic_key_here
FAL_AI_API_KEY=your_fal_ai_key_here
```

### Step 2: Test Your First Agent
Open Claude Code and try this simple command:
```
Use the content-director agent to help me create a LinkedIn post about AI productivity tools.
```

### Step 3: Create Your First Campaign
```
I have a product launch next week - a new project management tool. Help me create content across LinkedIn and Twitter to announce it.
```

**That's it!** Your system is now working. Continue reading for full setup and advanced features.

---

## 📋 Complete Setup (30 Minutes)

### Phase 1: API Configuration (15 minutes)

#### Essential APIs (Required)
1. **Anthropic Claude** - [Get API Key](https://console.anthropic.com/)
   - Used by all agents for AI content generation
   - Cost: ~$20-100/month depending on usage

2. **FAL.AI** - [Get API Key](https://fal.ai/)
   - Used for image and video generation
   - Cost: ~$10-50/month depending on image generation volume

#### Social Media APIs (For Posting)
3. **X (Twitter) API** - [X API Documentation](http://docs.x.com/x-api/introduction)
   ```
   # All 5 tokens required for full posting functionality
   TWITTER_API_KEY=your_api_key                    # Consumer Key
   TWITTER_API_SECRET=your_api_secret              # Consumer Secret  
   TWITTER_ACCESS_TOKEN=your_access_token          # User Access Token
   TWITTER_ACCESS_TOKEN_SECRET=your_access_secret  # User Access Secret
   TWITTER_BEARER_TOKEN=your_bearer_token          # App Bearer Token
   ```

4. **LinkedIn API** - [LinkedIn Developers](https://www.linkedin.com/developers/)
   ```
   LINKEDIN_ACCESS_TOKEN=your_token
   LINKEDIN_CLIENT_ID=your_client_id
   LINKEDIN_CLIENT_SECRET=your_client_secret
   ```

#### Email Marketing (Choose One)
5. **Mailchimp** (Recommended for beginners)
   ```
   MAILCHIMP_API_KEY=your_key
   MAILCHIMP_SERVER_PREFIX=us1  # or your server
   ```

#### Research APIs (Recommended)
6. **Google Search API** - [Cloud Console](https://console.cloud.google.com/)
   ```
   GOOGLE_SEARCH_API_KEY=your_key
   GOOGLE_CSE_ID=your_search_engine_id
   ```

### Phase 2: Test Each Agent (10 minutes)

After setting up your APIs, test each agent individually:

#### 1. Test Content Research
```
Use content-research-analyst to research trending topics in [your industry] for this week.
```

#### 2. Test Social Media Creation
```
Use x-poster to create a Twitter thread about the benefits of AI in business.
```

```
Use linkedin-content-specialist to write a professional post about remote work productivity.
```

#### 3. Test Email Marketing
```
Use email-marketing-specialist to create a welcome email sequence for new subscribers to my [business type] newsletter.
```

#### 4. Test Long-form Content
```
Use long-form-content-writer to create a 1500-word blog post about [your topic].
```

#### 5. Test Visual Content
```
Use visual-content-strategist to create captions and visual briefs for an Instagram campaign about [your product/service].
```

### Phase 3: Your First Full Campaign (5 minutes)

Now test the orchestrator with a complete campaign:

```
Use content-director for this campaign:

"I'm launching a new online course about [your topic] next month. I need:
- A blog post announcing the launch
- LinkedIn posts to build anticipation
- Twitter content to drive engagement  
- Email sequence for my subscribers
- Visual content strategy for social media

My target audience is [describe your audience]. The course focuses on [key benefits/topics]."
```

---

## 🎯 Your Content Creation Team

### **content-director** - Your Campaign Manager
- **When to use**: For any multi-platform content campaign
- **What it does**: Analyzes your request, creates strategy, delegates to specialists
- **Example**: "Create a product launch campaign across all channels"

### **content-research-analyst** - Your Intelligence Gatherer  
- **When to use**: Before creating campaigns, to understand trends
- **What it does**: Researches trends, competitors, SEO opportunities
- **Example**: "Research content gaps in the fintech industry"

### **x-poster** - Your Twitter Specialist
- **When to use**: For Twitter/X content creation and posting
- **What it does**: Creates tweets, threads, optimizes for engagement
- **Example**: "Create a Twitter thread about startup fundraising tips"

### **linkedin-content-specialist** - Your Professional Voice
- **When to use**: For LinkedIn content and B2B marketing
- **What it does**: Creates professional posts, articles, thought leadership content
- **Example**: "Write a LinkedIn article about leadership in remote teams"

### **email-marketing-specialist** - Your Email Expert
- **When to use**: For newsletters, email campaigns, automation sequences
- **What it does**: Creates email content, subject lines, sequences
- **Example**: "Create a 7-email nurture sequence for new leads"

### **long-form-content-writer** - Your Blog Writer
- **When to use**: For blog posts, articles, comprehensive content
- **What it does**: Creates SEO-optimized long-form content
- **Example**: "Write a comprehensive guide to content marketing ROI"

### **visual-content-strategist** - Your Visual Coordinator
- **When to use**: For visual content strategy and image generation
- **What it does**: Creates captions, alt text, visual briefs, generates images
- **Example**: "Create visual content strategy for our product launch"

---

## 💡 Quick Usage Tips

### Best Practices for Requests
1. **Be Specific**: Include your industry, audience, and goals
2. **Provide Context**: Share your brand voice, target audience, key messages
3. **Set Expectations**: Mention deadlines, content length, platform preferences
4. **Include Examples**: Reference content you like or want to emulate

### Sample Request Templates

#### For Campaign Creation:
```
Use content-director to create a [campaign type] for [product/service/topic]:

Target Audience: [describe your audience]
Key Messages: [main points you want to communicate]
Platforms: [which platforms to use]
Timeline: [when content should be published]
Goals: [what you want to achieve]
```

#### For Individual Content:
```
Use [agent-name] to create [content type] about [topic]:

Audience: [who this is for]
Tone: [professional/casual/educational/etc.]
Length: [word count or format requirements]
Key Points: [what to include]
```

### Common Workflows

#### Weekly Content Planning:
1. **Monday**: Use content-research-analyst to identify trending topics
2. **Tuesday**: Use content-director to plan week's content across platforms  
3. **Wednesday-Friday**: Let specialists create and refine individual pieces
4. **Weekend**: Review, schedule, and prepare for next week

#### Product Launch Campaign:
1. **Research Phase**: Use content-research-analyst for market insights
2. **Strategy Phase**: Use content-director to plan multi-platform campaign
3. **Creation Phase**: Specialists create platform-specific content
4. **Execution Phase**: Schedule and publish coordinated campaign

---

## 🚨 Troubleshooting Quick Fixes

### "API Key Invalid" Error
- Check `.env` file formatting (no spaces around `=`)
- Verify you copied the complete key
- Ensure key has proper permissions in the service dashboard

### Agent Not Responding
- Confirm the agent name is spelled correctly
- Make sure you're using the exact agent names from the team roster
- Try rephrasing your request more specifically

### Content Quality Issues
- Provide more specific context and requirements
- Include examples of content you like
- Specify your brand voice and target audience
- Ask agents to revise and improve initial outputs

### Rate Limiting Errors  
- Wait a few minutes before retrying
- Consider upgrading API plans for higher limits
- Spread requests across longer time periods

---

## 🎉 You're Ready!

### Next Steps:
1. **Start Small**: Create one piece of content to get familiar
2. **Build Up**: Try a simple 2-platform campaign  
3. **Scale Up**: Use content-director for comprehensive campaigns
4. **Optimize**: Track what works and refine your processes

### Need Help?
- Check `USER_GUIDE.md` for detailed documentation
- Review `WORKFLOW_EXAMPLES.md` for specific use cases
- See `TROUBLESHOOTING.md` for detailed problem solving
- Reference `API_SETUP_GUIDE.md` for technical configuration

---

## 🏆 Success Metrics to Track

### Content Performance:
- Engagement rates across platforms
- Content creation time savings
- Consistency of brand voice
- Campaign reach and impressions

### Operational Efficiency:
- Time from idea to published content
- Number of platforms covered per campaign
- Content repurposing effectiveness
- Team productivity improvements

### Business Impact:
- Lead generation from content
- Brand awareness metrics
- Content-driven conversions
- ROI on content marketing efforts

---

**Welcome to your new content creation superpower! 🚀**

*Questions? Start with a simple request to content-director and let the magic happen.*