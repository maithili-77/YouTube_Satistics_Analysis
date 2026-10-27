# YouTube_Satistics_Analysis

**Project Overview**
YouTube Video Statistics Analysis is a Big Data Analytics project
that explores YouTube trending-video statistics. It uses Apache Spark
(PySpark) to clean, process, group, and analyze the dataset, then
presents findings through visualizations and an interactive Gradio
dashboard.

The project helps users explore video popularity, channel performance,
category-level statistics, and audience engagement.

**Objectives**
- Analyze video views, likes, dislikes, and comments.
- Identify the most-viewed, most-liked, and most-commented videos.
- Compare statistics across channels and categories.
- Examine relationships between views, likes, and comments.
- Calculate an engagement-rate measure.
- Present analysis results through charts, tables, and an interactive
  dashboard.
  
**Technologies Used**
- Python --- main programming language
- Google Colab / Jupyter Notebook --- development environment
- Apache Spark (PySpark) --- data processing and aggregation
- Pandas --- preparing smaller result tables for display
- Matplotlib / Plotly --- data visualization
- Gradio --- interactive user interface
  
**Dataset**
The project uses a YouTube Trending Video Statistics CSV dataset,
referenced in the notebook as INvideos.csv.
https://www.kaggle.com/datasets/elijahconnectng/youtube-trending-video


Important columns include:

  Column            Meaning
  video_id        Video identifier
  title           Video title
  channel_title   Channel name
  category_id     Video category identifier
  views           Number of views
  likes           Number of likes
  dislikes        Number of dislikes, where available
  comment_count   Number of comments
  publish_time    Video publication time
  description     Video description

The presentation reports 37,352 original rows, 33,320 rows after
duplicate removal, and 33,088 rows after cleaning selected numeric
columns. Actual counts may differ if a different dataset version or
cleaning procedure is used.
Important: The CSV file may need to be uploaded separately to
Colab or placed at the file path expected by the notebook. Check the
dataset's original source and license before redistributing it.

**How the Analysis Works**
1. Load the data from the CSV file into Spark.
2. Inspect and clean the data by removing duplicate records and
   handling missing or invalid values in the fields used for analysis.
3. Process the data with PySpark to sort video records and
   aggregate statistics by channel or category.
4. Calculate engagement rate using the formula below, where views
   are greater than zero:
   Engagement Rate (%) = ((Likes + Comments) / Views) × 100
5. Visualize the results with charts and tables.
6. Explore the results in the Gradio interface by selecting an
   analysis and the number of results to display.
Dashboard Features
The notebook's interactive interface includes analysis options such as:
- Top Viewed Videos
- Top Liked Videos
- Top Commented Videos
- Top Channels
- Category Analysis
- Engagement Analysis
- Views vs. Likes
- Views vs. Comments
Users can select an analysis, choose how many results to display, and
click Analyze to view the resulting table and chart.

**Running the Project in Google Colab**
1. Open the Pyspark_project.ipynb notebook in Google Colab.
2. Upload the required CSV dataset (for example, INvideos.csv) to the
   Colab session, or update the notebook's file path to match its
   location.
3. Run the notebook cells in order, including the package-installation
   cells.
4. Confirm that the dataset loads and the cleaning and analysis cells
   finish successfully.
5. Run the dashboard cell that launches Gradio.
6. Open the Gradio link printed by the notebook to interact with the
   dashboard.
Package installation commands should be taken from the notebook. If a
package import fails, install the missing package in the Colab
environment and rerun the affected cells.
Example Engagement Calculation
If a video has 10,000 views, 800 likes, and 200 comments:

((800 + 200) / 10,000) × 100 = 10%

This is a project-defined engagement measure based on likes and comments
relative to views. It is not an official YouTube metric.

**Project Structure**
A simple suggested structure is:
YouTube-Video-Statistics-Analysis/
├── Pyspark_project.ipynb
├── INvideos.csv                 # Dataset; provide separately if not included
└── README.md
Your actual filenames and folders may differ.

**Limitations**
- Results depend on the dataset version and the cleaning steps
  applied.
- The analysis describes the available data; it does not automatically
  establish why a video became popular.
- The notebook is primarily a data-processing, analysis, and
  visualization project; it should not be described as a
  video-popularity prediction model unless a trained and evaluated
  predictive model is added.
- The engagement rate can be undefined when views are zero, so those
  records should be handled appropriately.
  
**Future Scope**
- Add filters for date, channel, and category.
- Connect to the YouTube Data API for updated statistics, subject to
  API access and quota limits.
- Add and evaluate predictive models for future views or engagement.
- Improve the dashboard with more KPIs, filters, and visualizations.
- Add an option to download analysis results.
  
**Authors**
- Arpita Hanwatkar
- Maithili Mahajan
  
**Conclusion**
This project demonstrates how PySpark can be used to process and analyze
YouTube video statistics. Data cleaning, aggregation, and visualization
help users compare video and channel performance, while Gradio provides
an interactive way to explore the results.
