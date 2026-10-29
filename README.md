# Lending Club loan portfolio analysis

Which loans made money, and which didn't? This project looks at about 1.3 million
finished Lending Club loans (2007 to 2018) and compares default rate and net return
across grade, term, purpose, income, debt-to-income and state.

## Main findings

- Grades A and B return about 5% over the life of the loan. Grade D is roughly
  break-even, and grades E, F and G lose money on average.
- 60-month loans default more in every grade and return less in grades A to F.
- For 36-month loans, net return peaked at 11.1% for 2013 loans and fell to 6.6% for
  2015 loans, as interest rates dropped and defaults rose.
- Small business loans default about twice as often as other loans in grade A.
- Loans with a debt-to-income ratio above 30 lose money on average.
- Default falls steadily as income rises, from 23.7% (under $40k) to 15.6% ($120k and over).

## Stack

Python (pandas), DuckDB for SQL, Power BI for the dashboard.

## How to run

1. Download `accepted_2007_to_2018Q4.csv.gz` from Kaggle (Lending Club dataset) into this folder.
2. `pip install -r requirements.txt`
3. Run `loans.ipynb` from top to bottom. It builds the DuckDB database and writes the
   summary tables to `exports/`.

## Notes

- Only loans with a final outcome (Fully Paid or Charged Off) are included.
- Net return is total payments minus loan amount, divided by loan amount, over the whole
  life of the loan, so only compare loans with the same term.
- Income figures are in US dollars.
- Loans issued after 2015 are left out of the year trend because many were still running
  when the data ends.