---
title: Playing with data
draft: false
tags:
  - notes
---
# prompt 1:
I have exported my text messages from my bank that has the all the transactions, the file is in json format but it has a lot of useless attributes like the bank's phone number I would like to remove, and at the end of the cleaning process, I would like to visualize that data with an graph, interactive graph. Mind you that data starts from 2022 so its a lot

To clean and visualize your bank transaction data from the JSON file, you can follow these steps:
### 1. **Load and Inspect the JSON Data**
   First, load the JSON file and inspect the structure to identify the unnecessary fields.

   ```python
   import json

   # Load the JSON data
   with open('transactions.json', 'r') as file:
       data = json.load(file)

   # Inspect the first transaction to understand the structure
   print(data[0])
   ```

### 2. **Filter Out Unnecessary Attributes**
   After identifying which fields are unnecessary (e.g., bank's phone number), you can remove them from the data.

   ```python
   # Define the fields you want to keep
   fields_to_keep = ['date', 'amount', 'transaction_type', 'description']

   # Filter the data
   cleaned_data = [
       {key: transaction[key] for key in fields_to_keep if key in transaction}
       for transaction in data
   ]

   # Save the cleaned data (optional)
   with open('cleaned_transactions.json', 'w') as file:
       json.dump(cleaned_data, file, indent=4)
   ```

### 3. **Convert to Pandas DataFrame**
   Convert the cleaned data into a `pandas` DataFrame for further manipulation and visualization.

   ```python
   import pandas as pd

   # Create a DataFrame
   df = pd.DataFrame(cleaned_data)

   # Convert 'date' to datetime for better analysis
   df['date'] = pd.to_datetime(df['date'])
   
   # Optionally inspect the DataFrame
   print(df.head())
   ```

### 4. **Visualize the Data**
   For interactive graphs, you can use `Plotly` or `Altair`. Let’s say you want to visualize the sum of transactions per month:

   #### Using `Plotly` for an Interactive Graph:
   ```python
   import plotly.express as px

   # Aggregate data (e.g., monthly sum of amounts)
   df['month'] = df['date'].dt.to_period('M')
   monthly_data = df.groupby('month')['amount'].sum().reset_index()

   # Create an interactive line graph
   fig = px.line(monthly_data, x='month', y='amount', title='Monthly Transaction Amounts')
   fig.show()
   ```

   #### Using `Altair` for Interactivity:
   ```python
   import altair as alt

   # Create an interactive line chart
   chart = alt.Chart(df).mark_line().encode(
       x='month:T',
       y='amount:Q',
       tooltip=['month', 'amount']
   ).interactive()

   chart.show()
   ```

### 5. **More Advanced Visualizations (Optional)**
   You can also create additional visualizations like:
   - **Pie charts** for transaction type distribution.
   - **Bar charts** to show monthly totals.
   - **Scatter plots** to compare transaction amounts over time.

### Next Steps
- Clean your JSON data using the method above.
- Once cleaned, visualize the data using an interactive library like Plotly.
- You can also export this visualization to HTML to share it or embed it in other platforms.

Let me know if you'd like any additional features or assistance with specific parts!
# 2
Now I want to show chatGPT the format of the JSON data and I firstly want to show one part of it and ask it how to open the file (have to choose one file) take whatever necessary and put it in a new file? or modify the current file? I think It will be easier if it can make a new file.

## JSON file format
"[]" represents arrays
"{}" represents JSON objects
and my file does have key-value pair like these ones
```
{
  "name": "Alice",
  "age": 30,
  "isStudent": false
}
```

### **Comparison of Usage**

- **`[]` for arrays**: Used when you need a list of items. Arrays are ordered collections, so the order of elements matters.
- **`{}` for objects**: Used to describe an entity or a complex structure where keys map to specific values. Objects are unordered collections of key-value pairs.

### I managed to do it successfully
Now I have the time and the body of the messages, I would like to convert the unix time code to a more human- readable date format.

Before I did the date, I counted the number of objects (aka how many messages I got)

#### Prompt
So currently I have a json file with lots of objects that have the "date" key-value pair but the value is the linux epoch time, how to loop through all the objects, read the "date" key-value pair and make a new key value pair and add the human readable date? Also I would like it to be in Hanoi time. Everything is done in python


