# How to Create a New Draft Charts Post

This guide explains how to create a new NFL Draft prospects chart post. There are two methods: an automated script (recommended) and a manual process.

## Method 1: Automated Script (Recommended)

The easiest way to create a new draft post is using the `create-draft-post.sh` script.

### Prerequisites

You need two CSV files with your draft data, named with today's date:

1. **YYYY-MM-DD-ranks.csv** - Individual player rankings
   - Format: `Rank,Overall,Player,School,Position,Date,,,State,Conference,Points`
   - Example: `1,1,Rueben Bain,Miami (FL),EDGE,2025-11-23,,,Florida,ACC,35`

2. **YYYY-MM-DD-top-schools.csv** - School aggregated data
   - Format: `School,Conference,ProjectedPoints,NumberOfProspects`
   - Example: `Ohio State,Big Ten,230,29`

### Steps

1. **Prepare your CSV files** with the date in the filename (e.g., `2025-12-10-ranks.csv` and `2025-12-10-top-schools.csv`)

2. **Copy the CSV files to the blog root directory**:
   ```bash
   cp /path/to/2025-12-10-ranks.csv .
   cp /path/to/2025-12-10-top-schools.csv .
   ```

3. **Run the script**:
   ```bash
   ./create-draft-post.sh 2026 "2026 Draft Prospects"
   ```

   Arguments:
   - First argument: Draft year (e.g., `2026`)
   - Second argument: Draft name (e.g., `"2026 Draft Prospects"`)

4. **The script automatically**:
   - Extracts the date from your CSV filenames
   - Creates the `static/data/YYYY-MM-DD/` directory
   - Moves the CSV files to the data directory
   - Creates a new numbered post (e.g., `nfl-draft-prospects-2026-04.md`)
   - Generates all chart shortcodes with correct paths
   - Fills in the title, date, and methodology section

5. **Preview your post**:
   ```bash
   hugodev
   ```

That's it! The post is ready to go.

---

## Method 2: Manual Process (Alternative)

If you prefer to create posts manually or need more control, follow these steps.

### Prerequisites

You need two CSV files with your draft data:
1. **ranks.csv** - Individual player rankings (without headers)
2. **top-schools.csv** - School aggregated data (with headers)

## Step 1: Prepare Your CSV Files

### ranks.csv format (no header row):
```
Index,Rank,PlayerName,School,Position,Date,,,State,Conference,Points
1,1,Player Name,School Name,QB,2026-03-15,,,State Name,Conference Name,35
```

**Required columns (0-indexed):**
- Column 0: Index
- Column 1: Rank
- Column 2: Player name
- Column 3: School
- Column 4: Position
- Column 5: Date
- Column 8: State
- Column 9: Conference
- Column 10: Points

### top-schools.csv format (with headers):
```
School,Conference,ProjectedPoints,NumberOfProspects
Penn State,Big Ten,183,28
```

**Required columns:**
- School
- Conference
- ProjectedPoints
- NumberOfProspects

## Step 2: Choose a Date Format

Pick a date for your data snapshot (format: YYYY-MM-DD), for example: `2026-03-15`

## Step 3: Create the Directory Structure

Create a folder in `static/data/` with your date:

```bash
mkdir -p static/data/2026-03-15
```

## Step 4: Copy Your CSV Files

Copy your CSV files to the data directory with the proper naming:

```bash
cp /path/to/your/ranks.csv static/data/2026-03-15/2026-03-15-ranks.csv
cp /path/to/your/schools.csv static/data/2026-03-15/2026-03-15-top-schools.csv
```

## Step 5: Create the Post Using the Archetype

Run Hugo's new command with the draft-charts archetype:

```bash
hugo new charts/nfl-draft-prospects-2026-01.md --kind draft-charts
```

This creates: `content/charts/nfl-draft-prospects-2026-01.md`

## Step 6: Update the CSV Paths

Open the newly created file and replace all instances of `DATE-HERE` with your actual date:

**Find:** `DATE-HERE`
**Replace with:** `2026-03-15`

There should be 8 replacements total (2 per chart × 4 charts).

### Example before:
```markdown
{{< obsplot-stacked csv="/data/DATE-HERE/DATE-HERE-ranks.csv" ... >}}
```

### Example after:
```markdown
{{< obsplot-stacked csv="/data/2026-03-15/2026-03-15-ranks.csv" ... >}}
```

## Step 7: Update the Title and Date (Optional)

The archetype will auto-generate a title and date, but you can customize them:

```toml
+++
title = "2026 NFL Draft Prospects as of March 15"
date = 2026-03-15T12:00:00Z
tags = ["draft", "charts", "prospects"]
featured_image = ""
description = "Interactive charts showing 2026 NFL Draft prospect data by school, state, conference, and position"
+++
```

## Step 8: Preview Your Charts

Start the Hugo development server:

```bash
hugodev
```

Navigate to your new post: `http://localhost:1313/charts/nfl-draft-prospects-2026-01/`

## Step 9: Verify the Charts

Check that all four charts display correctly:
1. ✅ Player Value by School
2. ✅ Player Value by State
3. ✅ Schools by Conference
4. ✅ Position Distribution by Conference

Hover over segments to verify tooltips show correct data.

## Troubleshooting

### Charts show but no data bars
- Check that CSV files are in the correct location
- Verify CSV file names match the paths in the markdown exactly
- Check browser console for errors

### Blank spaces in charts
- A conference might be missing from the color domain
- Check that all conferences in your data are listed in `obsplot-stacked.html`
- Currently supported: SEC, Big Ten, ACC, Big 12, Pac 12, FBS conferences, FCS, D2, D3

### Tooltip shows "undefined"
- For player charts: Check that ranks.csv has all required columns
- For school charts: Check that top-schools.csv has headers and required columns

### Browser cache issues
If changes don't appear after editing:
1. Hard refresh: Ctrl+Shift+R (or Cmd+Shift+R on Mac)
2. Open in incognito/private window
3. Stop Hugo server, restart, open new incognito window

## File Locations Reference

```
blog/
├── archetypes/
│   └── draft-charts.md              # Template for new posts
├── content/
│   └── charts/
│       └── nfl-draft-prospects-2026-01.md  # Your new post
├── layouts/
│   └── shortcodes/
│       ├── obsplot-stacked.html     # Stacked charts with conference colors
│       └── obsplot-stacked-auto.html # Stacked charts with auto colors
└── static/
    └── data/
        └── 2026-03-15/
            ├── 2026-03-15-ranks.csv
            └── 2026-03-15-top-schools.csv
```

## Quick Reference Commands

### Using the Script (Recommended)

```bash
# 1. Copy CSV files to blog root (files must be named YYYY-MM-DD-ranks.csv and YYYY-MM-DD-top-schools.csv)
cp /path/to/2025-12-10-ranks.csv .
cp /path/to/2025-12-10-top-schools.csv .

# 2. Run the script
./create-draft-post.sh 2026 "2026 Draft Prospects"

# 3. Preview
hugodev
```

### Manual Method

```bash
# Create data directory
mkdir -p static/data/YYYY-MM-DD

# Copy CSV files
cp ranks.csv static/data/YYYY-MM-DD/YYYY-MM-DD-ranks.csv
cp schools.csv static/data/YYYY-MM-DD/YYYY-MM-DD-top-schools.csv

# Create new post
hugo new charts/nfl-draft-prospects-YYYY-NN.md --kind draft-charts

# Start dev server
hugodev
```

Replace `YYYY-MM-DD` with your date and `NN` with a sequential number (01, 02, etc.).
