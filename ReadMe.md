# Fashion Recommendation System using RAG Pipeline
---
> A Generative Search System which can understand a user's query and recommend the most suitable fashion items based on their preferences from a vast collection of product data.
---

## Table of Contents
* [Objectives](#objectives)
* [Dataset](#dataset)
* [System Design](#system-design)
* [Implementationt](#implementation)
* [Models Used](#models-used)
* [Example Results](#example-results)
* [Key Points](#key-points)
* [Future Scope](#future-scope)
* [Conclusion](#conclusion)

## Objectives
The main objective of this project is to develop a fashion query response system that utilizes AI models to provide detailed and user-friendly responses to fashion-related queries. The system aims to enhance user experience by generating informative and contextually relevant answers, thereby assisting users in finding fashion items based on their preferences.

## Dataset
The dataset used for this project is [Myntra Fashion Product Dataset (kaggle.com)](https://www.kaggle.com/datasets/djagatiya/myntra-fashion-product-dataset). It includes thousands of fashion products, each with detailed information such as description, price, rating, brand name, and other attributes.
The dataset is organized in 'dataset/' folder as follows:
* _Fashion Dataset v2.csv_: This CSV file contains each product in a row, with various details spread across columns.
* _Image Folder_: This folder contains two zip folders. Extract all the images and place into this image folder. Then, this folder contains sample images for each product. Each image file is named according to the corresponding product's 'p_id' value from the CSV.

## System Design
![OverallSystemDiagram](https://github.com/user-attachments/assets/f7840271-8ed3-4abe-b4f1-25dd73efdba3)

## Implementation
The implementation involved several steps, including data preprocessing, model integration, and query response generation.

### Data Preprocessing:
- The CSV dataset was formatted to enhance data quality and readability.
- Blank entries were replaced, decimal points were standardized, and unnecessary columns were removed.
- Text columns were cleaned to remove HTML tags and extra characters.

### Model Integration:
- Advanced AI models like GPT-3.5 were integrated into the system to generate responses to user queries.
- Queries were passed through the model to generate detailed and contextually relevant responses.

### Query Response Generation:
- User queries were processed by both the search layer and the generation layer.
- The search layer retrieved relevant fashion items from the dataset.
- The generation layer utilized AI models to generate detailed responses to user queries, incorporating context and generating natural language responses.

## Models Used
| Topic | Model |
|:------|:------|
| Embedding | text-embedding-ada-002 |
| Cross Encoder for reranking | cross-encoder/ms-marco-MiniLM-L-6-v2 |
| Generative Response | gpt-3.5-turbo |

## Example Results
From Semantic search with reranking layer,
![Query1_SerachLayer (1)](https://github.com/user-attachments/assets/fa8c67b8-a5eb-4cf6-984d-5b22be1b4e7d)


From Generative search final layer,
![Query1_GenerationLayer (1)](https://github.com/user-attachments/assets/864cd076-694e-492d-89b5-e43aa901abba)

## Key Points
- Explored various models to implement embedding.
- Explored various ways to prepare the document for query.
- Explored different prompts to generate appropriate response for the user query.
- Implemented cache technique for faster response.
- Hands-on experience with Chroma DB.
- Explored various datasets to experiment with RAG apart from this fashion dataset.

## Future Scope
- Implementing the project as a streamlit application for end user.
- Rephrasing prompts and introducing interactive sessions with criteria-based filters.

## Conclusion
Upon comparison of the search query outcomes from both the search and generation layers, it becomes apparent that the generation layer produces more detailed and comprehensible results. While the search layer efficiently retrieves relevant information, the generation layer significantly enhances output quality and readability, making it a preferred choice for tasks requiring detailed and user-friendly responses.
