# Contributing to Cliniko Reports

First off, thank you for considering contributing to Cliniko Reports! It's people like you that make this project a great tool for the healthcare community.

## Code of Conduct

This project and everyone participating in it is governed by our Code of Conduct. By participating, you are expected to uphold this code.

## How Can I Contribute?

### Reporting Bugs

Before creating bug reports, please check the existing issues as you might find out that you don't need to create one. When you are creating a bug report, please include as many details as possible:

- **Use a clear and descriptive title**
- **Describe the exact steps to reproduce the problem**
- **Provide specific examples to demonstrate the steps**
- **Describe the behavior you observed and what behavior you expected**
- **Include screenshots if applicable**
- **Include your environment details** (Power BI version, Windows version, etc.)

### Suggesting Enhancements

Enhancement suggestions are tracked as GitHub issues. When creating an enhancement suggestion, please include:

- **Use a clear and descriptive title**
- **Provide a step-by-step description of the suggested enhancement**
- **Provide specific examples to demonstrate the steps**
- **Describe the current behavior and explain the behavior you expected**
- **Explain why this enhancement would be useful**

### Contributing Code

#### Development Environment Setup

1. **Fork the repository**

   ```bash
   git clone https://github.com/yourusername/cliniko-reports.git
   cd cliniko-reports
   ```

2. **Install Power BI Desktop**
   - Download from [Microsoft Power BI](https://powerbi.microsoft.com/desktop/)
   - Ensure you have the latest version

3. **Set up test environment**
   - Create a test Cliniko account if needed
   - Generate test API keys (never use production keys in development)

#### Making Changes

1. **Create a branch**

   ```bash
   git checkout -b feature/your-feature-name
   ```

2. **Make your changes**
   - Follow the coding standards outlined below
   - Test your changes thoroughly
   - Update documentation as needed

3. **Commit your changes**

   ```bash
   git add .
   git commit -m "Add descriptive commit message"
   ```

4. **Push to your fork**

   ```bash
   git push origin feature/your-feature-name
   ```

5. **Create a Pull Request**
   - Use a clear title and description
   - Reference any related issues
   - Include screenshots of any visual changes

## Coding Standards

### Power BI / DAX Standards 

- You should use human-readable names rather than any kind of technical naming convention, with spaces where you would expect to have spaces and all vowels present. For example, that means having names like [Sales Amount] rather than [Sales_Amount] or [SlsAmt]; similarly, prefixes like “Dim” and “Fact” might make sense to you but won’t mean anything to your users.

- You should use the correct business terminology, the terminology that your users will know and understand, rather than just make up some names that seem appropriate. Your users might not understand what [Total Sales Value] is if the generally accepted term is [Net Sales Amount].

- The names you use should be consistent across all datasets that contain the same data. That means that if you have a table called Sales in one dataset it should be called Sales in every other dataset that you build from the same data source, not Transactions, FactSales or something else.
### File Organization

- **Semantic Model**: Keep related tables and measures organized
- **Report Pages**: Use descriptive names for report pages
- **Visuals**: Ensure consistent styling across all visuals
- **Data Sources**: Document any changes to data source connections

### Documentation

- **README Updates**: Update README.md for any new features or changes
- **Code Comments**: Add comments for complex logic
- **Measure Descriptions**: Include descriptions for custom measures
- **Change Log**: Document significant changes

## Testing Guidelines

### Before Submitting

1. **Test with Sample Data**
   - Ensure all measures calculate correctly
   - Verify all visuals display properly
   - Test filter interactions

2. **Performance Testing**
   - Check query performance with realistic data volumes
   - Ensure refresh times are reasonable
   - Test with different data sizes

3. **Cross-Platform Testing**
   - Test on different screen resolutions
   - Verify mobile responsiveness if applicable
   - Check in both Power BI Desktop and Service

### Test Data

- **Never use production data** in development or testing
- Use anonymized or sample data when possible
- Document any test data requirements

## Pull Request Guidelines

### Before Submitting a Pull Request

- [ ] Code follows the established coding standards
- [ ] All tests pass and new functionality is tested
- [ ] Documentation is updated (README, comments, etc.)
- [ ] Commit messages are clear and descriptive
- [ ] No sensitive information (API keys, passwords) is included

### Pull Request Description

Please include:

1. **Summary of Changes**
   - What does this PR do?
   - Why is this change needed?

2. **Testing**
   - How was this tested?
   - Are there any edge cases to consider?

3. **Screenshots**
   - Include before/after screenshots for visual changes
   - Show any new reports or dashboards

4. **Breaking Changes**
   - Are there any breaking changes?
   - How should users migrate?

## Security Considerations

### API Keys and Sensitive Data

- **Never commit API keys** or other sensitive information
- Use parameter files or environment variables for configuration
- Include `.gitignore` entries for sensitive files
- Document how to securely configure credentials

### Data Privacy

- Follow healthcare data protection regulations (HIPAA, GDPR, etc.)
- Ensure no patient data is included in code or documentation
- Use sample or anonymized data for examples

## Community Guidelines

### Communication

- **Be respectful** and inclusive in all interactions
- **Be patient** with new contributors
- **Be constructive** in feedback and criticism
- **Use clear language** and avoid jargon when possible

### Getting Help

- **Check existing issues** before asking questions
- **Use descriptive titles** for issues and discussions
- **Provide context** when asking for help
- **Be specific** about what you're trying to achieve

## Recognition

Contributors will be recognized in the following ways:

- Listed in the project's README
- Mentioned in release notes for significant contributions
- Added to the project's contributors section

## License

By contributing to Cliniko Reports, you agree that your contributions will be licensed under the same license as the project (MIT License).

## Questions?

If you have any questions about contributing, please:

1. Check the [GitHub Discussions](https://github.com/yourusername/cliniko-reports/discussions)
2. Create an issue with the `question` label
3. Reach out to the maintainers

Thank you for contributing to Cliniko Reports! 🎉
