![demo](./assets/adv-hotel-finder.gif)

# SuiteDreams AI

A comprehensive AI-powered hotel search and discovery application built with Streamlit and integrated with Model Context Protocol (MCP) servers. SuiteDreams AI provides advanced filtering capabilities, detailed property information retrieval, and intelligent search recommendations.

**Author:** Bhavana Ediga

## Contact

- **Email:** [your email]
- **GitHub:** [your GitHub]

## Features

### Smart search capabilities

- **AI-powered queries**: Natural language hotel search with intelligent query processing
- **Multiple search modes**: Quick search, advanced filtering, and detailed hotel information
- **Location intelligence**: Support for cities, states, regions, and specific areas
- **Date-based filtering**: Check-in and check-out date support with validation
- **Guest configuration**: Flexible guest settings (adults, children, infants, pets)

### Advanced filtering

- **Price range control**: Set minimum and maximum price constraints per night
- **Room type preferences**: Filter by single, double, suite, family rooms, etc.
- **Star rating filters**: Minimum star rating requirements (3+, 4+, 5-star only)
- **Amenity selection**: Multi-select amenities (WiFi, Pool, Gym, Spa, etc.)
- **Custom preferences**: Tailored search based on specific requirements

### Comprehensive results

- **Detailed hotel information**: Complete property details, amenities, and policies
- **Price comparisons**: Clear pricing with per-night rates and total costs
- **Booking integration**: Direct links to hotel booking platforms
- **Location context**: Nearby attractions, transportation, and neighborhood info
- **Guest reviews**: Ratings, reviews, and guest feedback integration

### User experience

- **Multi-tab interface**: Organized search modes for different use cases
- **Real-time validation**: Input validation with helpful error messages
- **Progress tracking**: Visual progress indicators during search execution
- **Result management**: Save, export, and manage search results
- **Responsive design**: Optimized for desktop and mobile viewing

## Installation

### Prerequisites

- Python 3.11 or higher
- Nebius API key (for AI model access)
- Node.js / `npx` (for the Airbnb MCP server used at runtime)

### Setup

1. **Clone or copy this project** into a folder of your choice (for example `suitedreams-ai`):

   ```bash
   git clone [your repository URL]
   cd suitedreams-ai
   ```

2. **Install dependencies**:

   ```bash
   uv sync
   ```

3. **Environment variables** (optional):

   ```bash
   cp .env.example .env
   # Edit .env with your API keys
   ```

4. **Run SuiteDreams AI**:

   ```bash
   streamlit run app.py
   ```

   ![demo](./assets/hotel-finder.gif)

## Configuration

### API keys

- **Nebius API Key**: Required for AI model access and query processing (sidebar or `.env`).

### Advanced settings (in the app)

- **Request timeout**: Configure maximum wait time for searches (10–60 seconds)
- **Max results**: Set maximum number of hotels per search (5–50 results)
- **Robots.txt compliance**: Option to bypass robots.txt restrictions (via MCP args)
- **AI model selection**: Choose from available Nebius models
- **Response creativity**: Adjust AI response temperature (0.0–1.0)

## Usage

### Quick search

1. Open the **Quick Search** tab
2. Enter your destination location
3. Select a search type (Find Hotels, Best Deals, Luxury Hotels, etc.)
4. Adjust the generated query if needed
5. Click **Search with SuiteDreams AI**

### Advanced search

1. Open the **Advanced Search** tab
2. Fill in destination and dates, guest counts, room preference, star rating, and amenities
3. Review the generated query
4. Execute the search

### Listing details

Use the flows described in the app UI for listing-specific lookups when available.

## Architecture (overview)

- **Streamlit frontend**: Interactive web interface with multi-tab layout
- **MCP integration**: Model Context Protocol for hotel/listing data access
- **AI agent**: Nebius-powered natural language processing (SuiteDreams AI)
- **Async processing**: Non-blocking search execution

### Data flow

1. User enters search criteria in Streamlit
2. Parameters are validated and formatted
3. MCP client starts the configured server (e.g. via `npx`)
4. The SuiteDreams AI agent runs tools and returns formatted results
5. Results can be exported as JSON

## Export

- **JSON export**: Download search results with metadata from the UI when results are shown (files prefixed `suitedreams_ai_results_`).

## Development

### Project structure

```
suitedreams-ai/
├── app.py                 # Main Streamlit application (SuiteDreams AI)
├── pyproject.toml         # Project configuration and dependencies
├── README.md              # This documentation
├── LICENSE                # MIT License
├── .env.example           # Environment variables template
└── assets/                # Static assets (logos, images)
```

### Code style

- Python 3.11+ with type hints where applicable
- Formatting: Black / isort (see `pyproject.toml`)

## Troubleshooting

**Authentication errors**

- Confirm API keys and quotas for Nebius

**Connection issues**

- Check network access
- Ensure Node/`npx` is available for the MCP server

**Search errors**

- Simplify queries; validate dates (YYYY-MM-DD) and location spelling

**Performance**

- Lower max results or increase timeout in the sidebar

## License

This project is licensed under the MIT License — see the [LICENSE](LICENSE) file.

## Support

- **Issues:** [your GitHub issues URL]
- **Documentation:** This repository
