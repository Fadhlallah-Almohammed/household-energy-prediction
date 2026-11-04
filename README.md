# Household Energy Project

Predict next-hour electricity use from two earlier readings. Compare linear regression with
previous-hour and previous-day predictions. Use the existing selected dataset.

## Weekly tasks

Open plan/weekly_tasks.pdf and go to your member page.
Submit your saved work on Saturdays only: 7, 14, 21 and 28 November 2026.
Keep working files shared during the week so the next person can use them.
On Saturday, save your final weekly changes in the shared project or push them to GitHub,
tick the checklist and tell M1 they are ready. No separate weekly report or ZIP is needed.
M1 submits the project by the team target of 29 November, subject to instructor instructions.

## Open the notebooks

1. Use Python 3.11. From the project folder, run `python -m pip install -r requirements.txt`.
2. Run `jupyter lab` and open your notebook in its member folder.
3. Run cells from top to bottom. The project folder is two levels above the member folder.

| Member | Notebook | Input | Sample output |
|---|---|---|---|
| M2 | prepare_hourly_data.ipynb | data/pilot/half_hour_sample.csv | data/pilot/hourly_sample.csv |
| M3 | prepare_prediction_inputs.ipynb | data/pilot/hourly_sample.csv | data/processed/prediction_inputs_sample.csv |
| M3 | check_input_examples.ipynb | Invented examples | data/processed/input_examples.csv |
| M3 | check_five_rows.ipynb | Half-hour sample and saved sample inputs | data/processed/five_row_check.csv |
| M4 | predict_consumption.ipynb | data/raw/half_hour_readings_2013.csv | results/baseline_predictions_sample.csv |
| M4 | calculate_prediction_errors.ipynb | Saved sample predictions and score_columns.csv | results/baseline_scores_sample.csv |
| M5 | plot_consumption.ipynb | data/pilot/half_hour_sample.csv | Sample figures in figures/ |
| M5 | plot_daily_profile.ipynb | data/pilot/hourly_sample.csv | figures/daily_profile_sample.png |

Run the rows in this order. The input examples notebook needs no real data.
The five-row check needs the file saved by prepare_prediction_inputs.
The error notebook needs predictions saved by predict_consumption.
Generated files use fixed names and are replaced on another run. Keep important older runs in archive/.

## Data files

Members get the data from M1's shared storage; the ignore rules keep readings out of GitHub.

- data/raw/half_hour_readings_2013.csv: selected homes' half-hour readings.
- data/raw/household_metadata.csv: household descriptions and selection evidence.
- data/raw/selected_household_ids.csv: selected home IDs and source blocks.
- data/pilot/half_hour_sample.csv: the small starting sample.
- data/pilot/hourly_sample.csv: the sample converted into hours.
- data/household_split.csv: 300 individual home assignments, 240 development and 60 reserved.
- data/split_rules.json: the fixed home/date rules.

Source: Smart Meters in London, from London Datastore and the Kaggle copy:
https://www.kaggle.com/datasets/jeanmidev/smart-meters-in-london
Local names describe the files; source data and CSV column names have not changed.
Keep source attribution and original license information with the shared dataset package.

## What members create next

The notebooks currently contain sample work. The weekly tasks extend it to the shared dataset:

- M2: data/processed/hourly_readings.csv.
- M3: data/processed/prediction_inputs.csv and prediction_input_counts.csv.
- M4: results/validation_scores.csv and validation_predictions.csv; then test_scores.csv and test_predictions.csv.
- M5: figures/hourly_consumption.png, hourly_distribution.png, daily_profile.png,
  validation_prediction_example.png and the final comparison chart or table.
- M6: reports/project_report.docx and project_report.pdf, or the existing editable report format and its PDF.
- M7: slides/project_presentation.pptx and project_presentation.pdf.
- M1: review shared outputs and submit the final package.

Do not create empty result CSVs. They will be saved by the notebooks during the assigned work.
One member edits each notebook. Members can read each other's shared outputs during the week.

## Evaluation rules

Use the fixed 240 development homes. TRAIN is Jan-Aug 2013, VALIDATION Sep-Oct and TEST Nov-Dec.
Fit only on TRAIN, make choices on VALIDATION and evaluate fixed methods on TEST once.
Score all methods on the same home/time rows. Keep missing readings distinct from measured zero.
Raw timestamps mark half-hour ends in UTC; hourly timestamps mark hour starts.

## GitHub files

Commit notebooks, setup instructions, plan, split files and score column descriptions.
Get the readings from shared storage and regenerate outputs locally. Current ignore rules exclude
raw/pilot readings, generated CSVs/figures, checkpoints and archive backups.
Keep final submission files in reports/ and slides/. Empty folders use .gitkeep.
