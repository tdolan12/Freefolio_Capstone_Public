# 2024 UC Berkeley Master in Information and Data Science Fall Capstone
# FreeFolio

FreeFolio is a free, AI-powered platform using an agentic framework to dynamically generate real-time statistics and visualizations, letting users "Talk to their data." Developed as a capstone project by Thomas Dolan, Elad Oz, Glenn Desouza, and Maximillian Jacob.

## Demo

[![FreeFolio Demo](https://www.ischool.berkeley.edu/sites/default/files/styles/fullscreen/public/2024-12/freefolio_screenshot_1.png?itok=fzqFgSTa)](https://www.youtube.com/watch?v=awNxFPPbwP4)
                                       ^^Click to Play^^

## Code Access

This repository is private. If you have any questions or would like to discuss the project, please message me directly.

## Overview

FreeFolio simplifies investment portfolio creation for novice and DIY investors. By leveraging natural language inputs, it provides personalized guidance aligned with users' values and financial goals, democratizing access to investment opportunities. The platform integrates structured data from sources like the YFinance API and unstructured data from SEC filings, processed through advanced AI techniques, to deliver tailored portfolio recommendations and insights.

## Problem & Motivation

Investing can be overwhelming for novice investors who lack financial expertise or access to affordable advice. Current solutions, such as human advisors or robo-advisors, are costly and often fail to provide personalized guidance aligned with users' values and goals. This leaves many retail investors without accessible, tailored investment tools.

FreeFolio addresses this gap by offering a free, AI-powered platform that simplifies portfolio creation through natural language inputs. By removing cost barriers and providing personalized, user-friendly tools, FreeFolio empowers novice and DIY investors to make informed financial decisions, democratizing access to investment opportunities.

## Features & Functionality

- **Natural Language Portfolio Management**: Users can create, modify, and analyze investment portfolios through conversational AI.
- **Real-Time Statistics & Visualizations**: FreeFolio dynamically generates investment insights using an agentic framework.
- **Integration of Structured & Unstructured Data**: Uses APIs and SEC filings to provide a comprehensive analysis.
- **Personalized Investment Guidance**: AI-driven recommendations tailored to user-defined financial goals and ethical considerations.
- **Retrieval-Augmented Generation (RAG) AI**: Processes financial documents and integrates insights into decision-making.
- **Automated Portfolio Rebalancing**: Users can update allocations and optimize holdings through AI recommendations.

## Data Sources & Architecture

FreeFolio integrates structured and unstructured financial data using a sophisticated ReAct-agent system to deliver personalized portfolio recommendations and investment insights.

### **Data Sources**

1. **Structured Data**:
   - **YFinance API**: Provides market capitalization, sector performance, and key financial ratios.
   - **User Portfolio Data**: Dynamically maintained, enabling real-time modifications and insights.

2. **Unstructured Data**:
   - **SEC Filings (10-K, 10-Q Reports)**: Processed into semantic embeddings using Amazon SageMaker and stored in a VectorDB for retrieval.

### **Pipeline Architecture**

#### **Unstructured Data Pipeline** (RAG Agent)
- **Data Collection**: Scrapes financial filings from the EDGAR database.
- **Preprocessing**: Documents are chunked for efficient indexing.
- **Embedding Creation**: SageMaker generates embeddings for semantic search, stored in a VectorDB.
- **Integration**: The RAG agent queries this pipeline for relevant textual information.

#### **Structured Data Pipeline** (SQL Agent)
- **Data Collection**: Uses the YFinance API.
- **Data Storage**: Saved as flat files on EC2, stored in an SQL database.
- **Integration**: SQL agent retrieves structured metrics for portfolio analysis.

### **Inference Pipeline**

- **SQL Agent**: Retrieves structured data insights.
- **RAG Agent**: Fetches relevant information from unstructured financial documents.
- **YFinance Plotting Tools**: Generates stock performance charts and investment insights.
- **Portfolio Update Tools**: Enables real-time rebalancing and customization.
- **Agentic Orchestration**: Coordinates these components to provide seamless user interactions.

## Evaluation

FreeFolio employs a robust evaluation framework ensuring accuracy, relevance, and user satisfaction.

### **Evaluation Criteria**
- **Tool Selection Accuracy**: Ensuring the right tools are chosen for user queries.
- **Query Construction**: Validating structured SQL queries and RAG agent retrieval quality.
- **Text Output Quality**: Evaluating clarity, relevance, and factual accuracy of responses.
- **Visualization Precision**: Assessing the correctness of generated statistical plots and charts.

### **Challenges & Mitigation**
- **State Dependence**: Managing dynamic portfolio updates within conversational history.
- **Multi-Modal Output Handling**: Ensuring seamless text and visual data integration.
- **Scalability Considerations**: Optimizing AI response times for real-time interactivity.

## Future Improvements

- **Expanded Data Sources**: Incorporate alternative financial datasets for deeper insights.
- **Advanced Predictive Analytics**: Use AI to forecast stock performance and trends.
- **Customizable Ethical Investing Filters**: Allow users to refine portfolios based on ESG (Environmental, Social, and Governance) factors.
- **Mobile & Web Application Deployment**: Enhance accessibility across different platforms.

## Contributors

- **Thomas Dolan**  
- **Elad Oz**  
- **Glenn Desouza**  
- **Maximillian Jacob**  

## License

This project is licensed under the MIT License. See [LICENSE](LICENSE) for details.

## Acknowledgments

This project was developed as part of the UC Berkeley Master in Information and Data Science Fall Capstone program.


