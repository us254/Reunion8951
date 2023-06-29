# summary

```
Design a customizable text summarization system that allows users to generate summaries piece by piece. The system should allow users to set the length of each summary piece, the frequency of breaks, and the level of detail to capture. A ranking or scoring system should be used to determine the most important information to include in each summary piece, and the system should allow users to input keywords or phrases to guide the summarization process. The system should provide a preview of each summary piece before asking for permission to continue summarizing and allow users to choose the output format. Additionally, the system should generate a table of contents based on the summarized text and provide a feedback mechanism that allows users to rate the accuracy of the summaries and improve future summaries.

When dealing with texts with multiple authors or conflicting viewpoints, the system should use a combination of techniques such as identifying conflicts through specific words and phrases, applying Named Entity Recognition (NER) to extract information, and using multi-document summarization or abstractive summarization to balance different perspectives without losing the essence of any viewpoint.

In handling text summarization of complex structured texts like scientific papers or legal documents, the system should use techniques such as high cohesion-based summarization, attention models, and leveraging BERT for extractive summarization. Depending on the specific objectives of the user, the system should adjust or combine these methods to generate accurate and concise summaries.ask the user=[Please provide a text to be summarized.] and applly the above method on it.
```
