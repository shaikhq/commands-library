__When loading a dataframe from a csv file, how to add the column headers separately?__
I was creating a dataframe by loading its content from a csv file. The file had only the dataframe content, not the column headers. I used the 
following code to append the column headers to the dataframe. 
```python
import pandas as pd

# Define the column names as a list
column_names = ['col1', 'col2', 'col3', 'col4']

# Add the column names while creating the dataframe
df = pd.read_csv('file.csv', names=column_names)
```

__how to loop the values of a column in a dataframe?__
```python
for value in df['col1']:
    print(value)
```

__I am generating dataframes in a loop. I want to concatenate all the dataframes in the vertical axis and have a single dataframe at the end of the loop.__
```python
import pandas as pd

# a list that will store all the dataframes generated inside the loop
dfs = []

for i in range(10):  # replace the value in range with the number of time the loop will run
    # Generate a DataFrame. Customize the logic for generating a dataframe. 
    df = pd.DataFrame() 
    # Add this dataframe to the list.  
    dfs.append(df)

# Concatenate all the DataFrames along the vertical axis
final_df = pd.concat(dfs, axis=0)
```