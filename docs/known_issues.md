# Known Issues

## OCR Issues

1. **Mixed Script Recognition**
   - When questions contain both Latin and Cyrillic text, OCR accuracy decreases
   - Tesseract performs better with Cyrillic text
   - EasyOCR handles mixed scripts better but may still have issues

2. **Special Characters**
   - Question marks and other special characters may be misrecognized
   - Example: "?" may be recognized as "2"
   - Requires post-processing to fix

## Video Processing Issues

1. **Answer Visibility**
   - In some Slagalica episodes, the answer is not shown before cutting to the next game
   - Example: Episode from 14.11.2018
   - Results in incomplete question-answer pairs

2. **Text Positioning**
   - Rarely, question text may appear above the question rectangle
   - Example: Episode from 18.06.2020
   - Current algorithm may miss these questions

3. **Frame Transitions**
   - Fast transitions between frames may cause missed questions
   - Particularly problematic in high-motion segments
   - May require lower processing fps to catch all questions

## Content Availability

1. **Video Quality**
   - Some episodes may have poor video quality
   - Low resolution or compression artifacts affect OCR
   - May require additional preprocessing
