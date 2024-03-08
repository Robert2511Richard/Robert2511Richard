import csv
from collections import Counter

def read_sales_data(file_path):
    with open(file_path, newline='') as csvfile:
        reader = csv.DictReader(csvfile)
        sales_data = [row for row in reader]
    return sales_data

def extract_keywords(sales_data):
    all_descriptions = [description.lower() for product in sales_data for description in product['description'].split()]
    return Counter(all_descriptions)

def main():
    file_path = 'sales_data.csv'
    sales_data = read_sales_data(file_path)
    keywords = extract_keywords(sales_data)

    print("Melhores palavras-chave para anúncios:")
    for keyword, freq in keywords.most_common(5):
        print(f"{keyword}: {freq}")

if _name_ == '_main_':
    main()- 👋 Hi, I’m @Robert2511Richard
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...

<!---
Robert2511Richard/Robert2511Richard is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
