# fermplot-synthetic-demo-data

These data were synthetically generated using the following approach:

1. **Constants Selection**: Constants such as OD to DCW, biomass yield from glucose, and predicted CER were taken from this [paper](https://microbialcellfactories.biomedcentral.com/articles/10.1186/1475-2859-7-26).
2. **Initial Conditions**: Initial glucose concentration, pH level, Optical Density (OD), vessel weight, and agitation were arbitrarily set.
3. **Vessel Volume Calculation**: The volume of the fermentation vessel was calculated by assuming a medium density of 1.03 g/L.
4. **Base Consumption Modeling**: Base consumption was modeled to be linearly derived from biomass growth until the point of induction. After induction, it was derived from product formation.
5. **Product Formation**: Product concentration was modeled using a linear equation. The assumption was that product formation occurs primarily after IPTG induction at 24 hours and is produced linearly thereafter.
6. **Noise Introduction**: Noise was added to the synthetic data to simulate real-world variability. The Python code snippet for introducing noise is:
    ```python
    for col in variable_columns:
        noise = np.random.normal(loc=0, scale=0.1, size=df[col].shape)
        df[col] = df[col] + df[col] * noise
    ```
7. **Data Generation**: Using the above parameters and conditions, three synthetic data files (`synthetic_data_01-03`) were generated.

These data are only intended to be used for demos of the upload feature in the fermPlot application. Please direct any inquiries about this data to [ethan@fermplot.com](mailto:ethan@fermplot.com).
