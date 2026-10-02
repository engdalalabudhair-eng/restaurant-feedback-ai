# Restaurant Feedback AI

AI-powered restaurant customer feedback analysis automation built with **n8n, OpenAI, JavaScript, Google Forms, and Google Sheets**.

The system receives customer feedback through a form, validates and prepares the submitted data, uses an AI model to analyze the feedback, and stores both the original submission and the AI-generated analysis in Google Sheets.

---

## Overview

Restaurant feedback often contains useful information about customer satisfaction, service quality, food quality, and operational issues.

This project automates the process of collecting and analyzing customer feedback.

Instead of manually reviewing every submission, the workflow uses an AI model to classify and evaluate each feedback submission and produce structured results that can be stored and reviewed later.

---

## Problem

A restaurant may receive many customer feedback submissions containing:

- Customer information
- Ratings
- Written feedback
- Complaints
- Positive comments
- Suggestions

Manually reviewing and categorizing this information can become time-consuming.

This project provides an automated workflow that processes each submission and produces structured AI analysis.

---

## Solution

The automation follows this process:

```text
Google Form
     ↓
JavaScript Data Preparation & Validation
     ↓
Basic LLM Chain
     ↓
AI Feedback Analysis
     ↓
Structured Output
     ↓
Google Sheets

===========================================================================================================================
===========================================================================================================================

Workflow Architectur


Main workflow components

1. Google Form

The customer submits:

Customer Name
Email
Rate
Feedback

2. JavaScript

The JavaScript node prepares and validates the submitted data.

It:

Reads the submitted form fields
Validates required fields
Validates the customer rating
Ensures the rating is between 1 and 5
Cleans the feedback text
Calculates the feedback word count
Prepares structured input for the AI model

3. Basic LLM Chain

The AI model analyzes the customer feedback.

The analysis includes:

Sentiment
Category
Priority
AI Score
Issues
Recommended Action

4. Structured Output

The AI response is converted into a structured format so that individual analysis fields can be stored separately.

5. Google Sheets

The original customer information and AI-generated analysis are stored together in a Google Sheet.

---------------

AI Analysis

For each feedback submission, the AI generates the following fields:

Field	Description
Sentiment	Overall sentiment: Positive, Neutral, or Negative
Category	Main subject of the feedback
Priority	Low, Medium, or High
Score	AI evaluation score from 1 to 5
Issues	Main problems identified in the feedback
Recommended Action	Suggested action for the restaurant

The customer's original rating is also validated to ensure it is an integer between 1 and 5.

---------------

Input

The workflow receives the following information:

Customer Name
Email
Rate
FeedBack

The JavaScript processing step also generates:

Word Count

---------------

Output

The final Google Sheet contains both the original submission and the AI analysis.

Example structure:

Customer Name	    Email	            Rate    	FeedBack	   Word Count	  Sentiment 	Category	  Priority	Score	Issues	Recommended Action
Customer	    customer@email.com	   5     Very good	        2         Positive    Food Quality	 Low      5    No major issues reported
Maintain current quality

---------------

Screenshots

workflow
feedback
sheet

---------------

Technologies Used
1. n8n — Workflow automation
2. OpenAI — AI-powered feedback analysis
3. JavaScript — Data validation and preparation
4. Google Forms — Customer feedback collection
5. Google Sheets — Structured data storage

---------------

Project Structure:

restaurant-feedback-ai/
│
├── README.md
│
├── workflow/
│   └── restaurant-feedback-ai.json
│
└── screenshots/
    ├── workflow.png
    ├── feedback-form.png
    └── google-sheet.png

---------------

How It Works?

1.A customer submits the feedback form.
2. n8n receives the submission.
3. The JavaScript node validates and prepares the data.
4. The customer's rating is checked to ensure it is between 1 and 5.
5. The feedback data is sent to the AI model.
6. The AI analyzes the feedback.
7. The analysis is returned in a structured format.
8. The original data and AI analysis are stored in Google Sheets.

---------------

Data Validation

The workflow includes validation before AI processing.

The customer rating must:

Be an integer
Be greater than or equal to 1
Be less than or equal to 5

Feedback is optional. If no feedback is provided, the workflow can continue without treating the missing feedback as an error.

---------------

Security

No API keys, passwords, or private credentials are included in this repository.

Credentials should be configured separately inside n8n.

---------------

Future Improvements:

Possible future improvements include:

1.Automatic notification for high-priority feedback
2.Email notification to restaurant management
3.Dashboard for feedback analytics
4.Monthly sentiment reports
5.Automatic detection of recurring customer complaints
6.Feedback trend analysis over time
7.Integration with a restaurant CRM system

---------------

Project Purpose

This project was built as a practical example of combining AI, workflow automation, data validation, and structured data processing using n8n.

It demonstrates how unstructured customer feedback can be transformed into structured information that can support restaurant operations and customer experience analysis.

**********
