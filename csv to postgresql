import pandas as pd
import psycopg2
from sqlalchemy import create_engine
from sqlalchemy import text

# Define our PostgreSQL connection string
conn_string = "postgresql+psycopg2://user:password@127.0.0.1:5432/database_name"

# Create the connection engine
engine = create_engine(conn_string)

# Load the CSV file into a DataFrame
df = pd.read_csv(r'C:\Users\user\Desktop\mytable.csv')

print("CSV file loaded successfully.")
# Write data to PostgreSQL
df.to_sql('table_name', engine, if_exists='replace', index=False)

print("Data sent to PostgreSQL.")

# Verify data insertion
with engine.connect() as connection:
    result = connection.execute(text("SELECT COUNT(*) FROM table_name"))
    row_count = result.first()[0]

print(f"Number of rows in table_name: {row_count}")
