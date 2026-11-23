# daml-assignment1: 

## Paintings in the Rijksmuseum's Gallery of Honour

### The dataset
This dataset contains records and images of paintings displayed in the Gallery of Honour at the Rijksmuseum. Each item represents one painting, resulting in a total of 42 items.

### Motivation
The Gallery of Honour displays selected masterpieces by 17th-century artists and leads to *The Night Watch* by Rembrandt van Rijn. This dataset can be used to explore the chronological distribution of the paintings and the representation of different artists.

### Selection criteria
All paintings displayed in the Gallery of Honour were included, except for *De Gouden Leeuw op het IJ voor Amsterdam* by Willem van de Velde (II), dating from 1686, because no digital image was available.

### Data collection
The records and images were collected from the Rijksmuseum's online collection catalogue. The paintings were identified through the 'On Display in Gallery of Honour' label on the collection pages.

### Cleaning and preprocessing
The downloaded images were resized because the original files were too large to work with efficiently.

### Structure
The repository contains the following files and folders:

|---|---|
| `data/` | Folder containing the resized images of the 42 paintings. |
| `metadata.csv` | Final dataset containing the metadata for each painting. |
| `metadata_draft.csv` | Draft metadata used to prepare the final dataset. |
| `prepare_dataset.ipynb` | Notebook used to prepare the final dataset from metadata_draft.csv. |
| `check_dataset.ipynb` | Notebook used to inspect and validate the final dataset, metadata.csv. |
| `requirements.txt` | Lists the Python packages required to run the notebooks. |
| `.gitignore` | Specifies which files are excluded from version control. |
| `README.md` | Describes the dataset, its collection process, structure and limitations. |

#### Codebook of variables in metadata.csv

| Variable | Description | Type | Allowed values / missing values |
|---|---|---|---|
| `id` | Unique Rijksmuseum object identification code | String | Rijksmuseum object ID format, e.g. `SK-A-4118`; empty if unknown |
| `file` | Relative file path to the corresponding artwork image | String | Path format: `data/filename.jpg`; empty if unavailable |
| `title` | Title of the artwork as provided by the Rijksmuseum | String | Text; empty if unknown |
| `artist` | Name of the artist who created the artwork | String | Text; empty if unknown |
| `original_date` | Original date or estimated date of creation as provided by the Rijksmuseum | String | Original date notation, e.g. `1655`, `c. 1653`, or `c. 1653 - 1657`; empty if unknown |
| `earliest_date` | Earliest possible year of creation, extracted from the original date | Integer | Four-digit year; empty if unknown |
| `latest_date` | Latest possible year of creation, extracted from the original date | Integer | Four-digit year; empty if unknown |
| `source` | URL of the Rijksmuseum collection page for the artwork | String | Valid URL; empty if unavailable |
| `licence` | Copyright or usage licence assigned to the artwork image | Categorical | `Public Domain`; empty if unknown |

### Uses and limitations
The dataset can be used to explore the chronological distribution of paintings, compare artists and make visual comparisons. However, it contains only 42 paintings and is not representative of the entire Rijksmuseum collection or Dutch painting in the 17th century. Some production dates are estimates rather than exact dates.

### Ethical and legal aspects
All 42 paintings are marked with the Creative Commons Public Domain Mark (PDM 1.0) by the Rijksmuseum. The dataset contains no personal information.

### Licence and citation
The dataset is shared under the Creative Commons Zero (CC0 1.0) Public Domain Dedication. Users are encouraged to cite the dataset as follows:

Sikma, J. (2026). *Paintings in the Rijksmuseum's Gallery of Honour* [Dataset].

### Sources and references

- [Rijksmuseum collection catalogue](https://www.rijksmuseum.nl/en/collection)
- [Creative Commons Public Domain Mark 1.0](https://creativecommons.org/publicdomain/mark/1.0/)
- [Creative Commons CC0 1.0](https://creativecommons.org/publicdomain/zero/1.0/)
