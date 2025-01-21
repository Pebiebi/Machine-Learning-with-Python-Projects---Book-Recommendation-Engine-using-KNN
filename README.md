# Book Recommendation System using K-Nearest Neighbors

This project is a **Book Recommendation System** built using the **K-Nearest Neighbors (KNN)** algorithm. It utilizes the **Book-Crossings dataset**, containing 1.1 million ratings of 270,000 books by 90,000 users. The aim is to recommend books similar to a given book based on user ratings.

---

## Features

- **Data Cleaning:**
  - Remove users with less than 200 ratings.
  - Remove books with less than 100 ratings.
  - Handle missing data.
- **Model Preparation:**
  - Use a pivot table to create a user-item matrix.
  - Replace book ISBNs with their corresponding titles.
- **Book Recommendation:**
  - Implement a KNN-based model to recommend books.
  - Return the top 5 recommended books along with their similarity distances.
- **Error Handling:**
  - Handle cases where a book is not found in the dataset gracefully.

---

## Installation

1. Clone this repository:
   ```bash
   git clone https://github.com/your-username/book-recommendation-system.git
   ```
2. Navigate to the project directory:
   ```bash
   cd book-recommendation-system
   ```
3. Install the required Python packages:
   ```bash
   pip install -r requirements.txt
   ```

---

## Usage

1. Open the notebook in **Google Colab**:
   - Upload the notebook to your Google Drive.
   - Open it in Google Colab.
2. Follow the instructions in the notebook to clean the data, train the model, and test the recommendations.
3. Use the provided `get_recommends` function to get book recommendations:
   ```python
   get_recommends("The Queen of the Damned (Vampire Chronicles (Paperback))")
   ```
   Example Output:
   ```python
   [
     'The Queen of the Damned (Vampire Chronicles (Paperback))',
     [
       ['Catch 22', 0.793983519077301],
       ['The Witching Hour (Lives of the Mayfair Witches)', 0.7448656558990479],
       ['Interview with the Vampire', 0.7345068454742432],
       ['The Tale of the Body Thief (Vampire Chronicles (Paperback))', 0.5376338362693787],
       ['The Vampire Lestat (Vampire Chronicles, Book II)', 0.5178412199020386]
     ]
   ]
   ```
4. Create a copy of the notebook in your own Google Drive or download it locally for backup.

---

## Project Structure

```
.
├── data/                   # Dataset files (not included, see Note)
├── notebooks/              # Jupyter Notebook files
├── requirements.txt        # Python dependencies
└── README.md               # Project documentation (this file)
```

> **Note:** The dataset is not included in this repository. Please obtain the Book-Crossings dataset from the appropriate source.

---

## Testing

Use the provided `test_book_recommendation` function to validate the recommendation system:
```python
def test_book_recommendation():
    test_pass = True
    recommends = get_recommends("Where the Heart Is (Oprah's Book Club (Paperback))")
    if recommends[0] != "Where the Heart Is (Oprah's Book Club (Paperback))":
        test_pass = False
    recommended_books = ["I'll Be Seeing You", 'The Weight of Water', 'The Surgeon', 'I Know This Much Is True']
    recommended_books_dist = [0.8, 0.77, 0.77, 0.77]
    for i in range(2):
        if recommends[1][i][0] not in recommended_books:
            test_pass = False
        if abs(recommends[1][i][1] - recommended_books_dist[i]) >= 0.05:
            test_pass = False
    if test_pass:
        print("You passed the challenge! \U0001F389\U0001F389\U0001F389\U0001F389\U0001F389")
    else:
        print("You haven't passed yet. Keep trying!")
```
Run the test and ensure the output matches the expected format and recommendations.

---

## Contributing

Contributions are welcome! If you'd like to improve the code or documentation:
1. Fork the repository.
2. Create a feature branch:
   ```bash
   git checkout -b feature-name
   ```
3. Commit your changes:
   ```bash
   git commit -m "Add new feature"
   ```
4. Push to the branch:
   ```bash
   git push origin feature-name
   ```
5. Open a pull request.

---

## License

This project is licensed under the MIT License. See the LICENSE file for details.

---

## Acknowledgments

- **Book-Crossings Dataset:** Thank you to the creators of the dataset.
- **scikit-learn:** For providing the Nearest Neighbors implementation.
- **Instructor/Examiner:** For designing this project challenge.

---

## Contact

If you have any questions or issues, feel free to open an issue or reach out via GitHub!

