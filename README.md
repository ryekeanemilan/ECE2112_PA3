# ECE2112_PA2
Milan, Rye Keane Lorenzo | 2ECE-D

# Problem 1: Positional and Label-Based Slicing
After loading the dataset, display the shape and the complete list of column names for the cars DataFrame. Next, using positional slicing, create a new DataFrame called `cars_6_to_10 that` contains rows 6 through 10 of the dataset, where the first data row is considered row 1. From this new subset, display only the columns Model, `mpg, cyl, hp, and gear`, strictly in that order.


# Problem 2: Model Lookup
Rely strictly on Boolean indexing on the Model column to fulfill two requests without using any hard-coded row numbers to locate the vehicles. First, display the complete row for the Toyota Corolla and store the result in a variable named toyota. Second, for the Pontiac Firebird, display only the Model, mpg, hp, and wt columns, and store this result in a variable named pontiac.

# Problem 3: Multi-Model Subsetting
Create a DataFrame named selected cars containing only the records for three exact models: Datsun 710, Lotus Europa, and Ferrari Dino. For these specific records, retain only the columns `Model, mpg, cyl, hp, and gear`. You must select these rows by their model values rather than their numeric row positions. Once complete, display the selected cars DataFrame along with its shape.
