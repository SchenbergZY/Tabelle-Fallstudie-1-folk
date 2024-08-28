# 1. Difference between this repository and the origin one
  Please read Readme.md

# 2. Download data without reading Vorwort session in **Lerneinheit R - Arbeiten mit CSV-Dateien**
  Please click https://github.com/SchenbergZY/Tabelle-Fallstudie-1/raw/main/21341-0001_$F.csv to download the table to your computer. And then please upload the downloaded file to Binder or Colab you are running with.

# 3. User Experience of  **Lerneinheit R - Arbeiten mit CSV-Dateien**
## 3.1 2 bugs which happen under Colab/Binder but not happen under Windows command line.
### 3.1.1 Function choose.files()
  This function has no effect running under Colab/Binder when trigger. However in Windows command line, a window will pop out to let you choose a csv file to be loaded.

### 3.1.2 Function edit()
  This function has no effect running under Colab/Binder when trigger. However in Windows command line, a window will pop out to let you edit the dataframe parameter on fly.

## 3.2 Using Experience under Colab
  1. User needs to upload the CSV file
  2. tidyverse pre-installed so just run installing takes a short time
  3. running cell `head(data_csv)` after dataframe loaded takes infinite time as some text in the origin CSV file is not UTF-8 encoded, and user has to stop running the cell. After that user need to rerun `library(tidyverse)` and data_csv read command again. Otherwise there will be other bugs in showing the dataframe loaded
  4. choose.files() not work in Colab
  5. running `?read.csv2` pop up a window at the right side of the webpage
  6. `show(data_csv_3)` not work because nothing called data_csv_3 defined
  7. pandoc pre-installed so just run installing takes a short time
  8. `edit(Tabellendaten)` not work in Colab
## 3.3 Using Experience under Binder
  1. User needs to upload the CSV file
  2. tidyverse not-installed so run installing takes a long time
  3. running cell `head(data_csv)` after dataframe loaded takes long time as some text in the origin CSV file is not UTF-8 encoded, please wait till finished. 
  4. choose.files() not work in Binder
  5. running `?read.csv2` pop up a window at the right side of the webpage
  6. `show(data_csv_3)` not work because nothing called data_csv_3 defined
  7. pandoc not installed so run installing takes a while
  8. `edit(Tabellendaten)` not work in Binder
## 3.4 Using Experience under Live Code
  Waiting for long time with no response.

# 4.  User Experience of  Reproduzierbarkeit Nationaler Bildungsbericht
  1. Convert back to the German-specific letter
  2. left-strip the space of column "Angestelltenverhaeltnis"
  3. Convert column "Personalgruppe" to "Arbeitsverhältnis"

# 5.  User Experience of  **3rd ipynb**
  TBD
