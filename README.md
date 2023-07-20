# chatbot-task

Your task is to create a simple **python function**. We designed it so it could be completed in less than 1-2 hours.

## Task
that would take in one text string and return another text string: 

```python
def answer_question(user_question: str) -> str:
   # Your solution here
```

This function represents a "backend" for a chatbot for retail investors.

To make it the task as easy as possible, user query will always come with certain guarantees:
- The question will always be about **one** single company.
   - The company is guaranteed to be mentioned in the query and exist in the dataset.
- The question will always be about a single specific full fiscal year (i.e. only `fiscal_period=FY`, no questions about quarters).
   - The year is guaranteed to be mentioned in the query and exist in the dataset.
- The topic of any user question guaranteed will be one of only these five (i.e. user will never ask about any other topic):
   - Total Revenue
   - Net Income / (Loss) Attributable to Common Shareholders
   - Price to Earnings (P/E)
   - Dividend Yield
   - Return on Equity (ROE).
 
## Example questions and answers

- **Question:** How much did walmart generate in sales in 2021?
   - **Answer:** In 2021, Walmart Inc generated $XXX billion in sales.
   - Note: Corresponding information is *Total Revenue*

- **Question:** What was the bottom line for walgreens common shareholders in 2022?
   - **Answer:** The bottom line for Walgreens Boots Alliance Inc's common shareholders in 2022 was $XXX million.
   - Note: Corresponding information is *Net Income / (Loss) Attributable to Common Shareholders*

- **Question:** How much was verizon stock worth compared to its earnings in 2021?
   - **Answer:** In 2021, for every dollar of earnings, Verizon Communications Inc's stock was worth XX.XX.
   - Note: Corresponding information is *Price to Earnings (P/E)*

- **Question:** What percentage of its share price did Visa return to its shareholders as dividends in 2022?
   - **Answer:** In 2022, Visa Inc returned X.XX% of its share price to its shareholders as dividends.
   - Note: Corresponding information is *Dividend Yield*

- **Question:** What was the efficiency of Apple in generating profits from its shareholders' equity in 2021?
   - **Answer:** In 2021, Apple Inc generated a return of XX.XX% on its shareholders' equity.
   - Note: Corresponding information is *Return on Equity (ROE)*
  
## Software design

- We recommend using the OpenAI ChatGPT API (be careful to not include your API key in the code).
- Your solution should be put in public (or private, if you like) Github repository.
- Do not modify the CSV files (and do not directly modify the data files, i.e. your program should always read the original files).
- You do not necessarily have to put all of your code inside the function, you can put some code outside of it as well.
   - In that case, consider using Python *Class* and *Method* instead of a *Function*.
- Feel free to develop in Jupyter notebooks, if you want.
   - It would be great if you included a Jupyter notebook to demonstrate any exploration you do.
