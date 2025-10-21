Basic Chatbot – Informational Bot

Objective:
Create a simple chatbot that provides information about an AWS service (e.g., Amazon S3).
Steps:
Log into AWS Management Console


Go to Amazon Lex → Create bot


Name: S3InfoBot


Language: English (ZA)


Choose None for advanced configuration → Create


Create One Intent


Intent name: S3Info


Example utterance:


“What is S3?”


Response:


“Amazon S3 is a cloud storage service that lets you store and retrieve any amount of data from anywhere.”


Build & Test


Click Build


In the test window, type “What is S3?”


Confirm the bot replies correctly.


A functional chatbot that answers one question has been created.





PART 2: Quiz Chatbot for CloudLearners Inc.
Scenario:
You’re a developer for CloudLearners Inc., tasked with creating an educational quiz chatbot that tests learners on Amazon S3.
Objective:
Build a Lex chatbot that:
Starts a quiz.
Asks multiple-choice questions.
Provides feedback for correct/incorrect answers.
Lets users continue or end the quiz.



Step-by-Step Setup
Step 1: Create the Bot
Name: CloudQuizBot


Language: English (ZA)


Basic settings: Default / None advanced config


Step 2: Create Intent: S3Quiz
Utterances:
“Start quiz”


“Quiz me on S3”


“I’m ready for the quiz”


Response:
Let's begin your S3 quiz!
Question 1: What does S3 stand for?
A) Simple Storage Service
B) Secure Server Storage
C) Smart Storage System
Please type A, B, or C.

Add Branching Logic (using Conditional Responses)
If user says A →
 Response: “Correct! S3 stands for Simple Storage Service. Would you like the next question?”


If user says B or C →
 Response: “Incorrect. The correct answer is Simple Storage Service. Would you like the next question?”


Add Follow-up Question
Question 2: What is Amazon S3 mainly used for?
A) Cloud storage
B) Web hosting
C) Cloud computing
Please type A, B, or C.

Conditional responses:
A → “Correct! S3 is mainly used for Cloud Storage.”


B/C → “Incorrect. The correct answer is Cloud Storage.”

Quiz Logic Flow (Simplified)

User: Start quiz
Bot: Question 1 → checks answer
Bot: Gives feedback → asks to continue
User: Yes → next question
Bot: Question 2 → checks answer
Bot: Gives feedback → ends or restarts quiz

Recap: Learning AWS Lex, chatbot development, and quiz interaction.

