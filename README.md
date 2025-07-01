# Capstone-Project
## Report: Demand Function and Pricing Behavior
### Demand Function
The pricing model is based on a linear demand function where the price is adjusted from a base price of $10 according to:
- **Occupancy Rate**: For every 1% above 50% occupancy, the price increases by $0.05, reflecting higher demand.
- **Traffic Conditions**: Low traffic reduces the price by $1, average has no effect, and high traffic increases it by $2, capturing external demand pressure.
- **Queue Length**: For every unit above 3, the price increases by $0.5, incentivizing rerouting when queues are long.
- **Special Days**: A $2 premium is added on special days (e.g., holidays) due to expected higher demand.
- **Vehicle Type**: Cars and trucks increase the price by $1, while cycles reduce it by $1, reflecting space and value differences.
- **Smoothing**: The price is computed as 70% of the new calculated price and 30% of the previous price to ensure smooth transitions.

### Pricing Behavior
- **High Demand**: When occupancy rates exceed 50% (e.g., >288 spaces for BHMBCCMKT01, >960 for Shopping), prices increase significantly, especially during high traffic or special days. For example, on 08-10-2016 at 13:30 for BHMBCCMKT01 (Occupancy=357, 61.9% rate, high traffic, queue=7), the price would be approximately $13.95.
- **Low Demand**: Early mornings (e.g., 8:00 AM) with low occupancy and traffic result in prices close to or below $10 (e.g., $9.50 for cycles).
- **Competitor Comparison**: The dynamic price generally exceeds the simulated competitor price ($10 ± $2) during peak hours, justifying the model's responsiveness to demand.

### Visualizations
- **Pricing Plots**: Show dynamic prices (blue) versus competitor prices (red) over time, highlighting how prices rise with demand (e.g., midday peaks) and drop during low demand (e.g., early morning).
- **Occupancy Plots**: Display occupancy rate trends, correlating higher rates with price increases, providing transparency into pricing decisions.

### Interesting Insight
An unexpected observation is the significant occupancy spike on 15-10-2016 for BHMBCCMKT01 (442 spaces at 15:01), despite no special day indicator, suggesting an unrecorded event or data anomaly that drove high demand and elevated prices.

## Conclusion
The baseline linear model effectively adjusts prices based on real-time demand signals, ensuring higher prices during peak usage and lower prices during off-peak times. The Pathway integration enables real-time processing, and Bokeh visualizations clearly demonstrate the model's responsiveness to occupancy and external factors. Future improvements could include more complex models (e.g., machine learning) and rerouting logic to optimize parking lot utilization.
