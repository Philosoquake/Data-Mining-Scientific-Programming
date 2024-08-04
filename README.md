# Tagesschau Data Mining Project

This project aims to uncover insights from the Tagesschau.de dataset using data science techniques. The project includes data acquisition, processing, analysis, and visualization.

## Name
Tagesschau Data Mining Project

## Description
This project analyzes news articles from Tagesschau.de to uncover insights about various natural disasters reported across different regions. The analysis includes data acquisition, cleaning, processing, and visualization of the results.

## Visuals
This project includes visualizations of the distribution and frequency of disaster reports across different regions in Germany. The visualizations are created using bar charts and grouped bar charts.

## Installation
To run this project, follow these steps:
1. Clone the Gitlab repository.
2. Install the necessary packages:
    ```julia
    using Pkg
    Pkg.add("DataFrames")
    Pkg.add("CSV")
    Pkg.add("Plots")
    Pkg.add("Test")
    Pkg.add("Dates")
    Pkg.add("Markdown")
    Pkg.add("InteractiveUtils")
    Pkg.add("DataStructures")
    Pkg.add("StatsPlots")
    Pkg.add("Colors")
    ```
3. Ensure you have all the required datasets (`geotags.csv`, `tags.csv`, `taggeschau.csv`, `regions.csv`) in the `data` directory.
4. Open the Pluto notebook and run all the cells.

## Usage
To run the analyses and generate the visualizations:
1. Load the data and run the analyses as described in the notebook.
2. The visualizations will be generated based on the data analysis methods provided.

## Project Structure
    
- **Data Loading**: Load and display the datasets.
- **Explorative Data Analysis**: Analyze and understand the datasets.
- **Formulate Questions**: Identify interesting questions to explore.
- **Data Processing**: Develop methods to answer the questions.
- **Visualization**: Visualize the results.
- **Documentation**: Document the project and methods.
- **Unit Tests**: Ensure methods work as intended.

## Key Questions and Answers

### 1. How are geotags distributed across articles?
- The `analyze_geotags` function analyzes the distribution of geotags in articles. It shows the frequency of each geotag, highlighting the geographical focus of the articles.

### 2. How often are flood-related articles published, and which regions are most affected?
- The `get_flood_news` and `get_flood_count_by_region` functions identify and count flood-related articles. The results show the number of flood events reported in each region.

### 3. How often are forest fire-related articles published, and which regions are most affected?
- The `get_forestfire_news` and `get_forestfire_count_by_region` functions identify and count forest fire-related articles. The results show the number of forest fire events reported in each region.

### 4. How often are volcanic eruption-related articles published, and which regions are most affected?
- The `get_vulkan_news` and `get_vulkan_count_by_region` functions identify and count volcanic eruption-related articles. The results show the number of volcanic eruption events reported in each region.

### 5. How often are earthquake-related articles published, and which regions are most affected?
- The `get_earthquake_news` and `get_earthquake_count_by_region` functions identify and count earthquake-related articles. The results show the number of earthquake events reported in each region.

### 6. What is the overall distribution of disaster-related articles by region?
- The `get_disaster_count_by_region` function combines all disaster-related articles and provides a comprehensive view of the distribution of these events by region. It highlights which regions are most frequently reported for each type of disaster.

## Support
For support, please contact:
- Kathrin Fuchs - [kathrin.fuchs@tuhh.de](mailto:kathrin.fuchs@tuhh.de)
- Klevi Elezi - [klevi.elezi@tuhh.de](mailto:klevi.elezi@tuhh.de)
- Taulant Xhelili - [taulant.xhelili@tuhh.de](mailto:taulant.xhelili@tuhh.de)

## Roadmap
Future releases may include:
- Enhanced visualizations.
- Additional data analysis techniques.
- Integration with more datasets.

## Contributing
We are open to contributions. Please follow these steps to get started:
1. Fork the repository.
2. Create a new branch (`git checkout -b feature-branch`).
3. Make your changes.
4. Commit your changes (`git commit -am 'Add new feature'`).
5. Push to the branch (`git push origin feature-branch`).
6. Create a new Pull Request.

## Authors and acknowledgment
This project was developed by:
- Kathrin Fuchs
- Klevi Elezi
- Taulant Xhelili

## License
This project is licensed under the MIT License.

## Project status
We worked extensively on this project and faced several challenges:
- Difficulty in joining the tables `taggeschau`, `geotags`, and `tags` using the `externalId` column and retrieving the names of the cities.
- Although the tables were joined successfully, we faced issues integrating the new table into a DataFrame and combining it with the catastrophe DataFrame for plotting.
- Initially, we couldn't understand the `regionId` column, but later found its meaning on the taggeschau.de website.
- We struggled with defining the `regionId 0`. After discussions, we concluded that it's best to ignore this undefined region to proceed with the project.
- We created a new CSV file with the `regionId` and the corresponding city names.

Despite these challenges, the project provides valuable insights and visualizations related to natural disasters reported on Tagesschau.de.

## Unit Tests

The project includes comprehensive unit tests for the core methods to ensure they function correctly. The tests cover:

- `analyze_geotags`
- `context_search` (including regex matching)
- `remove_from_dataframe`
- `group_by_date_interval` (tested with a `SubDataFrame`)
- `get_flood_news`
- `get_forestfire_news`
- `get_vulkan_news`
- `get_earthquake_news`
- `get_flood_count_by_region`
- `get_forestfire_count_by_region`
- `get_vulkan_count_by_region`
- `get_earthquake_count_by_region`
- `get_disaster_count_by_region`
