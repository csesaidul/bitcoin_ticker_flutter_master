# Contributing to Bitcoin Ticker Flutter

Thank you for your interest in contributing to the Bitcoin Ticker Flutter project! We welcome contributions from developers of all skill levels.

## 🤝 How to Contribute

### Types of Contributions

We welcome several types of contributions:

- **Bug Reports**: Help us identify and fix issues
- **Feature Requests**: Suggest new features or improvements
- **Code Contributions**: Submit bug fixes or new features
- **Documentation**: Improve our documentation
- **Testing**: Help us test the application on different devices
- **Translations**: Help us support more languages

## 🚀 Getting Started

### Prerequisites

Before contributing, ensure you have:

- Flutter SDK 3.8.1 or higher
- Dart SDK 3.2.0 or higher
- Git installed on your system
- A code editor (VS Code, Android Studio, or IntelliJ)
- CoinAPI key for testing

### Development Setup

1. **Fork the Repository**
   ```bash
   # Fork the repo on GitHub, then clone your fork
   git clone https://github.com/YOUR_USERNAME/bitcoin-ticker-flutter.git
   cd bitcoin-ticker-flutter
   ```

2. **Set Up Development Environment**
   ```bash
   # Install dependencies
   flutter pub get
   
   # Verify Flutter installation
   flutter doctor
   ```

3. **Create Environment File**
   ```bash
   # Create .env file with your API key
   echo "API_KEY=your_coinapi_key_here" > .env
   ```

4. **Run the Application**
   ```bash
   # Run on your preferred device/emulator
   flutter run
   ```

5. **Run Tests**
   ```bash
   # Run all tests
   flutter test
   
   # Run tests with coverage
   flutter test --coverage
   ```

## 📋 Development Workflow

### Creating a Contribution

1. **Create a New Branch**
   ```bash
   # Create and switch to a new branch
   git checkout -b feature/your-feature-name
   # or
   git checkout -b fix/issue-number
   ```

2. **Make Your Changes**
   - Follow our coding standards (see below)
   - Write tests for new features
   - Update documentation if needed
   - Ensure all tests pass

3. **Commit Your Changes**
   ```bash
   # Add your changes
   git add .
   
   # Commit with a descriptive message
   git commit -m "feat: add price alert notifications"
   ```

4. **Push to Your Fork**
   ```bash
   git push origin feature/your-feature-name
   ```

5. **Create a Pull Request**
   - Go to the original repository on GitHub
   - Click "New Pull Request"
   - Provide a clear title and description
   - Reference any related issues

## 🎯 Coding Standards

### Code Style

- **Dart Style**: Follow the official [Dart Style Guide](https://dart.dev/guides/language/effective-dart/style)
- **Flutter Best Practices**: Adhere to [Flutter's best practices](https://flutter.dev/docs/development/ui/widgets/intro)
- **Linting**: Use `flutter analyze` to ensure code quality

### Code Formatting

```bash
# Format all Dart files
dart format lib/ test/

# Check for formatting issues
dart format --set-exit-if-changed lib/ test/
```

### Naming Conventions

- **Files**: Use `snake_case` for file names
- **Classes**: Use `PascalCase` for class names
- **Variables**: Use `camelCase` for variables and functions
- **Constants**: Use `SCREAMING_SNAKE_CASE` for constants

### Example Code Style

```dart
// Good
class CryptoCurrencyCard extends StatelessWidget {
  const CryptoCurrencyCard({
    super.key,
    required this.cryptoCurrency,
    required this.selectedCurrency,
    required this.price,
  });

  final String cryptoCurrency;
  final String selectedCurrency;
  final String? price;

  @override
  Widget build(BuildContext context) {
    return Card(
      elevation: 5.0,
      child: Padding(
        padding: const EdgeInsets.all(16.0),
        child: Text(
          '1 $cryptoCurrency = $price $selectedCurrency',
          style: Theme.of(context).textTheme.headlineSmall,
        ),
      ),
    );
  }
}
```

## 🧪 Testing Guidelines

### Writing Tests

- **Unit Tests**: Test individual functions and classes
- **Widget Tests**: Test UI components
- **Integration Tests**: Test complete user flows

### Test Structure

```dart
// Example widget test
void main() {
  group('CryptoCurrencyCard', () {
    testWidgets('displays correct cryptocurrency information', (tester) async {
      // Arrange
      const testCrypto = 'BTC';
      const testCurrency = 'USD';
      const testPrice = '50000';

      // Act
      await tester.pumpWidget(
        MaterialApp(
          home: CryptoCurrencyCard(
            cryptoCurrency: testCrypto,
            selectedCurrency: testCurrency,
            price: testPrice,
          ),
        ),
      );

      // Assert
      expect(find.text('1 BTC = 50000 USD'), findsOneWidget);
    });
  });
}
```

### Running Tests

```bash
# Run all tests
flutter test

# Run specific test file
flutter test test/widget/crypto_card_test.dart

# Run tests with coverage
flutter test --coverage
```

## 📝 Commit Message Guidelines

We follow [Conventional Commits](https://www.conventionalcommits.org/) for commit messages:

### Format

```
type(scope): description

[optional body]

[optional footer]
```

### Types

- `feat`: A new feature
- `fix`: A bug fix
- `docs`: Documentation changes
- `style`: Code style changes (formatting, etc.)
- `refactor`: Code refactoring
- `test`: Adding or updating tests
- `chore`: Maintenance tasks

### Examples

```bash
# Good commit messages
feat: add price alert notifications
fix: resolve currency conversion bug
docs: update API setup instructions
test: add unit tests for CoinData service
refactor: improve error handling in price fetching
```

## 🐛 Bug Reports

When reporting bugs, please include:

### Bug Report Template

```markdown
## Bug Description
A clear description of the bug.

## Steps to Reproduce
1. Go to '...'
2. Click on '...'
3. See error

## Expected Behavior
What you expected to happen.

## Actual Behavior
What actually happened.

## Environment
- Device: [e.g., iPhone 12, Pixel 5]
- OS: [e.g., iOS 14.5, Android 11]
- App Version: [e.g., 1.0.0]
- Flutter Version: [e.g., 3.8.1]

## Screenshots
If applicable, add screenshots.

## Additional Context
Any other relevant information.
```

## ✨ Feature Requests

When requesting features, please include:

### Feature Request Template

```markdown
## Feature Description
A clear description of the feature.

## Problem Statement
What problem does this feature solve?

## Proposed Solution
How would you like this feature to work?

## Alternative Solutions
Other ways to solve this problem.

## Additional Context
Any other relevant information.
```

## 📚 Documentation

### Documentation Standards

- Use clear, concise language
- Include code examples where appropriate
- Keep documentation up-to-date with code changes
- Use proper Markdown formatting

### Documentation Types

- **API Documentation**: Document all public methods and classes
- **User Documentation**: Instructions for end users
- **Developer Documentation**: Technical implementation details

## 🔍 Code Review Process

### For Contributors

1. **Self-Review**: Review your own code before submitting
2. **Tests**: Ensure all tests pass
3. **Documentation**: Update relevant documentation
4. **Description**: Provide clear PR description

### For Reviewers

1. **Code Quality**: Check for code style and best practices
2. **Functionality**: Verify the feature works as expected
3. **Tests**: Ensure adequate test coverage
4. **Documentation**: Check for updated documentation

## 📋 Pull Request Template

```markdown
## Description
Brief description of changes.

## Type of Change
- [ ] Bug fix
- [ ] New feature
- [ ] Breaking change
- [ ] Documentation update

## Testing
- [ ] Unit tests added/updated
- [ ] Widget tests added/updated
- [ ] Integration tests added/updated
- [ ] Manual testing completed

## Checklist
- [ ] Code follows project style guidelines
- [ ] Self-review completed
- [ ] Tests pass locally
- [ ] Documentation updated
- [ ] No breaking changes (or marked as breaking)

## Screenshots
If applicable, add screenshots of the changes.

## Related Issues
Closes #[issue number]
```

## 🎉 Recognition

We appreciate all contributions! Contributors will be:

- Listed in our contributors section
- Mentioned in release notes for significant contributions
- Invited to join our contributor community

## 🤔 Questions?

If you have questions about contributing:

- **Email**: support@dreamershorizon.com
- **Website**: [dreamershorizon.com](https://dreamershorizon.com)
- **GitHub Issues**: For technical questions
- **GitHub Discussions**: For general discussions

## 📄 License

By contributing to this project, you agree that your contributions will be licensed under the MIT License.

---

Thank you for contributing to Bitcoin Ticker Flutter! 🚀

*Last updated: July 4, 2025*
