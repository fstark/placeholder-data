# placeholder-data
Placeholder data files for real-world data

A set data files to generate real-world data.

Goal is not to be too fancy or exhaustive, but have a way to generate a some good-looking real-world data for placeholder or anonymization.

When it make sense, lists are in popularity order.

Stats:

   947 companynames.txt
  1918 firstnames-female.txt
  1540 firstnames-male.txt
 10000 lastnames.txt

## Firstnames

Most popular first names extracted from https://www.ssa.gov/OACT/babynames/names.zip with the script:

	#!/bin/bash

	echo > /tmp/$$.txt

	for i in $( ls *.txt ); do
		grep ',F' $i | head -500 | cut -f 1 -d , >> /tmp/F-$$.txt
		grep ',M' $i | head -500 | cut -f 1 -d , >> /tmp/M-$$.txt
	done

	sort -u /tmp/F-$$.txt > ../firstnames-female.txt
	sort -u /tmp/M-$$.txt > ../firstnames-male.txt

	rm -f /tmp/F-$$.txt
	rm -f /tmp/M-$$.txt

## Names

Names extraced from https://www2.census.gov/topics/genealogy/2010surnames/names.zip using:

    tail -n +2 Names_2010Census.csv | head -10000 | cut -f 1 -d , > lastnames.txt

## Companies

List of companies from SEC web site https://www.sec.gov/rules/other/4-460list.htm

## Top domains:

List from https://moz.com/top500/domains/csv

Extracted with :

    tail -n +2 top500.domains.08.17.csv | cut -f 2 -d , | sed -e 's/"*\/*//g' > domainnames.txt

