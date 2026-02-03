# Q&A Dataset Generator

A web-based tool for generating high-quality question and answer datasets to train Large Language Models (LLMs). This application uses any OpenAI API-compatible LLM to generate diverse Q&A pairs on any topic.

## Features

- **OpenAI API Compatible**: Works with any API that follows the OpenAI chat completion format
- **Batch Generation**: Generate Q&A pairs in configurable batches with progress tracking
- **Customizable**: Configure topic, number of pairs, batch size, and model
- **Dataset Management**: Import, export, edit, and delete Q&A pairs
- **Combine Datasets**: Merge multiple dataset files into one
- **Statistics**: View pair count and average question/answer lengths
- **No Installation Required**: Pure HTML/JavaScript - just open in a browser

## Getting Started

### Prerequisites

- A modern web browser (Chrome, Firefox, Safari, Edge)
- An API key for an OpenAI-compatible LLM service (OpenAI, Azure OpenAI, local LLM with OpenAI-compatible API, etc.)

### Usage

1. Open `index.html` in your web browser

2. **Configure API Settings**:
   - Enter your API endpoint (default: OpenAI)
   - Enter your API key
   - Specify the model name (e.g., `gpt-3.5-turbo`, `gpt-4`)

3. **Configure Dataset**:
   - Enter a topic for your Q&A pairs
   - Set the number of pairs to generate (minimum 100 recommended)
   - Set batch size (number of pairs generated per API call, 1-20)

4. **Generate Dataset**:
   - Click "Generate Dataset" to start
   - Watch the progress bar as pairs are generated
   - Click "Stop Generation" to halt early if needed

5. **Manage Your Dataset**:
   - **Edit**: Modify individual questions or answers
   - **Delete**: Remove unwanted pairs
   - **Export**: Download your dataset as JSON
   - **Import**: Load a previously saved dataset
   - **Clear**: Remove all pairs and start fresh

6. **Combine Datasets**:
   - Use the "Combine Datasets" section to merge multiple JSON files
   - Select multiple files and they'll be combined into one download

## Dataset Format

The application exports datasets in JSON format:

```json
[
  {
    "question": "What is machine learning?",
    "answer": "Machine learning is a subset of artificial intelligence..."
  },
  {
    "question": "What are neural networks?",
    "answer": "Neural networks are computing systems inspired by..."
  }
]
```

## API Compatibility

This tool works with any API that implements the OpenAI chat completion format:

- **OpenAI**: `https://api.openai.com/v1/chat/completions`
- **Azure OpenAI**: `https://YOUR_RESOURCE.openai.azure.com/openai/deployments/YOUR_DEPLOYMENT/chat/completions?api-version=2024-02-15-preview`
- **Local LLMs**: Any local model with OpenAI-compatible API (e.g., LM Studio, LocalAI, Ollama with openai-compatible endpoint)
- **Other Providers**: Anthropic Claude (via proxy), Mistral AI, etc.

## Tips for Best Results

1. **Topic Specificity**: Be specific about your topic for better-focused Q&A pairs
   - Good: "Python list comprehensions and their use cases"
   - Less good: "Programming"

2. **Batch Size**:
   - Smaller batches (1-5): More API calls but more diverse pairs
   - Larger batches (10-20): Fewer API calls but potentially less diverse

3. **Model Selection**:
   - GPT-3.5-turbo: Fast and cost-effective
   - GPT-4: Higher quality but more expensive
   - Local models: Free but may need more prompt tuning

4. **Dataset Size**:
   - Minimum 100 pairs recommended for meaningful training
   - 1000+ pairs for robust fine-tuning
   - 10,000+ pairs for production-grade models

5. **Review and Edit**: Always review generated pairs for quality and accuracy

## Privacy and Security

- All API calls are made directly from your browser to the API endpoint
- No data is sent to any third-party servers (except your configured LLM API)
- API keys are stored only in memory during your session
- Datasets are saved locally on your device

## Troubleshooting

**Error: "Please enter an API key"**
- Make sure you've entered your API key in the configuration section

**Error: "API Error: 401"**
- Your API key is invalid or expired
- Check that you're using the correct API endpoint for your key

**Error: "Failed to parse Q&A pairs"**
- The LLM didn't return valid JSON
- Try a different model or reduce batch size
- Some models may need additional prompt tuning

**Pairs aren't generating**
- Check browser console for errors (F12)
- Verify your API endpoint is correct and accessible
- Ensure you have sufficient API credits/quota

## License

This project is open source and available for educational and commercial use.

## Contributing

Feel free to submit issues, feature requests, or pull requests to improve this tool.
