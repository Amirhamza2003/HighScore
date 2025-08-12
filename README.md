# Math Question Generator

A Python application that generates math assessment questions using the Groq AI API. This tool helps educators create high-quality math questions based on provided base questions and curriculum paths.

## Features

- **AI-Powered Question Generation**: Uses Groq's Llama3-8b-8192 model to generate contextual math questions
- **Multiple Difficulty Levels**: Support for Easy, Moderate, Hard, and Mix difficulty settings
- **Curriculum-Based Generation**: Generate questions for specific subjects, units, and topics
- **Multiple Choice Format**: Creates questions with 5 options (A-E) and detailed explanations
- **Word Document Export**: Automatically saves generated questions to a Word document
- **Batch Processing**: Generate questions for multiple curriculum paths in one session

## Prerequisites

- Python 3.7 or higher
- Groq API key (get one from [Groq Console](https://console.groq.com/))

## Installation

1. **Clone or download the project files**

2. **Install required dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

   Or install manually:
   ```bash
   pip install groq python-docx requests
   ```

## Usage

1. **Run the application**:
   ```bash
   streamlit run high_score_generator.py
   ```

2. **Follow the interactive prompts**:

   a. **Enter your Groq API key** when prompted
   
   b. **Select difficulty level**:
      - 1) Easy
      - 2) Moderate
      - 3) Hard
      - 4) Mix (random difficulty for each question)
   
   c. **Enter two base questions** that will serve as templates for generating similar questions
   
   d. **Enter curriculum paths** in the format:
      ```
      Subject | Unit | Topic; Subject | Unit | Topic; ...
      ```
      
      Example:
      ```
      Quantitative Math | Problem Solving | Numbers and Operations; Quantitative Math | Algebra | Quadratic Equations & Functions
      ```

3. **Wait for generation**: The application will generate 2 questions per curriculum path

4. **Check output**: A Word document will be created with all generated questions

## Example Usage

```
=== MATH QUESTION GENERATOR ===

Please enter your Groq API key:
gsk_your_api_key_here
✓ API key validated successfully!

Select difficulty level:
1) Easy
2) Moderate
3) Hard
4) Mix (random difficulty for each question)
Enter your choice (1-4): 2

Selected difficulty: MODERATE

Enter Base Question 1:
What is the value of x in the equation 2x + 5 = 13?

Enter Base Question 2:
Solve for y: 3y - 7 = 8

Enter curriculum paths (one or many) as: Subject | Unit | Topic; Subject | Unit | Topic; ...
Example: Quantitative Math | Problem Solving | Numbers and Operations; Quantitative Math | Algebra | Quadratic Equations & Functions
Quantitative Math | Algebra | Linear Equations; Quantitative Math | Problem Solving | Word Problems
```

## Output Format

The generated questions follow this structure:

```
title: Assessment title for [Topic]
description: assessment description for [Topic]
question: Write your question here
instruction: Write instruction here
difficulty: [easy/moderate/hard]
order: Question number
option A: ...
option B: ...
option C: ...
option D: ...
option E: ...
correct_answer: A/B/C/D/E
explanation: Write your question explanation here
subject: [Subject]
unit: [Unit]
topic: [Topic]
plusmarks: 1
```

## File Structure

```
Folder/
├── math_question_generator.py    
├── requirements.txt              
├── README.md                     
└── math_assessment_questions_*.docx  
```

## Configuration

### Model Settings
- **Model**: Llama3-8b-8192
- **Temperature**: 0.7 (balanced creativity and consistency)
- **Max Tokens**: 2000 (sufficient for detailed questions)

## Error Handling

The application includes error handling for:
- Invalid API keys
- Network connectivity issues
- Invalid curriculum path formats
- Missing required inputs

## Output Files

Generated questions are saved to Word documents with timestamps:
- Format: `math_assessment_questions_[timestamp].docx`
- Contains all generated questions organized by curriculum path
- Includes headers and formatting for easy reading

## Troubleshooting

### Common Issues

1. **API Key Error**: Ensure your Groq API key is valid and has sufficient credits
2. **Import Errors**: Make sure all dependencies are installed correctly
3. **Network Issues**: Check your internet connection for API calls
4. **Invalid Curriculum Paths**: Follow the exact format: `Subject | Unit | Topic`

### Getting Help

If you encounter issues:
1. Check that all dependencies are installed
2. Verify your Groq API key is valid
3. Ensure you have an active internet connection
4. Check the curriculum path format

## Security Notes

- API keys are not stored or logged
- No sensitive information is saved to files
- All API calls are made securely over HTTPS

## License

This project is open source and available under the MIT License.

## Contributing

Feel free to submit issues, feature requests, or pull requests to improve the application.

---

**Note**: This application requires a valid Groq API key to function. Make sure you have sufficient API credits for your intended usage.
