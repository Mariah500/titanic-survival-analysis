# titanic-survival-analysis
# Titanic Exploratory Data Analysis

Exploratory data analysis on the Titanic passenger dataset (Kaggle), 
examining what factors were associated with higher survival odds.

Roadmap project: [PASTE YOUR COPIED PROJECT URL HERE]

## Question
What kind of passengers were more likely to survive?

## Technologies Used
- Python
- Pandas
- Matplotlib / Seaborn
- Jupyter Notebook

## 1. Data Inspection
The dataset contains 891 passengers and 12 columns. Key missing data:
- `Age`: 177 missing values (714 non-null)
- `Cabin`: 687 missing values (204 non-null)
- `Embarked`: 2 missing values

## 2. Survival Rates by Group

**By Sex**
| Sex | Survival Rate |
|--------|---------------|
| Female | 74.2% |
| Male | 18.9% |

Survival was strongly linked to gender: women had a survival rate of 
about 74%, compared to only 19% for men. This is one of the clearest 
patterns in the dataset and is consistent with a "women and children 
first" evacuation policy.

**By Passenger Class**
| Pclass | Survival Rate |
|--------|---------------|
| 1 | 63.0% |
| 2 | 47.3% |
| 3 | 24.2% |

Passenger class had a clear relationship with survival, dropping 
steadily from 1st to 3rd class. The raw counts show most deaths came 
from 3rd class, but this is partly because 3rd class had far more 
passengers overall (~500) than 1st class (~220). Looking at the rate 
rather than the count shows individual odds, not just group size, 
were also worse in 3rd class.

**By Age Group**
| Age Group | Survival Rate |
|-----------|---------------|
| Child | 58.0% |
| Teen | 42.9% |
| Adult | 36.0% |
| MidAge | 39.0% |
| Senior | 22.7% |

**By Sex and Class Combined**
| Sex | Pclass | Survival Rate |
|--------|--------|---------------|
| Female | 1 | 96.8% |
| Female | 2 | 92.1% |
| Female | 3 | 50.0% |
| Male | 1 | 36.9% |
| Male | 2 | 15.7% |
| Male | 3 | 13.5% |

Combining gender and class reveals the starkest gap in the dataset: 
1st class women had a survival rate of about 97%, while 3rd class men 
had a survival rate of only 14%. This suggests survival depended 
heavily on both factors working together, not just one alone.

## 3. Visualizations

**Survival Count by Sex** — bar chart comparing raw survivor/non-survivor 
counts for male vs female passengers. Most men did not survive, while 
most women did — the clearest single pattern in the dataset.

**Survival Count by Class** — bar chart comparing raw survivor/non-survivor 
counts across 1st, 2nd, and 3rd class.

**Age Distribution by Survival (raw counts)** — histogram of passenger 
age, split by survival. Most passengers were between 20 and 30 years 
old, so this group also has the highest raw death count. However, the 
0–5 age bracket is the only range where survivors outnumber 
non-survivors, showing that young children were prioritized during 
evacuation despite being a small group overall.

**Age Distribution by Survival (relative frequency)** — same chart 
normalized as density instead of raw counts, so survivors and 
non-survivors can be compared shape-for-shape regardless of their very 
different group sizes (342 survivors vs 549 non-survivors). When 
compared as proportions, survivors are relatively more concentrated 
in the youngest age groups than non-survivors — a pattern that was 
harder to see in the raw-count version.

## Key Takeaway
Survival on the Titanic was not random. Sex, passenger class, and age 
all show consistent, meaningful relationships with survival — women, 
1st class passengers, and children had substantially better odds. 
Comparing relative frequencies rather than raw counts is essential 
here, since the passenger groups differ significantly in size (e.g. 
far more men than women, far more 3rd class than 1st).
