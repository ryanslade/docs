## Load financial data
This tutorial uses real-time cryptocurrency data, also known as tick data, from
[Twelve Data][twelve-data].

### Ingest the dataset
To ingest data into the tables that you created, you need to download the
dataset and copy the data to your database.

<procedure>

#### Ingesting the dataset

1.  Download the `crypto_sample.zip` file. The file contains two `.csv`
    files; one with company information, and one with real-time stock trades for
    the past month. Download:
    <tag
    type="download">[crypto_sample.zip](https://assets.timescale.com/docs/downloads/candlestick/crypto_sample.zip)
    </tag>

1.  In a new terminal window, run this command to unzip the `.csv` files:

    ```bash
    unzip crypto_sample.zip
    ```

1.  At the `psql` prompt, use the `COPY` command to transfer data into your
    TimescaleDB instance. If the `.csv` files aren't in your current directory,
    specify the file paths in these commands:

    ```sql
    \COPY crypto_ticks FROM 'tutorial_sample_tick.csv' CSV HEADER;
    ```

    ```sql
    \COPY crypto_assets FROM 'tutorial_sample_assets.csv' CSV HEADER;
    ```

    Because there are millions of rows of data, the `COPY` process could take a
    few minutes depending on your internet connection and local client
    resources.

</procedure>

[twelve-data]: https://twelvedata.com/