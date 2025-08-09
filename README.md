# deep_research
# Deep Research Agent Pipeline

A modular multi-agent system for automated research workflows: planners structure a topic, searchers fetch sources, writers generate reports, optional email sending, and a manager orchestrates the process.

## Features
- Topic-driven automated research
- Task planning, concurrent retrieval, deduplication, and evidence tracking
- Structured Markdown report generation with links and citations
- Pluggable agents and search backends for easy customization

## File Structure
deep_research.py       # Main script / CLI entrypoint
research_manager.py    # Orchestrates agents and data flow
planner_agent.py       # Decomposes topic into sub-research tasks
search_agent.py        # Fetches and filters search results
writer_agent.py        # Generates structured report in Markdown
email_agent.py         # (optional) Sends report via email

## Requirements
- Python 3.10+
- uv tool for virtualenv and dependency management
- Environment variables (in .env):
  - OPENAI_API_KEY (required)
  - Optional search API keys (e.g. SERPER_API_KEY, BING_SEARCH_KEY)

## Quick Start
git clone https://github.com/JIARUIWANG79/deep_research.git  
cd deep_research  
uv init  
uv add openai python-dotenv  
uv sync  
uv run python deep_research.py  

## Workflow Overview
1. Planner: Splits the main topic into focused search tasks.
2. Search Agent: Retrieves and filters sources concurrently.
3. Manager: Aggregates and deduplicates evidence.
4. Writer: Produces the final Markdown report.
5. Email Agent (optional): Sends the report to your email.

