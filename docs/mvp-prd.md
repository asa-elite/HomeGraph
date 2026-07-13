# HomeGraph MVP Product Requirements Document

## 1. Product Summary

HomeGraph turns household documents into a connected knowledge graph that helps users understand their possessions, coverage, recurring payments, and upcoming deadlines.

## 2. Problem Statement

Household information is scattered across receipts, warranties, insurance policies, and recurring bills. Users cannot easily determine how these documents relate or find the evidence needed to answer important household questions.

## 3. Target User

A person responsible for organizing household purchases, insurance coverage, subscriptions, and important expiration dates.

## 4. MVP User Story

As a household organizer, I want to upload household documents and ask questions about the information connecting them so that I can understand coverage, payments, and deadlines without manually searching every document.

## 5. Product Promise

Upload household documents, ask a question, and see an evidence-backed answer with the graph connections used to produce it.

## 6. Supported Documents

The MVP supports text-based versions of:

- Purchase receipt
- Product warranty
- Insurance summary
- Recurring bill or subscription statement

The MVP does not support scanned documents or images requiring OCR.

## 7. Golden Questions

### Question 1

Which warranties expire in the next 90 days?

Expected result:
- Relevant products
- Warranty expiration dates
- Supporting documents
- Highlighted graph paths

### Question 2

Is the sample laptop covered, and what documents would I need to file a claim?

Expected result:
- Applicable warranty or policy
- Coverage information found in the documents
- Required supporting documents
- Missing information clearly identified

### Question 3

Which recurring payments use the household’s primary credit card?

Expected result:
- Matching subscriptions or bills
- Providers
- Payment frequency
- Supporting statement evidence

### Question 4

What household deadlines require attention this month?

Expected result:
- Upcoming renewals and expirations
- Related product, policy, or subscription
- Supporting evidence
- Results ordered by date

## 8. Core User Flow

1. User opens HomeGraph.
2. User loads the fictional sample household.
3. User uploads a supported document.
4. GPT-5.6 extracts proposed entities, relationships, dates, and evidence.
5. The application validates and saves the information to Neo4j.
6. User selects or enters a question.
7. HomeGraph retrieves the relevant graph path.
8. GPT-5.6 produces a grounded answer.
9. The interface displays the answer, evidence, and graph path.

## 9. Functional Requirements

- Accept supported text-based documents.
- Extract document text.
- Use GPT-5.6 Sol to propose structured facts.
- Validate model output before persistence.
- Store connected facts in Neo4j.
- Associate important facts with source evidence.
- Answer all four golden questions.
- Display the relevant graph path.
- Provide a repeatable sample-data reset.

## 10. Nonfunctional Requirements

- A judge can use the application without developer assistance.
- The complete demo can be performed in under 2 minutes and 30 seconds.
- No real personal or financial information is used.
- Reprocessing a document does not duplicate graph data.
- Unsupported claims are identified as unknown.
- The application is accessible through a public HTTPS URL.

## 11. Out of Scope

- OCR and image processing
- Email or Google Drive integration
- Real bank-account connections
- Authentication and multiple households
- Notifications
- Mobile application
- Automatic insurance claims
- Unrestricted AI-generated Cypher
- Production-grade fuzzy entity resolution

## 12. Demo Scenes

1. Explain the household-information problem.
2. Load the fictional household.
3. Upload a document.
4. Show extracted entities, relationships, and evidence.
5. Ask a golden question.
6. Show the answer, highlighted graph path, and source evidence.
7. Briefly explain how Codex and GPT-5.6 were used.

## 13. Definition of Done

The MVP is complete when a judge can:

- Load the sample household.
- Process at least three supported document types.
- Ask all four golden questions successfully.
- Inspect the evidence behind important claims.
- View the graph path supporting an answer.
- Reset and repeat the demonstration.
- Run the project using the README instructions.