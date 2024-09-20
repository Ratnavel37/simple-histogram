# Population Data Analysis

This project analyzes the distribution of population across different countries in the year 2020 using the World Bank's population data. The data is visualized through a histogram plot to depict the number of countries in various population ranges.

## Files

- `API_SP.POP.TOTL_DS2_en_csv_v2_3401680.csv`: The population dataset downloaded from the World Bank. It contains population data for different countries and regions over the years.
  
## Requirements

This project uses the following Python libraries:
- `pandas`: For data manipulation and analysis.
- `matplotlib`: For plotting the population histogram.

Make sure to install these packages if they are not already installed:

```bash
pip install pandas matplotlib
```

## Code Explanation

The script performs the following steps:

1. **Load the Data**: 
   The CSV file is loaded using `pandas.read_csv()`. The first four rows, which are metadata, are skipped using the `skiprows` parameter.
   
   ```python
   data = pd.read_csv(file_path, skiprows=4)
   ```

2. **Extract Population Data for 2020**: 
   The script extracts the population data for the year 2020 and filters out any missing values using `dropna()`. The resulting DataFrame consists of two columns: 'Country Name' and the population in 2020.
   
   ```python
   population_2020 = data[['Country Name', '2020']].dropna()
   ```

3. **Create a Histogram**: 
   A histogram of the population distribution is plotted using `matplotlib`. The population data is divided into 30 bins, and the edges of the bins are highlighted for clarity.
   
   ```python
   plt.hist(population_2020['2020'], bins=30, edgecolor='black')
   ```

4. **Plot Customization**: 
   Titles and axis labels are added to the plot for better readability, and a grid is displayed to improve visualization.

   ```python
   plt.title('Distribution of Population in 2020 Across Countries')
   plt.xlabel('Population')
   plt.ylabel('Number of Countries')
   plt.grid(True)
   ```

5. **Display the Plot**: 
   The histogram is displayed using `plt.show()`.

## Usage

1. Place the `API_SP.POP.TOTL_DS2_en_csv_v2_3401680.csv` dataset in the same directory as the script.
2. Run the Python script in your environment (e.g., Google Colab or a local Python environment).
3. The script will display a histogram of the distribution of population across countries for the year 2020.

## Example Output

The histogram will show the number of countries that fall into various population ranges in 2020, providing insights into how populations are distributed across different countries.
