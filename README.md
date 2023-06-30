# Plagiarism-checker
import difflib

# Function to calculate similarity ratio between two texts
def calculate_similarity(text1, text2):
    text1_lines = text1.splitlines()
    text2_lines = text2.splitlines()

    matcher = difflib.SequenceMatcher(None, text1_lines, text2_lines)
    similarity_ratio = matcher.ratio()

    return similarity_ratio

# Read the contents of two text files
def read_text_file(file_path):
    with open(file_path, 'r') as file:
        text = file.read()
    return text

# Take file paths as input from the user
file1_path = input("Enter the path of the first text file: ")
file2_path = input("Enter the path of the second text file: ")

# Read the contents of the text files
file1_text = read_text_file(file1_path)
file2_text = read_text_file(file2_path)

# Calculate the similarity ratio
similarity_ratio = calculate_similarity(file1_text, file2_text)

# Display the similarity ratio
print("Similarity Ratio:", similarity_ratio)
