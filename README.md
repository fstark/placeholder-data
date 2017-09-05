# placeholder-data
Placeholder data files for real-world data

A set data files to generate real-world data.

Goal is not to be too fancy or exhaustive, but have a way to generate a some good-looking real-world data for placeholder or anonymization.

When it make sense, lists are in popularity order

## Firstnames

First names extracted from https://www.ssa.gov/OACT/babynames/names.zip

Extracted most popular males and females.

## Names

Names extraced from https://www2.census.gov/topics/genealogy/2010surnames/names.zip

Using tail -n +2 Names_2010Census.csv | head -10000 | cut -f 1 -d , > ../lastnames.txt

## Companies

List of companies from SEC web site https://www.sec.gov/rules/other/4-460list.htm

