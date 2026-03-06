# EarthSathi
AI Hackathon


Prompt :

Build an AI-powered Portfolio Manager agent for banks that helps retail customers analyze their investment portfolios and receive ESG-based green investment recommendations.

The system should be serverless and built using AWS services.

Goal:
Create an AI agent that analyzes a customer's portfolio, evaluates ESG scores of existing investments, compares them with bank-approved green stocks, and recommends a more sustainable and profitable portfolio.

Problem:
Most banks provide personalized investment advisory services mainly to high net worth individuals, leaving retail investors with limited guidance. Retail investors often lack tools to understand ESG scores, sustainability risks, or portfolio optimization opportunities.

This solution should improve retail customer engagement and promote sustainable investing.

Technology Stack:
- Core development environment: AWS Kiro IDE
- AI model: Amazon Bedrock (Claude model via MCP)
- Agent deployment: Bedrock AgentCore
- Portfolio storage: DynamoDB
- External ESG data: mock ESG API similar to Yahoo Finance
- Tool execution: AWS Lambda
- API exposure: API Gateway
- Architecture: fully serverless

System Architecture:
User Dashboard → API Gateway → Lambda → Kiro Agent → Bedrock Model → Data Tools (Portfolio DB + ESG APIs)

Agent Role:
Portfolio Manager AI

Responsibilities:
1. Analyze a customer's investment portfolio
2. Retrieve ESG scores for all portfolio assets
3. Evaluate credit risk and sustainability exposure
4. Identify low ESG score holdings
5. Search for bank-approved green energy stocks
6. Recommend portfolio rebalancing
7. Estimate potential profit and risk
8. Generate a 2-year projection of portfolio growth

Agent Tools (implemented via Lambda):
1. get_customer_portfolio(customer_id)
   - Fetch portfolio data from DynamoDB

2. get_esg_score(stock_symbol)
   - Retrieve ESG score from mock API

3. get_green_energy_stocks()
   - Return a list of bank-approved green investment assets

4. calculate_portfolio_health_score(portfolio)
   - Compute a portfolio health score based on ESG score, diversification, and risk

5. simulate_portfolio_growth(portfolio)
   - Estimate portfolio growth for 2 years based on expected returns

Agent Workflow:
1. Customer clicks the "Portfolio Manager" button on the dashboard
2. System refreshes and retrieves the user's portfolio
3. Agent analyzes portfolio composition
4. Agent retrieves ESG scores for each asset
5. Agent calculates portfolio risk and sustainability exposure
6. Agent compares holdings with high ESG green energy stocks
7. Agent suggests optimized portfolio changes
8. Agent simulates expected portfolio value after 2 years
9. Agent generates insights and recommendations

Output Requirements:
The output must be visualized on a dashboard.

Dashboard Components:

1. Portfolio Health Score
- Display a score out of 100
- Factors: ESG ratings, diversification, risk

2. Asset Allocation Chart
- Pie chart showing distribution of:
  - Tech stocks
  - Energy
  - Green energy
  - Other assets

3. ESG Exposure Chart
- Bar graph showing ESG scores of each holding

4. Portfolio Projection Graph
- Line chart showing expected growth for the next 2 years

5. Insights Panel
Generate AI insights such as:
- High carbon exposure detected
- Low ESG score asset identified
- Suggested green stock replacements
- Risk and profit expectations

Example Insight:
"Your portfolio contains a low ESG-rated oil company. Replacing 20% of this holding with NextEra Energy could improve your portfolio ESG score by 18% while maintaining similar expected returns."

UI Requirements:
Create a simple dashboard with:
- "Portfolio Manager" button
- Portfolio health score widget
- Asset allocation pie chart
- ESG score visualization
- 2-year growth projection graph
- AI insights panel

Deployment:
Package the agent using Bedrock AgentCore and deploy it as a scalable serverless runtime.

Ensure that the system is modular so additional financial tools or ESG datasets can be integrated later.





UI Prompt :
Generate a responsive web dashboard UI for a financial assistant platform.

The dashboard should include a chatbot named "SAAR".

Design Requirements:
Use modern UI design with a clean financial dashboard theme.
Use HTML, CSS, and JavaScript (or React if preferred).
The UI should be responsive and simple for demo purposes.

Dashboard Layout:

Create a landing dashboard page that displays the services offered by the platform.

Title:
"ArthSaathi"

Sections on the first page should include four service cards:

1. Portfolio Manager
Description:
Analyze a user's investment portfolio and provide a portfolio health score, asset allocation insights, and risk analysis.

2. Financial Insights
Description:
Provide insights about spending patterns, investments, and financial health.

3. Chatbot
Description:
An AI-powered chatbot assistant that answers financial queries and helps users analyze their portfolio.

4. About Us
We are building an AI-powered financial copilot designed to make intelligent portfolio management accessible to everyday investors. While professional wealth management has traditionally been limited to high-net-worth individuals, millions of retail investors are left to navigate complex financial decisions on their own.

Our platform bridges this gap by combining AI-driven portfolio analysis, personalized financial insights, and risk assessment to help users make smarter investment decisions. By simplifying financial data and delivering actionable insights, we empower individuals to understand, manage, and grow their investments with confidence.

Our mission is simple — To democratize portfolio management and make intelligent financial guidance accessible to everyone.

Each service should appear as a card with:
- icon
- title
- short description
- hover animation

Chatbot Requirements:

Create a floating chatbot button in the bottom-right corner of the screen.

Chatbot Button:
- circular button
- fixed position bottom-right
- label "SAAR"
- chatbot icon

When the user clicks the button:
- a chatbot popup window should open.

Chatbot Popup UI:

Header:
Chatbot name: "SAAR"
Subtitle: "ArthSaathi"

Include:
- close button
- minimize button

Chat Window:

When the chatbot opens for the first time, display 4 sample FAQ questions.

Example FAQ Suggestions:
1. "Analyze my portfolio"
2. "What is a portfolio health score?"
3. "Show me my financial insights"
4. "How can I improve my investments?"

The FAQ questions should appear as clickable suggestion buttons.

If the user clicks one of the suggestions:
- the text should automatically populate into the chat input.

Chat Interface:

Include:
- message display area
- user message bubble
- bot response bubble
- input text field
- send button

Behavior:

When the user types a message and clicks send:
- display the message in the chat window
- simulate chatbot typing animation
- show a placeholder response.

Example response:
"Thanks for your question. I'm analyzing your request and will provide insights shortly."

Additional UI Features:

- smooth open/close animation for chatbot popup
- scrollable chat history
- responsive layout for desktop and mobile
- clean financial dashboard colors (light background with blue accents)

File Structure to Generate:

/ui
   index.html
   styles.css
   chatbot.js
   dashboard.js

Ensure the chatbot component can later be connected to backend APIs or AI models.
