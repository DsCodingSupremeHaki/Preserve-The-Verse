# 📚 Poem Data Organizer

This Python script processes a string of poem data, extracting and organizing information about various highlighted poems. It demonstrates fundamental string and list manipulation techniques in Python to transform raw text into structured data.

---

## How It Works

The script starts with a single string containing information about several poems (title, poet, and publication year), separated by specific delimiters. It then performs the following operations:

* **Splits** the initial string into a list of individual poem entries.
* **Strips** any leading or trailing whitespace from each poem entry.
* Further **splits** each poem entry into a sublist containing its title, poet, and date.
* Creates **separate lists** for all titles, all poets, and all publication dates.
* **Formats and prints** each poem's details in a human-readable sentence.

---

## Getting Started

### Prerequisites

You'll need **Python 3** installed on your computer to run this script.

### Installation

No special installation is required. Just save the code to a `.py` file.

1.  **Save the code:** Copy the entire code block provided and save it as `poem_organizer.py` (or any other name ending with `.py`) on your computer.

---

## Usage

1.  **Open your terminal or command prompt.**
2.  **Navigate to the directory** where you saved `poem_organizer.py`.
    ```bash
    cd path/to/your/project
    ```
3.  **Run the script** using Python:
    ```bash
    python poem_organizer.py
    ```
4.  The script will print various outputs to your console, showing the progression of data cleaning and organization, ultimately displaying a formatted sentence for each poem.

---

## Code

Here's the full code for the Poem Data Organizer:

```python
highlighted_poems = "Afterimages:Audre Lorde:1997,  The Shadow:William Carlos Williams:1915, Ecstasy:Gabriela Mistral:1925,   Georgia Dusk:Jean Toomer:1923,   Parting Before Daybreak:An Qi:2014, The Untold Want:Walt Whitman:1871, Mr. Grumpledump's Song:Shel Silverstein:2004, Angel Sound Mexico City:Carmen Boullosa:2013, In Love:Kamala Suraiyya:1965, Dream Variations:Langston Hughes:1994, Dreamwood:Adrienne Rich:1987"

print("Original String:")
print(highlighted_poems)

# Split the string into a list of individual poem entries
highlighted_poems_list = highlighted_poems.split(",")
print("\nAfter splitting by comma:")
print(highlighted_poems_list)

# Clean up whitespace from each poem entry
highlighted_poems_stripped = []
for poem in highlighted_poems_list:
    highlighted_poems_stripped.append(poem.strip())
print("\nAfter stripping whitespace:")
print(highlighted_poems_stripped)

# Break up the information for each poem into its own list (list of lists)
highlighted_poems_details = []
for string in highlighted_poems_stripped:
    highlighted_poems_details.append(string.split(":"))
print("\nAfter splitting details (list of lists):")
print(highlighted_poems_details)

# Create three new lists for titles, poets, and dates
titles = []
poets = []
dates = []

# Iterate through the highlighted_poems_details list and populate the new lists
for item in highlighted_poems_details:
    titles.append(item[0])
    poets.append(item[1])
    dates.append(item[2])

print("\nFormatted Poem Details:")
# Loop to format and print the highlighted poem details
for i in range(0, len(highlighted_poems_details)):
    print("The poem {} was published by {} in {}.".format(titles[i], poets[i], dates[i]))
```

---

## Learning Context & Credits

This project was developed as part of the **"Learn Python 3"** (or a similar string/list manipulation focused) curriculum on [Codecademy](https://www.codecademy.com/). It served as a practical exercise to reinforce understanding of **Python string and list methods**, including:

* Using `split()` for parsing data
* Applying `strip()` for data cleaning
* Appending to lists and iterating through them
* Accessing list elements by index
* String formatting with `.format()`

---

## Future Enhancements (Ideas for Improvement)

This project provides a solid foundation for data parsing. Here are some ideas for how you could expand upon it:

* **User Input:** Allow users to provide their own string of poem data.
* **Functions:** Organize the code into functions (e.g., `parse_poems(data_string)`) for better modularity and readability.
* **Error Handling:** Add checks for malformed input strings to ensure robust parsing.
* **Data Structures:** Consider using a list of dictionaries (e.g., `{"title": "Afterimages", "poet": "Audre Lorde", "year": "1997"}`) for a more organized and accessible data structure.
* **Filtering/Searching:** Add functionality to search for poems by title, poet, or year.

---
