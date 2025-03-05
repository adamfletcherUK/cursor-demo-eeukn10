# Cursor Demo Prompt Workflows

This repository contains a collection of demonstration prompt workflows for using Cursor to build code effectively. These workflows showcase different approaches to software development using Cursor's AI capabilities.

## 🎯 Purpose

This repository serves as a practical demonstration of how to leverage Cursor's AI capabilities for various software development tasks. Each workflow is designed to showcase a specific aspect of the development process, from requirements gathering to implementation.

## 📚 Available Workflows

### 1. Product Requirements Document (PRD) Workflows
- **Create PRD Sections**: Generate structured sections for a Product Requirements Document
- **Implement PRD**: Convert PRD specifications into actionable code

### 2. User Story Workflows
- **Create User Stories**: Generate detailed user stories from high-level requirements
- **Implement User Story**: Convert user stories into working code

### 3. Application Specification Workflows
- **Create App Specification**: Generate detailed technical specifications for applications

## 🧠 How to Use

1. Navigate to the `documents/workflows` directory
2. Choose the workflow that matches your current development phase
3. Follow the prompts in the selected workflow file
4. Use Cursor's AI capabilities to assist with the implementation

## 📁 Repository Structure

```
.
├── documents/
│   ├── workflows/         # Prompt workflow templates
│   ├── pocs/             # Proof of concept implementations
│   └── canned_prompts/   # Reusable prompt templates
├── progress/             # Track progress and learnings
└── .cursor/             # Cursor-specific configurations
```

## ⚙️ Cursor Rules

This repository includes Cursor-specific rules in `.cursor/rules/CODING.mdc` that guide the AI's code generation and development approach. Key aspects include:

### Core Principles
- Speed over perfection - focusing on quick learning outcomes
- Readability over optimization
- Heavy debugging and logging for AI analysis
- Documentation as you go

### Development Standards
- **Code Structure**: Files under 100 lines, one concept per file
- **Debugging**: Consistent logging format for both Python and TypeScript
- **Documentation**: Comprehensive file and function documentation
- **Testing**: Console-based test cases with sample inputs/outputs
- **Error Handling**: Simple try/catch blocks with contextual logging

### Implementation Process
1. Document the concept
2. Write usage example
3. Implement minimal version
4. Add debug statements
5. Add basic tests
6. Document learnings

These rules ensure consistent, maintainable, and well-documented code while focusing on rapid learning and concept validation.

## 🎓 AI Teaching Guidelines

This repository also includes generic AI rules that define how Cursor should interact with developers, focusing on educational and collaborative aspects:

### Core Teaching Principles
- **Explain the "Why"**: Every code snippet and suggestion includes clear explanations of underlying principles and best practices (tagged with 🧠 LEARNING)
- **Explore Alternatives**: Present different approaches and discuss their trade-offs
- **Share Reasoning**: Break down the thought process and solution steps
- **Address Edge Cases**: Identify and discuss potential edge cases and mitigation strategies
- **Combined Commentary**: Integrate practical implementation with educational insights
- **Encourage Questions**: Explicitly invite follow-up questions and discussion

### Interactive Learning
- **Strategic Pop Quizzes**: Use targeted questions (tagged with 🎉 POP QUIZ) to reinforce key concepts
- **Interactive Feedback**: Provide detailed explanations for answers, helping developers understand both correct and incorrect approaches
- **Progressive Learning**: Build understanding through guided exploration and practical examples

These guidelines ensure that every interaction with Cursor is not just about writing code, but about building understanding and developing best practices.

## 🚀 Getting Started

1. Clone this repository
2. Open it in Cursor
3. Choose a workflow from the `documents/workflows` directory
4. Follow the prompts to start building your application

## 💡 Best Practices

- Start with a clear understanding of your requirements
- Use the workflows in sequence for best results
- Leverage Cursor's AI capabilities for code generation and review
- Document your learnings and improvements

## 🤝 Contributing

Feel free to:
- Add new workflows
- Improve existing workflows
- Share your experiences and learnings
- Report issues or suggest improvements

## 📝 License

This repository is open source and available under the MIT License.

---

Built with ❤️ using Cursor 