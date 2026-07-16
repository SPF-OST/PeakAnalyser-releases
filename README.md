# Peak Analyser

A GUI application to visualize aggregated heating demand profiles and analyze the feasibility of peak load shifting.
This tool allows users to visualize demand data (and scale it up), interactively adjust peak power limits, and calculate the feasibility of shifting excess energy demand to earlier time periods.


* **Interactive Visualization:** Zoom, pan, and hover over data points to see exact values.
* **Peak Load Analysis:** Drag a horizontal line to set a power limit (kW) or type a specific value.
* **Automated Feasibility Check:** Instantly checks every day in the dataset to see if there is enough preceding capacity to cover the excess demand above the peak limit.
* **Manual Shift Calculation:** Select specific regions using markers to calculate exact energy excess (kWh) and available buffer capacity.
* **Data Scaling:** Apply scale factors to the dataset dynamically to simulate higher/lower demand scenarios.
* **Standalone Executable:** Can be packaged into a single `.exe` file with a splash screen.

## User Instructions

### CSV Format

The application expects a CSV file with at least two columns:

* **Timestamp**: A date/time string (e.g., 2023-01-01 00:00).
* **Power**: A numeric value representing the heating demand (kW).

The code has only been tested with hourly timestamp.

### Workflow

1. _Set Peak Limit_: Type a value in the `Peak Power (kW)` box. Default initial value is _800_. This would affect the scaling of the plot which is displayed.

2. _Load File_: Click `Load CSV File` to browse the CSV file and load your data.

3. _Adjust Peak Limit_:

* Drag the Purple Dashed Line up or down or type a value in the `Peak Power (kW)` box and press Enter.

* Check the panel on the right for an immediate automated feasibility report.

4. _Scale_ the Demand profile up by typing `Scale Factor` and then click `Apply`.

5. _Manual Analysis_:

* Check the box `Lock Peak Line`.
* Click 3 points on the graph to define the shift regions: The first point denotes start of available capacity (Buffer start), the second point marks the start of the peak event (Buffer end / Peak start)
  and the third point marks the end of the peak event.
* Click `Analyze & Visualize` to see the calculation results.

6. Click `Clear Markers` to _reset_ the three marked points and start a new analysis on the same plot.

