# GMP Utility Maintenance Screening

A GIS portfolio project combining utility asset mapping, rule-based maintenance screening, and machine learning anomaly detection in an interactive dashboard.

## Live dashboard

[Open the dashboard](https://gis-siue.maps.arcgis.com/apps/dashboards/f6d21e3bc9104bdd872f2ec5305ae4cd)

## Project objective

Organize utility asset data, identify poles for further review, and present screening results through an accessible web dashboard.

## Work completed

- Prepared study-area pole and distribution-line layers in ArcGIS Pro.
- Calculated pole age and rule-based maintenance priority scores.
- Classified poles as High, Medium, Low, or Unknown priority.
- Applied an unsupervised PCA anomaly screen to eligible pole records.
- Published the layers and web map to ArcGIS Online.
- Built a dashboard with asset counts, a priority chart, an interactive map, and a review list.
- Configured chart selections to filter the map and list selections to zoom to individual poles.
- Exported the dashboard configuration to JSON for backup.

## Results

| Measure | Result |
|---|---:|
| Total poles | 11,133 |
| High maintenance priority | 1,299 |
| Poles screened for anomalies | 11,126 |
| Poles flagged for review | 561 |
| Poles excluded because age was missing | 7 |
| Distribution-line feature records | 31 |

The review list displays 25 ML-flagged poles with the highest rule-based maintenance scores. Distribution-line records may contain multipart geometry; the count does not represent individual wire spans.

## Machine learning approach

Principal Component Analysis (PCA) was used for unsupervised anomaly screening to identify unusual combinations of pole attributes.

The anomaly flag and maintenance priority score serve different purposes:

- **Maintenance priority:** a rule-based screening classification.
- **ML anomaly flag:** an unusual asset record requiring inspection or data verification.

These results are not validated failure predictions. Inspection and failure history would be needed to develop and evaluate a predictive model.

## Tools

- ArcGIS Pro: data preparation, analysis, and symbology
- Python and ArcPy: asset processing and field calculations
- NumPy: PCA-based anomaly screening
- ArcGIS API for Python: dashboard configuration retrieval and export
- ArcGIS Online: hosted layers and web map publishing
- ArcGIS Dashboards: visualization and interactive actions
- GitHub: documentation and configuration backup

## Code and configuration

Analysis was performed in an ArcGIS Pro Python notebook.

The notebook covered layer and field inspection, maintenance screening, anomaly screening, and dashboard export.

`dashboard.json` contains the exported dashboard configuration. It depends on the published ArcGIS web map and layers; it is not a standalone application or a copy of the underlying data.

## Limitations

- Screening results require field verification.
- Missing age data prevented seven poles from entering ML screening.
- No predictive accuracy or failure probability was established.
- Distribution lines were mapped but were not assigned a validated risk model.
- This project does not provide a complete 3D digital twin.

## Author

Hanson Tawiah

Independent portfolio demonstration using Green Mountain Power asset data. This project does not imply endorsement by Green Mountain Power.
