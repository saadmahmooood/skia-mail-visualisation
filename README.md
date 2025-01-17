# Analyzing an Email Archive from Gmane

This project provides tools to analyze and visualize email data using Python and the D3 JavaScript library. It retrieves email archives from a cached subset of Gmane.org data and processes them for further analysis and visualization.

---

## Features

### **Data Retrieval**
- Retrieve email data from the archive at [Dr. Chuck's Cache](http://mbox.dr-chuck.net/export.php).
- Use `gmane.py` as a spider to fetch email data incrementally and store it in `content.sqlite`.
- Supports restarting to handle interruptions or throttling.

### **Data Processing**
- Use `gmodel.py` to clean and compress data from `content.sqlite` into `index.sqlite`.
- Perform email mapping for consistent sender and domain representations.
- Supports iterative refinement of data mappings for better analysis.

### **Data Analysis**
- Generate insights such as:
  - Top email participants.
  - Most active organizations.
- Perform word frequency analysis in email subject lines.

### **Data Visualization**
- Visualize participation trends over time with `gline.py`.
- Create word clouds of subject line keywords with `gword.py`.
- Use D3.js-powered `.htm` files (e.g., `gword.htm`, `gline.htm`) to explore interactive visualizations.

---

## Installation

1. **Clone the Repository**
   ```bash
   git clone https://github.com/yourusername/email-archive-analysis.git
   cd email-archive-analysis
   ```

2. **Setup for Windows (UTF-8 Encoding Issue)**
   For proper Unicode character display, run the following in your command prompt:
   ```bash
   chcp 65001
   ```

---

## Usage

### 1. Spider Email Data
Run the `gmane.py` script to retrieve email messages:
```bash
python3 gmane.py
```

### 2. Process Data
Use `gmodel.py` to clean and compress the raw data:
```bash
python3 gmodel.py
```

### 3. Analyze Data
Run analysis scripts like `gbasic.py` to extract insights:
```bash
python3 gbasic.py
```

### 4. Visualize Data
Generate visualization data and use D3.js to explore results:
- Word Frequency (`gword.py`):
  ```bash
  python3 gword.py
  ```
  Open `gword.htm` in a browser to view the word cloud.
  
- Organization Trends (`gline.py`):
  ```bash
  python3 gline.py
  ```
  Open `gline.htm` in a browser to view participation trends.

---

## Example Outputs

### Top Email Participants
```
steve.swinsburg@gmail.com 2657
azeckoski@unicon.net 1742
ieb@tfd.co.uk 1591
csev@umich.edu 1304
david.horwitz@uct.ac.za 1184
```

### Top Organizations
```
gmail.com 7339
umich.edu 6243
uct.ac.za 2451
indiana.edu 2258
unicon.net 2055
```

---

## Resources

- [Google Charts](https://developers.google.com/chart/)
- [D3.js Calendar Visualization](http://mbostock.github.io/d3/talk/20111018/calendar.html)
- [Natural Language Toolkit (NLTK)](http://nltk.org/install.html)

---

## Acknowledgements

- **Dr. Chuck** for the cached email data and guidance.
- [D3.js](https://d3js.org/) for interactive visualizations.

---

## License

This project is licensed under the MIT License.
