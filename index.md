
# PeakAnalyser

**PeakAnalyser** is a freeware Windows desktop application for visualizing aggregated heating demand profiles and assessing the feasibility of shifting peak heating demand to earlier time periods.

## Download

### [Download PeakAnalyser Beta Version with Example Data]({{ site.github.repository_url }}/releases/latest/download/v0.1.0-beta.1/PeakAnalyser-v0.1.0-beta.1.zip)
The download package contains:

- `PeakAnalyser.exe`
- `PeakAnalyser-example.csv`

[View the latest release notes]({{ site.github.repository_url }}/releases/tag/v0.1.0-beta.1)

> The application is provided free of charge. The source code is not publicly distributed.

### Running the application

1. Extract the downloaded ZIP file.
2. Open the extracted folder.
3. Double-click `PeakAnalyser.exe`.
4. Select **Load CSV File**.
5. Choose `PeakAnalyser-example.csv` to test the application.


<div style="text-align: center; margin: 1.5rem 0;">
  <img
    src="{{ '/assets/images/screenshot_1.png' | relative_url }}"
    alt="PeakAnalyser main window"
    style="height: 350px; width: auto; max-width: 100%; object-fit: contain;"
  >
</div>

<div style="
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 16px;
  flex-wrap: wrap;
  margin: 1.5rem 0;
">
  <img
    src="{{ '/assets/images/screenshot_2.png' | relative_url }}"
    alt="PeakAnalyser automated analysis"
    style="height: 350px; width: auto; max-width: 100%; object-fit: contain;"
  >

  <img
    src="{{ '/assets/images/screenshot_3.png' | relative_url }}"
    alt="PeakAnalyser manual analysis"
    style="height: 350px; width: auto; max-width: 100%; object-fit: contain;"
  >
</div>

---

## Main features

* **Interactive visualization:** Zoom, pan and hover over data points to view exact values.
* **Peak load analysis:** Set the peak power limit by entering a value or dragging the horizontal peak-limit line.
* **Automated feasibility check:** Analyse whether the available capacity before a peak event is sufficient to shift the excess demand.
* **Manual shift analysis:** Select a buffer period and peak period to calculate the excess energy and available buffer capacity.
* **Demand scaling:** Apply a scale factor to simulate higher or lower heating demand.
* **Standalone application:** Run PeakAnalyser as a Windows executable without installing Python.

## Installation

1. Download `PeakAnalyser.exe` using the download link above.
2. Save the file in a suitable folder on your computer.
3. Double-click `PeakAnalyser.exe` to start the application.

## CSV input format

PeakAnalyser expects a CSV file containing at least the following columns:

| Column      | Description                                    |
| ----------- | ---------------------------------------------- |
| `Timestamp` | Date and time in the format `YYYY-MM-DD HH:MM` |
| `Power`     | Heating demand as a numeric value in kW        |

Example:

```csv
Timestamp,Power
2026-01-01 00:00,645.2
2026-01-01 01:00,621.7
2026-01-01 02:00,598.4
```

PeakAnalyser has currently been tested with hourly time steps.

## Basic workflow

### 1. Set the initial peak limit

Enter a value in the **Peak Power (kW)** field.

The default initial value is `800 kW`. Setting an appropriate value before loading the data affects the initial scaling of the plot.

### 2. Load the CSV file

Select **Load CSV File** and choose the CSV file containing the heating-demand profile.

### 3. Adjust the peak limit

The peak limit can be changed in either of the following ways:

* Drag the purple dashed line up or down.
* Enter a value in the **Peak Power (kW)** field and press **Enter**.

The panel on the right displays the automated feasibility results.

### 4. Scale the demand profile

Enter a value in the **Scale Factor** field and select **Apply**.

The demand profile and corresponding analysis are updated using the selected scale factor.

### 5. Perform a manual analysis

1. Select **Lock Peak Line**.
2. Click three points on the graph:

   * The first point marks the beginning of the available buffer period.
   * The second point marks the end of the buffer period and the beginning of the peak event.
   * The third point marks the end of the peak event.
3. Select **Analyze & Visualize**.

PeakAnalyser calculates and displays:

* The excess energy demand above the selected peak limit
* The available buffer capacity before the peak event
* Whether the selected load shift is feasible

### 6. Start another manual analysis

Select **Clear Markers** to remove the three selected points and perform another analysis using the same demand profile.

## Notes and limitations

* The application has currently only been tested with hourly input data.
* The automated analysis evaluates the available capacity before peak events based on the selected peak limit for each day.

## Support and issue reporting

Problems and suggestions can be reported through the repository’s [Issues page]({{ site.github.repository_url }}/issues).

When reporting an issue, include:

* A description of the problem
* A screenshot of any error message

Do not upload confidential demand data to a public issue.

## Licence

PeakAnalyser is distributed as proprietary freeware. 
It may be downloaded and used free of charge, but its source code is not publicly distributed.

See the [PeakAnalyser Freeware Terms]({{ '/FREEWARE-LICENSE.html' | relative_url }}) for further information.
