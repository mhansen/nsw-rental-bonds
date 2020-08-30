# nsw-rental-bonds

Converting monthly Excel Spreadsheet NSW Rental bond lodgment data into single
data file (for export to BigQuery), for [visualising in Data Studio][dashboard].

We source data from [Fair Trading NSW's monthly rental lodgement
spreadshets][fairtrading], [licensed under Creative Commons
Attribution][datagov].

The trouble is this data is in one Excel (xlsx) spreadsheet per month, but I'd
like to visualise the data:

- in Data Studio, which doesn't connect directly to Excel.
- for all time, not just a single month.

## Install Dependencies

```
$ pip3 install jupyter pandas pyarrow xlrd
```

## Steps

1. Download all the [monthly lodgment spreadsheets from Fair
   Trading][fairtrading]. I just manually click all the links in my browser,
   and they're all downloaded to my Downloads folder.
2. Move the downloaded spreadsheets to the `xlsx` directory in this repository.
3. Run `jupyter notebook` and open `convert-spreadsheets.ipynb`
4. Run all the cells
5. You will have a single dataframe, exported to JSONL and Parquet format in
   your working directory.

[fairtrading]: https://www.fairtrading.nsw.gov.au/about-fair-trading/data-and-statistics/rental-bond-data
[datagov]: https://data.nsw.gov.au/data/dataset/rental-bond-lodgement/resource/6dc55389-f014-40b5-979d-369f462076fe
[dashboard]: https://datastudio.google.com/u/0/reporting/e7cd38d9-42ca-42d0-9791-4757dabd52c0/page/XBrdB
