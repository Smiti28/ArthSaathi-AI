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
