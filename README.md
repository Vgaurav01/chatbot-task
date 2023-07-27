# chatbot-task

Your assignment is to create a simple Python function. We've designed this task to be achievable within 1-2 hours.

## Task Description
You are to implement a function that accepts a single text string as input and returns another text string as output:

```python
def answer_question(user_question: str) -> str:
   # Your solution here
```

This function will serve as the "backend" for a chatbot designed for retail investors.

To simplify the task, the user question will **always** adhere to the following conditions (no need to check for errors):

- The question always explicitly names exactly one specific company (for example "walmart" for Walmart Inc.)
   - Information about this company is guaranteed to be present in the dataset.
- The question always has a single four digit number XXXX, that's the full fiscal year related to the question
   - In other words, filter for only `fiscal_period == "FY"`, as there will be no questions about quarters, etc.
   - Information about this year is guaranteed to be present in the dataset.
- The user always asks for one out of five factual **quantities** of a single company for a single year.
   - For example question `In 2022, how much was the dollar value of goods sold by walmart?`, refers to `Total Revenue`.
   - All of the quantities are directly available in the CSV data files. The user will never ask about anything else.
   - The five quantities are:
      - `Total Revenue`
      - `Net Income / (Loss) Attributable to Common Shareholders`
      - `Price to Earnings (P/E)`
      - `Dividend Yield`
      - `Return on Equity (ROE)`
 
## Example Questions and Answers

Notice that keyword search will not work, for example "revenue" is not mentioned in the question that seeks an answer about revenue. Consider allowing your program to use OpenAI API (ChatGPT) to assist with the control flow.

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
- Please place your solution in a public or private Github repository, as per your preference. We would expect to find one (or multiple) `.py` or `.ipynb` files with your source code in it. Don't copy-paste your code to chat applications.
- Don't modify the CSV files. Your program should read the original CSV files and process them, don't use something like Excel to manually edit the data in the CSV files.
- Don't copy-paste the data from CSV to a data structure in your source code. Your program should read the original CSV files and process them, don't manually search for the data yourself.
- Use only the CSV files as the source of truth, don't depend on OpenAI API or the any other sources for the factual information.
- It's not mandatory to encapsulate all of your code within a function; you can place some code outside of it as well, for example by using Python classes and methods.
- Feel free to develop in Jupyter notebooks, if you prefer.
   - It would be beneficial if you included a Jupyter notebook to demonstrate any exploratory work you undertake.
- **BONUS POINTS**. Let's send only send **one** (final) quantity to ChatGPT (instead of just including the multiple values from CSV, or the CSV itself), by doing all the data filtering in pandas. This may require multiple LLM prompts to be sent.
