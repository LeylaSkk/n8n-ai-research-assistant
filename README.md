# n8n-ai-research-assistant
Intelligent research assistant built with n8n that automatically generates comprehensive reports on any topic. Uses web search + AI analysis to deliver professional research reports via email. Free tier compatible with SerpAPI and Groq.
# AI Research Assistant - n8n Workflow

An intelligent, automated research assistant that generates comprehensive, professional research reports on any topic using web search and AI analysis. Built with n8n, this workflow transforms a simple topic submission into a detailed research report delivered directly to your email.

## Features

- **Web Form Interface**: Clean, user-friendly form for topic submission
- **Intelligent Web Search**: Automated Google search using SerpAPI
- **AI-Powered Analysis**: Advanced research report generation using Groq's Llama models
- **Email Delivery**: Formatted HTML reports sent directly to specified email addresses
- **Free Tier Compatible**: Works with free tiers of all required services
- **No Code Solution**: Fully visual workflow - no programming required

## How It Works

1. **Input**: User submits research topic and email address via web form
2. **Search**: System searches Google for current, relevant information
3. **Analysis**: AI analyzes search results and generates structured research report
4. **Delivery**: Professional report sent to user's email within minutes

## Sample Output

The workflow generates structured reports including:
- Executive Summary
- Key Findings
- Current Trends
- Future Implications
- Source Citations
- Recommended Actions

## Prerequisites

- n8n instance (cloud or self-hosted)
- Gmail account
- Internet connection

## Required API Keys (All Free Tier)

| Service | Purpose | Free Tier | Signup |
|---------|---------|-----------|---------|
| SerpAPI | Web Search | 100 searches/month | [serpapi.com](https://serpapi.com) |
| Groq | AI Analysis | 14,400 requests/day | [console.groq.com](https://console.groq.com) |
| Gmail | Email Delivery | Unlimited | [gmail.com](https://gmail.com) |

## Installation

### 1. Import Workflow
1. Download `ai-research-assistant.json` from this repository
2. Open your n8n instance
3. Click "Import from file" 
4. Select the downloaded JSON file
5. Click "Import"

### 2. Configure API Keys

#### SerpAPI Setup
1. Sign up at [serpapi.com](https://serpapi.com)
2. Get your API key from the dashboard
3. In the "HTTP Request" node, replace `YOUR_SERPAPI_KEY` with your actual key

#### Groq Setup  
1. Sign up at [console.groq.com](https://console.groq.com)
2. Create an API key
3. In the "HTTP Request1" node headers, replace `YOUR_GROQ_KEY` with your actual key

#### Gmail Setup
1. Click on the "Send a message" node
2. Click "Connect my account"
3. Follow OAuth flow to authorize n8n
4. Grant email sending permissions

### 3. Activate Workflow
1. Save the workflow (Ctrl+S)
2. Toggle "Active" in the top right
3. Your form URL will be generated automatically

## Usage

### For End Users
1. Open the form URL (found in the n8n Form trigger node)
2. Enter your research topic (e.g., "artificial intelligence in healthcare")
3. Enter your email address
4. Click Submit
5. Receive comprehensive research report within 2-3 minutes

### For Administrators  
- Monitor workflow executions in n8n dashboard
- Check API usage in respective service dashboards
- Modify AI prompts in the Groq node for different report styles

## Customization Options

### Modify Report Structure
Edit the prompt in the Groq HTTP Request node to change:
- Report sections and headings
- Analysis depth and focus
- Output format (markdown, HTML, plain text)
- Tone and style (academic, business, casual)

### Adjust Search Parameters
In the SerpAPI HTTP Request node, modify:
- Number of search results (`num` parameter)
- Search region/country (`gl` parameter)  
- Search language (`hl` parameter)
- Search type (web, news, images)

### Email Formatting
In the Gmail node, customize:
- Subject line templates
- HTML email styling
- Attachment options
- CC/BCC recipients

## Architecture

```
Web Form → SerpAPI Search → Groq AI Analysis → Gmail Delivery
```

**Node Details:**
- **n8n Form**: Collects user input (topic + email)
- **HTTP Request (SerpAPI)**: Searches web for relevant information
- **HTTP Request (Groq)**: AI analysis and report generation  
- **Gmail**: Formatted email delivery

## API Usage & Costs

### Free Tier Limits
- **SerpAPI**: 100 searches/month (sufficient for moderate use)
- **Groq**: 14,400 requests/day (very generous)
- **Gmail**: No API limits for personal use
- **n8n**: 5 workflows, 5000 executions/month (cloud free tier)

### Scaling Considerations
For high-volume usage:
- SerpAPI paid plans start at $50/month for 5,000 searches
- Groq offers higher rate limits on paid plans
- Consider n8n paid plans for more workflows and executions

## Security Best Practices

- Never commit actual API keys to version control
- Use environment variables for sensitive data
- Regularly rotate API keys
- Monitor API usage for unusual activity
- Restrict form access if needed (authentication, domain restrictions)

## Troubleshooting

### Common Issues

**"Invalid API key" errors**
- Verify API keys are correctly entered
- Check for extra spaces or characters
- Ensure API key has necessary permissions

**"No search results" errors**  
- Verify SerpAPI quota hasn't been exceeded
- Try simpler, more common search terms
- Check internet connectivity

**"JSON parameter needs to be valid JSON" errors**
- Ensure expressions in Groq node are properly formatted
- Verify node references match actual node names
- Test with hardcoded values first

**Email delivery failures**
- Confirm Gmail OAuth connection is active
- Check spam/junk folders
- Verify recipient email addresses are valid

### Debug Mode
Enable debug mode in n8n to see detailed execution logs and identify issues in the workflow chain.

## Contributing

Contributions are welcome! Please:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

### Enhancement Ideas
- PDF report generation
- Multiple output formats
- Research source filtering
- Scheduled/recurring research
- Integration with knowledge bases
- Multi-language support
- Citation management
- Research archiving

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Support

- **n8n Documentation**: [docs.n8n.io](https://docs.n8n.io)
- **SerpAPI Docs**: [serpapi.com/search-api](https://serpapi.com/search-api)
- **Groq API Docs**: [console.groq.com/docs](https://console.groq.com/docs)

## Acknowledgments

- Built with [n8n](https://n8n.io) - powerful workflow automation platform
- Powered by [Groq](https://groq.com) - fast AI inference
- Search powered by [SerpAPI](https://serpapi.com) - Google search API
- Email delivery via [Gmail API](https://developers.google.com/gmail)

---

**Note**: This workflow is designed for research and educational purposes. Always verify important information from multiple sources and consider the limitations of AI-generated content.
