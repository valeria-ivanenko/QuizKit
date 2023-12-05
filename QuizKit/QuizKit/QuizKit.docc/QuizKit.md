# QuizKit Framework

## Overview
QuizKit is a versatile Swift framework designed for effortlessly creating and managing quizzes in your iOS applications. It offers a customizable and easy-to-use interface to enhance the user experience in educational or trivia-based apps.

## Features
- **Customizable Quiz Layout**: Configure the appearance of your quizzes, including background, font, text alignment, and more.
- **Dynamic Question Handling**: Easily add and display questions with multiple choice answers.
- **Answer Validation**: Automatically checks user's answers and keeps track of the score.
- **Progress Tracking**: Displays a progress bar to indicate the user's progress through the quiz.
- **Result Display**: Shows the user's score at the end of the quiz with an option to reset and start over.
- **Animation Enhancements**: Smooth transitions between questions for an engaging user experience.

## Installation
### Swift Package Manager
To integrate QuizKit into your Xcode project using Swift Package Manager, add it as a dependency in your `Package.swift` file:

```swift
dependencies: [
    .package(url: "https://github.com/valeria-ivanenko/QuizKit.git", .upToNextMajor(from: "1.0.0"))
]
```

## Usage
To effectively use QuizKit in your iOS projects, follow these steps:

### Importing QuizKit
First, import QuizKit at the top of your Swift file:

```swift
import QuizKit
```
### Creating Questions
Define your quiz questions:

```swift
let questions = [
    Question(questionLabel: "What is the capital of France?",
            options: ["Paris", "London", "Berlin"],
            correctOptionIndex: 0),
    // More questions here...
]
```
### Configuring the Quiz
Set up the appearance and behavior of your quiz:

```swift
let quizConfig = QuizConfig(
    background: .lightGray,
    font: .systemFont(ofSize: 18),
    textAlignment: .left,
    // Additional configurations...
)
```

### Initializing the Quiz
Create an instance of Quiz with your questions and configuration:

```swift
let quiz = Quiz(questions: questions, config: quizConfig)
````

### Displaying the Quiz
In your ViewController, add the QuizView:

```swift
override func viewDidLoad() {
    super.viewDidLoad()
    let quizView = QuizView(quiz: quiz, frame: self.view.bounds)
    self.view.addSubview(quizView)
}
```

## Examples

Here's a simple implementation of QuizKit in a ViewController:

```swift
import UIKit
import QuizKit

class MyQuizViewController: UIViewController {
    override func viewDidLoad() {
        super.viewDidLoad()

        let questions = [
            Question(questionLabel: "What is 2+2?", options: ["3", "4", "5"], correctOptionIndex: 1),
            Question(questionLabel: "What is 5+3?", options: ["6", "7", "8"], correctOptionIndex: 2)
        ]

        let quizConfig = QuizConfig(background: .white, font: .systemFont(ofSize: 18))
        let quiz = Quiz(questions: questions, config: quizConfig)

        let quizView = QuizView(quiz: quiz, frame: self.view.bounds)
        self.view.addSubview(quizView)
    }
}
```
