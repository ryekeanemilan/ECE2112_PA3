# ECE2112_PA2
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
```

# Problem 2: Model Lookup
Rely strictly on Boolean indexing on the Model column to fulfill two requests without using any hard-coded row numbers to locate the vehicles. First, display the complete row for the Toyota Corolla and store the result in a variable named toyota. Second, for the Pontiac Firebird, display only the Model, mpg, hp, and wt columns, and store this result in a variable named pontiac.

# Problem 3: Multi-Model Subsetting
Create a DataFrame named selected cars containing only the records for three exact models: Datsun 710, Lotus Europa, and Ferrari Dino. For these specific records, retain only the columns `Model, mpg, cyl, hp, and gear`. You must select these rows by their model values rather than their numeric row positions. Once complete, display the selected cars DataFrame along with its shape.
