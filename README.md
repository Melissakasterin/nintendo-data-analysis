# Nintendo Console Sales Analysis

An analysis of official Nintendo sales data comparing hardware and software sales across four console generations: Wii, Wii U, Switch and Switch 2.

## Questions

1. How many software units were sold per hardware unit for each console?
2. Which console has the highest software-to-hardware ratio?
3. Are the results directly comparable, given that the consoles have been on the market for different lengths of time?

## Data

- **Source:** [Nintendo – Dedicated Video Game Sales Units](https://www.nintendo.co.jp/ir/en/finance/hard_soft/index.html) (official Nintendo Investor Relations website)
- **Data as of:** September 30, 2026
- **File:** `data/raw/nintendo_lifetime_sales.csv`
- **Content:** worldwide life-to-date hardware and software sales in million units

## Methods

1. Entered the official sales figures manually into a CSV file
2. Loaded and explored the data with pandas (`shape`, `dtypes`, `describe()`)
3. Checked data quality: missing values and duplicate rows
4. Calculated the software-to-hardware ratio (software units ÷ hardware units)
5. Visualized the results with a bar chart using matplotlib

## Results

![Software-to-hardware ratio by Nintendo console](reports/figures/software_hardware_ratio.png)

- The **Switch** has the highest ratio: **10.14** software units per hardware unit.
- The **Switch 2** has the lowest ratio: **2.78**.

## Limitations

- The data is life-to-date. The Switch 2 launched in June 2025, the Switch in March 2017. The consoles had very different amounts of time to sell software, so their ratios are **not directly comparable**.
- Nintendo reports **sell-in** figures (units shipped to retailers), not units sold to end customers.
- The software figures include games **bundled** with consoles.

## Project Structure

```text
nintendo-data-analysis/
├── data/
│   ├── raw/
│   │   └── nintendo_lifetime_sales.csv   # sales data entered from Nintendo IR
│   └── README.md                         # description of the data folder
├── notebooks/
│   ├── 00_pandas_practice.ipynb          # my pandas practice exercises
│   └── 01_data_overview.ipynb            # main analysis
├── reports/
│   └── figures/
│       └── software_hardware_ratio.png   # chart used in this README
├── .gitignore
├── LICENSE
├── README.md
└── requirements.txt                      # required Python libraries
```

## How to Run

```bash
git clone https://github.com/Melissakasterin/nintendo-data-analysis.git
cd nintendo-data-analysis
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

Then open `notebooks/01_data_overview.ipynb` in VS Code or Jupyter and run all cells.

## Next Steps

- Collect quarterly sales data from Nintendo's earnings reports
- Compare the consoles after the same number of quarters since launch
- Analyze regional sales (Japan, The Americas, Other)