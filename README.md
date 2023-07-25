# chatbot-task

Your assignment is to create a simple Python function. We've designed this task to be achievable within 1-2 hours.

## Task Description
You are to implement a function that accepts a single text string as input and returns another text string as output:

```python
def answer_question(user_question: str) -> str:
   # Your solution here
```

This function will serve as the "backend" for a chatbot designed for retail investors.

To simplify the task, the user query will **always** adhere to the following conditions (no need to check for errors):

- The question will always pertain to a **single** company.
  - The company will be explicitly mentioned in the query (e.g. `cocacola`) and is guaranteed to be present in the dataset.
- The question will always relate to a specific full fiscal year (i.e., only `fiscal_period == "FY"`, no questions about quarters, etc.).
   - The year will be explicitly mentioned in the query as the only four digit number in the query.
   - Information about this year is guaranteed to be present in the dataset.
- The subject of the user's question will always be one of the following five topics (i.e., the user will never ask about any other topic):
   - `Total Revenue`
   - `Net Income / (Loss) Attributable to Common Shareholders`
   - `Price to Earnings (P/E)`
   - `Dividend Yield`
   - `Return on Equity (ROE)`
 
## Example Questions and Answers

Notice that keyword search will not work, for example "revenue" is not mentioned in the question that seeks an answer about revenue. Consider allowing your program to use ChatGPT to assist with the control flow.

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
  
## Guidelines for Software Design

- We recommend using Python [Pandas](https://pandas.pydata.org/) library for loading and processing the CSVs.
- We recommend using the [OpenAI API](https://platform.openai.com/docs/quickstart). Please ensure not to include your API key in the code.
   - You are welcome to utilize any helpful libraries, such as [Marvin](https://www.askmarvin.ai/), [LMQL](https://lmql.ai/), [Microsoft Guidance](https://github.com/microsoft/guidance), [guardrails](https://shreyar.github.io/guardrails), [LangChain](https://python.langchain.com/docs/get_started/introduction.html), or others. However, using the OpenAI API directly is also perfectly acceptable.
- Please place your solution in a public or private Github repository, as per your preference. Don't copy paste your code in chat.
- Don't modify the CSV files. Your program should always read the original files and process them, don't use Excel or the like to manually edit the data in the source file.
- Don't copy-paste the data from CSV to a data structure in your source code. Your program should read the original files and process them, don't manually search for the data yourself.
- It's not mandatory to encapsulate all of your code within a function; you can place some code outside of it as well, for example by using Python classes and methods.
- Feel free to develop in Jupyter notebooks, if you prefer.
   - It would be beneficial if you included a Jupyter notebook to demonstrate any exploratory work you undertake.
