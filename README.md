# ECE2112_PA3
Milan, Rye Keane Lorenzo | 2ECE-D

# Problem 1: Positional and Label-Based Slicing
After loading the dataset, display the shape and the complete list of column names for the cars DataFrame. Next, using positional slicing, create a new DataFrame called `cars_6_to_10 that` contains rows 6 through 10 of the dataset, where the first data row is considered row 1. From this new subset, display only the columns Model, `mpg, cyl, hp, and gear`, strictly in that order.

The code first uses the `shape` attribute and columns property to verify the overall dimensions

```
print("Shape of the dataset:", cars.shape)
print("\nComplete list of columns:", list(cars.columns))
```

When taking specific rows, Pandas uses zero-based indexing, so the count always starts at zero. To isolate rows six to 10, the `.iloc` with the range of `[5:10]` will work perfectly in this scenario. 

```
cars_6_to_10 = cars.iloc[5:10]
```

Now that the right rows are in order, they need to be filtered down to just the requested columns. By using `.loc`, the `:` tells Pandas to keep all the rows in the new subset, while the bracketed list picks out the exact columns in the required order.  

```
cars_6_to_10 = cars_6_to_10.loc[:,['Model', 'mpg', 'cyl', 'hp', 'gear']]

print("\nRows 6 to 10 (Selected Columns):")
display(cars_6_to_10)
```

# Problem 2: Model Lookup
Rely strictly on Boolean indexing on the Model column to fulfill two requests without using any hard-coded row numbers to locate the vehicles. First, display the complete row for the Toyota Corolla and store the result in a variable named toyota. Second, for the Pontiac Firebird, display only the Model, mpg, hp, and wt columns, and store this result in a variable named pontiac.

In this problem, a straightforward approach would be to simply enter the exact row numbers for the specific models. In more advanced cases, the straightforward solution becomes risky because the dataset could change at any time without notice. To avoid headaches with those kinds of scenarios, a boolean condition can be used such that the code evaluates the condition: `cars['Model'] == 'Toyota Corolla'`. This serves as a true-or-false filter across the entire `Model` column. Placing this filter inside `.loc` pulls the exact row where the condition is True. Since no columns were specified, it defaults to looking at all of the columns for the Corolla.   

```
toyota  = cars.loc[cars['Model'] == 'Toyota Corolla']
```

For the Pontiac Firebird, the code handles both row search and column filtering simultaneously. Inside `.loc`, the first argument finds the correct row similar to how the Corolla was hunted down, and the second argument is a list that specifies exactly which columns to keep. This accomplishes the task in a single line. The `display()` function then outputs both variables as tables.

```
pontiac = cars.loc[cars['Model'] == 'Pontiac Firebird', ['Model', 'mpg', 'hp', 'wt']]

print("Toyota Corolla Details:")
display(toyota)

print("\nPontiac Firebird Selected Details:")
display(pontiac)
```

# Problem 3: Multi-Model Subsetting
Create a DataFrame named selected cars containing only the records for three exact models: Datsun 710, Lotus Europa, and Ferrari Dino. For these specific records, retain only the columns `Model, mpg, cyl, hp, and gear`. You must select these rows by their model values rather than their numeric row positions. Once complete, display the selected cars DataFrame along with its shape.

Instead of writing three separate blocks of code for the three different cars, the conditions are combined. By using the OR operator `(|)`, the code looks for the Datsun 710, Lotus Europa, or Ferrari Dino all at once. Each condition must be placed in parentheses so that it runs properly. The combined conditions are then passed to `.loc`, along with the list of required columns, to generate the precise table immediately.

```
selected_cars = cars.loc[(cars['Model']=='Datsun 710') | (cars['Model']=='Lotus Europa') | (cars['Model']=='Ferrari Dino'), ['Model', 'mpg', 'cyl', 'hp', 'gear']]
```

Before showing the final table, the code prints `selected_cars.shape` to verify that the output has exactly 3 rows and 5 columns. Once confirmed, `display()` presents the final output.

```
print("Shape of selected cars:", selected_cars.shape)
print("\nSelected Cars Dataset:")
display(selected_cars)
```

---

Read Me File Version History

September 6, 2026 - Uploaded the finished `ipynb` file

September 6, 2026 - Started writing the README file

September 6, 2026 - Finished the repository

