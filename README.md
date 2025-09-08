<p align="center">
  <a href="https://brightdata.com/">
    <img src="https://mintlify.s3.us-west-1.amazonaws.com/brightdata/logo/light.svg" width="300" alt="Bright Data Logo">
  </a>
</p>

# Brand Reputation Monitoring Workflow 🛡️

**AI-powered brand reputation monitoring that automatically searches Google News, analyzes sentiment, and delivers actionable insights via email using [Bright Data's Web Scraper API](https://brightdata.com/products/web-scraper), OpenAI, and SendGrid!**

<div align="center">
  <img src="https://img.shields.io/badge/python-3.8+-blue"/>
  <img src="https://img.shields.io/badge/License-MIT-blue"/>
</div>

---

## Features 🚀

- **Automated News Discovery**: Uses [Bright Data's Search Engine API](https://brightdata.com/products/serp-api) to find Google News pages for your brand queries.
- **Intelligent Content Extraction**: Scrapes news articles at scale using [Bright Data's Web Scraper API](https://brightdata.com/products/web-scraper) with parallel processing.
- **AI-Powered Analysis**: Leverages OpenAI to analyze sentiment, extract insights, and identify the most relevant news for brand monitoring.
- **Smart Content Filtering**: Automatically selects the top news articles most relevant to your brand reputation.
- **Professional Email Reports**: Generates beautifully formatted HTML email reports with sentiment analysis and actionable insights.
- **Automated Delivery**: Sends branded monitoring reports directly to stakeholders via SendGrid.
- **Configurable Monitoring**: Easy-to-customize search queries and recipient lists through JSON configuration.

---

## How It Works 🔄

1. **Configuration Loading**: Reads your monitoring setup from `config.json`
2. **News Discovery**: Searches Google for news pages using your brand queries
3. **Content Extraction**: Scrapes all relevant news pages in parallel
4. **Content Selection**: AI identifies the most important news articles
5. **Detailed Analysis**: Each article gets sentiment analysis and brand insights
6. **Report Generation**: Creates a professional HTML email report
7. **Automated Delivery**: Sends the report to your team via email

---

## Prerequisites 🛠️

- Python 3.8+ 🐍
- [Bright Data API token](https://docs.brightdata.com/api-reference/authentication#how-do-i-generate-a-new-api-key%3F) 🔑
- OpenAI API key 🔑
- SendGrid API key 📧

---

## Installation ⚙️

1. Clone this repository:

    git clone https://github.com/brightdata/brand-reputation-monitoring-workflow
    cd brand-reputation-monitoring-workflow

2. Install dependencies:

    pip install -r requirements.txt

3. Create a `.env` file in the project root with your API keys:

    BRIGHT_DATA_API_TOKEN=your_bright_data_api_token
    OPENAI_API_KEY=your_openai_api_key
    SENDGRID_API_KEY=your_sendgrid_api_key

---

## Configuration 📝

Create a `config.json` in the root directory to customize your brand monitoring:

    {
      "search_queries": [
        "YourBrand news",
        "YourBrand reviews",
        "YourBrand controversy",
        "YourCompany announcement"
      ],
      "num_news": 5,
      "sender": "monitoring@yourcompany.com",
      "recipients": [
        "pr@yourcompany.com",
        "marketing@yourcompany.com",
        "ceo@yourcompany.com"
      ]
    }

**Configuration Fields:**

- `search_queries`: List of search terms to monitor your brand (supports multiple queries)
- `num_news`: Number of top articles to analyze in detail (default: 5)
- `sender`: Email address to send reports from (must be verified in SendGrid)
- `recipients`: List of email addresses to receive monitoring reports

---

## Usage ▶️

Run the brand monitoring workflow:

    python main.py

The workflow will:

1. 🔍 Search for news using your configured queries
2. 📰 Scrape and analyze relevant articles
3. 🧠 Generate AI-powered insights and sentiment analysis
4. 📧 Send a professional HTML report to your team

**Sample Output:**

    Retrieving Google News page URLs for the following search queries: YourBrand news, YourBrand reviews
    2 Google News page URL(s) retrieved!

    Scraping content from each Google News page...
    Google News pages scraped!

    Extracting the most relevant news URLs...
    5 news articles found:
    - https://example.com/news1
    - https://example.com/news2
    ...

    Analyzing each news for brand reputation monitoring...
    News analysis complete!

    Generating HTML email body...
    HTML email body generated!

    Sending the email with the brand reputation monitoring HTML report...
    Email sent!

---

## Email Report Features 📊

Each automated report includes:

- **Article Summaries**: Concise 30-word summaries of each news piece
- **Sentiment Analysis**: Positive, negative, or neutral sentiment classification
- **Actionable Insights**: 3-5 key takeaways for brand reputation management
- **Direct Links**: Easy access to original articles for deeper review
- **Professional Formatting**: Clean, responsive HTML design ready for stakeholders

---

## Advanced Configuration 🧑‍💻

### Custom Search Parameters
Modify search queries for different monitoring scenarios:

    {
      "search_queries": [
        "\"YourBrand\" competitor analysis",
        "YourBrand customer complaints",
        "YourBrand industry leadership",
        "YourBrand product launch"
      ]
    }

### Scheduling Automation
Set up automated monitoring with cron jobs:

    # Run every Monday at 9 AM
    0 9 * * 1 /usr/bin/python3 /path/to/your/project/main.py

### Custom Analysis Prompts
Fine-tune the AI analysis by modifying the system prompts in the `process_news_list()` function for industry-specific insights.

---

## API Integration Details 🔧

This workflow leverages three powerful APIs:

- **[Bright Data Search Engine API](https://docs.brightdata.com/api-reference/web-scraper-api/search-engines/google)**: For discovering Google News URLs
- **[Bright Data Web Scraper API](https://docs.brightdata.com/api-reference/web-scraper-api)**: For parallel content extraction
- **OpenAI GPT**: For content analysis and report generation
- **SendGrid Email API**: For professional report delivery

---

## Troubleshooting & Tips 💡

- **API Keys**: Ensure all API keys are correctly set in your `.env` file
- **Email Verification**: Sender email must be verified in SendGrid dashboard
- **Rate Limits**: The workflow includes built-in handling for API rate limits
- **Search Queries**: Use specific brand terms and variations for comprehensive monitoring
- **Content Quality**: More specific queries yield better analysis results
- **Recipient Limits**: SendGrid free tier supports up to 100 emails per day

### Common Issues:

- **No news found**: Try broader search queries or check if your brand has recent coverage
- **Email not delivered**: Verify sender email in SendGrid and check recipient spam folders
- **Analysis quality**: Refine search queries to get more relevant articles

---

## Use Cases 🎯

- **Crisis Management**: Early detection of negative brand mentions
- **Competitive Intelligence**: Monitor competitor news and market positioning  
- **PR Campaign Tracking**: Measure coverage and sentiment of marketing initiatives
- **Product Launch Monitoring**: Track reception and feedback on new releases
- **Executive Briefings**: Regular brand health reports for leadership teams

---

**Stay ahead of your brand reputation! 🚀**
