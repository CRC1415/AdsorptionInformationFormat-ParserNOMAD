# Contribute to the Documentation

Help us improve the documentation for the AIF parser plugin! This guide explains how to contribute to the documentation.

## How to Contribute

### Reporting Documentation Issues

If you find documentation errors or areas that need improvement:

1. Check if the issue already exists in our [GitHub issues tracker](https://github.com/CRC1415/AdsorptionInformationFormat-ParserNOMAD/issues)
2. Create a new issue describing the problem
3. Include suggestions for improvement

### Submitting Documentation Changes

To submit documentation updates:

1. Fork the repository
2. Create a branch for your changes
3. Modify the documentation files in the `docs/` directory
4. Preview your changes locally
5. Submit a pull request with a clear description

## Documentation Structure

The documentation is organized into four main sections:

### 1. Tutorial
Guides users through basic usage and workflows.

### 2. How-to Guides
Step-by-step instructions for specific tasks.

### 3. Explanation
Background information and conceptual explanations.

### 4. Reference
Technical specifications and API documentation.

## Writing Guidelines

### Style and Tone

- Use clear, concise language
- Write for both beginners and experienced users
- Use active voice
- Include practical examples where appropriate
- Maintain consistent terminology

### Markdown Format

All documentation is written in Markdown format. Follow these conventions:

- Use H1 for main section titles
- Use H2 for subsections
- Use bullet points for lists
- Use code blocks for command examples
- Use tables for structured data

### Technical Accuracy

Ensure all technical information is accurate:
- Test command examples before submitting
- Verify all links work
- Check that all code samples are valid
- Confirm that all references are current

## Previewing Changes Locally

To preview documentation changes locally:

```bash
# Install documentation dependencies
uv pip install -r requirements_docs.txt

# Serve the documentation locally
mkdocs serve
```

Then open your browser to `http://localhost:8000` to view the documentation.

## Documentation Updates

### Adding New Pages

To add a new page to the documentation:

1. Create a new Markdown file in the appropriate directory (`docs/tutorial/`, `docs/how_to/`, etc.)
2. Add a link to the new page in the main index file
3. Ensure the content follows the established style

### Updating Existing Pages

When updating existing documentation:

1. Keep the original structure and purpose
2. Focus on improving clarity and accuracy
3. Add new information without removing existing content
4. Test any code examples or commands

## Contact

For questions about documentation contributions, please contact:

- Ron Dockhorn <ron.dockhorn@tu-dresden.de>

## Resources

- [MkDocs Documentation](https://www.mkdocs.org/)
- [Markdown Syntax Guide](https://www.markdownguide.org/)
- [NOMAD Documentation Standards](https://nomad-lab.eu/prod/v1/staging/docs/)
