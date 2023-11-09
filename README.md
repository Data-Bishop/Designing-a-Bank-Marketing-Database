# Piggy Bank: Bank Marketing Database Project
Author: Abasifreke Nkanang (DataBishop)

<iframe width="560" height="315" src='https://dbdiagram.io/e/654d5d057d8bbd6465e2494a/654d5d137d8bbd6465e24a2a'> </iframe>

## Introduction

Personal loans are a significant revenue source for banks, with interest rates often hovering around 10%. To harness the potential of this financial opportunity, you've been entrusted with the task of working alongside a bank to clean and store data collected during a recent marketing campaign aimed at persuading customers to take out personal loans. The bank's future marketing campaigns will also rely on this stored data. Thus, your mission is to set up a PostgreSQL database and design a schema that allows for the easy import of data from upcoming campaigns.

You have been provided with a CSV file named "bank_marketing.csv," which you will clean, reformat, and split into separate files based on the tables you'll create. The use of Pandas is highly recommended for these data manipulation tasks. Finally, you will write SQL code that the bank can execute to create the required tables and populate them with data from the CSV files. To ensure security compliance, you'll save the SQL code as multiline string variables that the bank can employ to establish the database on their end.

## Project Details

### Database Design

The database will consist of three key tables:

#### 1. Client Table

- **id (serial)**: Client ID - primary key (corresponds to `client_id` in the dataset).
- **age (integer)**: Client's age in years (from the `age` column).
- **job (text)**: Client's type of job (from the `job` column).
- **marital (text)**: Client's marital status (from the `marital` column).
- **education (text)**: Client's level of education (from the `education` column).
- **credit_default (boolean)**: Whether the client's credit is in default (from the `credit_default` column).
- **housing (boolean)**: Whether the client has an existing housing loan (mortgage) (from the `housing` column).
- **loan (boolean)**: Whether the client has an existing personal loan (from the `loan` column).

#### 2. Campaign Table

- **campaign_id (serial)**: Campaign ID - primary key (new column, no direct mapping in the dataset).
- **client_id (serial)**: Client ID - references `id` in the Client table.
- **number_contacts (integer)**: Number of contact attempts to the client in the current campaign (from the `campaign` column).
- **contact_duration (integer)**: Last contact duration in seconds (from the `duration` column).
- **pdays (integer)**: Number of days since contact in the previous campaign (999 indicates not previously contacted, from the `pdays` column).
- **previous_campaign_contacts (integer)**: Number of contact attempts to the client in the previous campaign (from the `previous` column).
- **previous_outcome (boolean)**: Outcome of the previous campaign (from the `poutcome` column).
- **campaign_outcome (boolean)**: Outcome of the current campaign (from the `y` column).
- **last_contact_date (date)**: Last date the client was contacted (a combination of day, month, and the newly created year).

#### 3. Economics Table

- **client_id (serial)**: Client ID - references `id` in the Client table.
- **emp_var_rate (float)**: Employment variation rate (quarterly indicator, from the `emp_var_rate` column).
- **cons_price_idx (float)**: Consumer price index (monthly indicator, from the `cons_price_idx` column).
- **euribor_three_months (float)**: Euro Interbank Offered Rate (euribor) three-month rate (daily indicator, from the `euribor3m` column).
- **number_employed (float)**: Number of employees (quarterly indicator, from the `nr_employed` column).

## Usage

1. **Data Preparation**: Use Pandas to clean, reformat, and split the "bank_marketing.csv" data into separate files based on the tables specified.
2. **SQL Script**: Write SQL scripts to create the tables and populate them with data from the cleaned CSV files.
3. **Database Setup**: Execute the SQL scripts to establish the PostgreSQL database on the bank's end.

## Contribution

Contributions to this project are welcome. If you have suggestions, improvements, or additional features, please feel free to fork the repository, make your changes, and submit a pull request.

## License

This project is open-source and available under the [Apache License](LICENSE). Feel free to use, modify, and distribute it in accordance with the license terms.

---

Happy Banking and Data Management! 🐖💰🏦