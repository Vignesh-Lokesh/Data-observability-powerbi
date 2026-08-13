# Project Workflow

The mock files simulate incoming daily data.

1. CSV files represent incoming source files.
2. Power Query is used for data preparation and transformation.
3. The cleaned data is loaded into the Power BI model.
4. DAX measures calculate data-quality indicators.
5. Power BI cards and charts visualize the results.
6. Date slicers allow users to investigate individual days.
7. The dashboard status changes according to the selected filter context.

In a production implementation, the mock source can be replaced with an enterprise source such as a Microsoft Fabric Lakehouse.
