# Day 5 - Text Processing Part 1

## What I Learned
- `cat` — view file contents with line numbers
- `head` — peek at the top of a file
- `tail` — view bottom of file and follow live logs
- `grep` — search and filter data by pattern
- `cut`  — extract specific columns from a file
- `sort` — sort data alphabetically or numerically
- `uniq` — find, count and remove duplicate records

## Why These Commands Matter to a Data Engineer
As a Data Engineer, raw data arrives as messy, unorganized
text files — CSVs, logs, exports. Before writing a single
line of Python or SQL, these terminal commands allow you to:
- Instantly inspect any dataset regardless of size
- Filter specific records without loading into a database
- Detect duplicates before they corrupt your pipeline
- Sort and prepare data for downstream processing
Every DE uses these commands daily on production servers.

## Commands I Practiced

### cat — View File
```bash
cat -n patients.csv        # view with line numbers
cat file1.csv file2.csv    # concatenate two files
```

### head — Top of File
```bash
head patients.csv          # first 10 lines
head -n 1 patients.csv     # header row only
```

### tail — Bottom of File
```bash
tail patients.csv          # last 10 lines
tail -f pipeline.log       # follow live log updates
```

### grep — Search and Filter
```bash
grep "dog" patients.csv        # find matching lines
grep -i "dog" patients.csv     # case insensitive
grep -n "dog" patients.csv     # show line numbers
grep -c "dog" patients.csv     # count matches
grep -v "dog" patients.csv     # exclude pattern
```

### cut — Extract Columns
```bash
cut -d',' -f1 patients.csv     # column 1
cut -d',' -f2,3 patients.csv   # columns 2 and 3
cut -d',' -f2- patients.csv    # column 2 to end
```

### sort — Sort Data
```bash
sort patients.csv                  # alphabetical
sort -r patients.csv               # reverse
sort -n numbers.csv                # numerical
sort -t',' -k3 patients.csv        # sort by column 3
```

### uniq — Find Duplicates
```bash
sort patients.csv | uniq           # remove duplicates
sort patients.csv | uniq -c        # count occurrences
sort patients.csv | uniq -d        # show duplicates only
```

## What I Built
A veterinary patient data inspection pipeline using only
terminal commands — no Python, no SQL, just Linux.

Pipeline steps:
1. Created a messy veterinary CSV dataset (patients.csv)
2. Inspected structure using cat, head, tail and wc
3. Filtered records using grep — dogs vs cats, specific names
4. Extracted specific columns using cut
5. Sorted data by species and weight
6. Detected duplicate records using sort and uniq
7. Generated a full data inspection report saved to report.txt

## Project Structure
day5-linux/
├── patients.csv        # raw veterinary dataset
├── report.txt          # data inspection report
└── README.md           # documentation
## Key Insight from Today
In online tutorials, datasets are always clean and perfectly
formatted. In the real world, raw data is messy, incomplete
and inconsistent. A Data Engineer's job starts before any
analysis — cleaning and preparing data is where the real
work begins.

This is why I am learning this. And why I love it.

## Mistakes I Made & Fixed
| Mistake | What Happened | Fix |
|---|---|---|
| `uniq` without sort first | Missed non-consecutive duplicates | Always `sort \| uniq` |
| `grep "Dog"` with capital D | No results returned | Use `grep -i "dog"` for case insensitive |
| `cut` wrong column number | Got wrong data | Used `head -n 1` first to check structure |

## The Vet Meets Data Engineering Angle
As a veterinarian I have always worked with patient records —
species, weight, treatment history, outcomes. Today I
realized I have been thinking about data my whole career.
The difference is now I am learning to process it at scale.
Cleaning a CSV of 10 million animal health records is just
a larger version of what I did in the clinic every day.
That is my edge.

## My Background
Veterinarian transitioning into Data Engineering.
Currently: ALX Professional Foundations + self-learning Linux.

## Author
**Peter Kamanda** | Veterinarian → Data Engineer in Progress
📍 Nairobi, Kenya | ALX DE Program 

## Resources
 [GitHub Profile](https://github.com/petergetheiba)
