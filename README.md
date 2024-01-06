# Book-Recommendation-System

This is a Book Recommendation System based on Google Books.

The first part of the code fetches book data from the Google Books API and stores it in a CSV file. The fetch_books function takes a search query, API key, and the total number of desired results as parameters. It makes multiple requests to the Google Books API, retrieves book information, and writes it to the CSV file.

Text Processing and Feature Engineering - The next part of the code involves preprocessing the textual data from the fetched books. The preprocess_text function tokenizes, lowercases, removes stop words, and performs stemming on the text. The processed text is then used to create new features such as Processed_Authors, Processed_Categories, and Combined_Features (a combination of book description, authors, and categories).

TF-IDF Vectorization - The code uses the TF-IDF (Term Frequency-Inverse Document Frequency) vectorization technique to convert the textual data into numerical vectors. This is done using the TfidfVectorizer from scikit-learn.

Cosine Similarity Calculation - The cosine similarity between books is calculated based on their TF-IDF vectors. The result is stored in the cosine_sim matrix.

Recommendation Function - The recommend_books function takes a search query, preprocesses it, vectorizes it using TF-IDF, and calculates the cosine similarity with the precomputed matrix. It then returns the titles of the top 10 recommended books based on similarity.

Model Serialization (Saving and Loading) - The model, including the DataFrame, TF-IDF vectorizer, TF-IDF matrix, and cosine similarity matrix, is serialized using the pickle module. The model is saved to a file named 'book_recommendation_model.pkl'. Later, the model is loaded back using pickle for making recommendations.

Example Query - The last part of the code demonstrates how to use the loaded model for making recommendations. In this case, a search query ("java") is used, and the top recommended books are printed.

This code essentially sets up a book recommendation system using Google Books data, TF-IDF vectorization, and cosine similarity. The model is saved for future use and can be loaded to provide book recommendations based on user queries.
