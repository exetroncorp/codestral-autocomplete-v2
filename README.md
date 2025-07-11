# Codestral Autocomplete V2 - Enhanced

An enhanced VS Code autocomplete extension using Codestral with Continue-inspired completion logic for superior line navigation and positioning.

## Features

- **Smart Inline Completions**: Leverages Continue's proven completion logic for proper text replacement and positioning
- **Intelligent Triggering**: Context-aware completion triggering that avoids interrupting your workflow
- **Single-Line Processing**: Advanced single-line completion handling adapted from Continue's implementation
- **Multi-Language Support**: Works with 25+ programming languages
- **Caching**: Built-in LRU cache for faster completions
- **Configurable**: Extensive configuration options for debouncing, timeouts, and behavior
- **Status Bar Integration**: Visual feedback on completion status
- **Manual Mode**: Option to trigger completions only manually

## Key Improvements Over V1

1. **Fixed Line Navigation**: No more unwanted line jumps when typing comments or strings
2. **Continue-Inspired Logic**: Uses proven completion processing from the Continue extension
3. **Better Context Awareness**: Smarter detection of when to trigger completions
4. **Improved Performance**: Debouncing and caching for better responsiveness
5. **Enhanced Error Handling**: Better error reporting and recovery

## Installation

1. Install the extension from the VS Code marketplace
2. Get your Codestral API key from [Mistral AI](https://console.mistral.ai/)
3. Configure the API key in VS Code settings: `Codestral Autocomplete: Api Key`

## Configuration

### Basic Settings

- `codestral-autocomplete.apiKey`: Your Codestral API key
- `codestral-autocomplete.enabled`: Enable/disable autocomplete
- `codestral-autocomplete.manualMode`: Only trigger completions manually

### Advanced Settings

- `codestral-autocomplete.debounceDelay`: Delay before triggering completion (default: 300ms)
- `codestral-autocomplete.timeout`: Request timeout (default: 10000ms)
- `codestral-autocomplete.maxTokens`: Maximum tokens to generate (default: 64)
- `codestral-autocomplete.temperature`: Completion randomness (default: 0.1)
- `codestral-autocomplete.minTriggerChars`: Minimum characters to trigger (default: 2)
- `codestral-autocomplete.useCache`: Enable completion caching (default: true)

## Commands

- `Codestral: Toggle Autocomplete` (`Ctrl+K Ctrl+A`): Enable/disable autocomplete
- `Codestral: Force Completion` (`Ctrl+Alt+Space`): Manually trigger completion
- `Codestral: Clear Cache`: Clear the completion cache
- `Codestral: Show Logs`: Show debug logs

## How It Works

This extension uses the same proven completion logic as the Continue extension:

1. **Context Analysis**: Analyzes the code context around your cursor
2. **Smart Triggering**: Determines when completions should be shown
3. **API Request**: Sends context to Codestral API for completion generation
4. **Processing**: Uses Continue's single-line processing logic for proper positioning
5. **Display**: Shows the completion as inline suggestion

## Supported Languages

JavaScript, TypeScript, Python, Java, C#, C++, C, Go, Rust, PHP, Ruby, Swift, Kotlin, Scala, HTML, CSS, SCSS, Less, JSON, YAML, XML, Markdown, SQL, Shell, PowerShell, Dockerfile, Makefile

## Troubleshooting

### No Completions Appearing

1. Check that the extension is enabled (status bar should show ✓ Codestral)
2. Verify your API key is configured correctly
3. Check the logs: `Codestral: Show Logs`
4. Try manual completion: `Ctrl+Alt+Space`

### Completions Are Slow

1. Reduce `debounceDelay` for faster triggering
2. Increase `timeout` if requests are timing out
3. Enable caching if disabled

### Unwanted Completions

1. Increase `minTriggerChars` to require more typing
2. Enable `manualMode` to only trigger manually
3. Adjust `temperature` for more predictable completions

## Development

### Building

```bash
npm install
npm run compile
```

### Testing

```bash
npm test
```

### Packaging

```bash
npm run package
```

## Architecture

The extension is built with a modular architecture inspired by Continue:

- **CompletionProvider**: Main completion logic with Continue-style processing
- **CodestralClient**: API client for Codestral integration
- **ConfigManager**: Configuration handling and validation
- **StatusBar**: Visual status feedback
- **Cache**: LRU cache for performance
- **Logger**: Debug logging system

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Add tests for new functionality
5. Submit a pull request

## License

MIT License - see LICENSE file for details

## Acknowledgments

- **Continue Extension**: For the proven completion logic and architecture inspiration
- **Mistral AI**: For the Codestral API
- **VS Code Team**: For the excellent extension API
