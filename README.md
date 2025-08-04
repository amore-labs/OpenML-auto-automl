# OpenML Auto-AutoML
Welcome to AutoML4All, an initiative to make it easier for anyone to build machine learning models automatically, even without programming experience. We hope that this helps to democratize the use of machine learning for scientists and students across scientific domains. At the moment, this is focused on tabular data  - although the data in the tables can be multimodal (mixtures of numeric values, text, categories, and images).

## How it works

If anyone uploads a dataset to [OpenML](https://openml.org), we perform these steps every 5 hours:  
    - Check if there are new datasets uploaded to OpenML.
    - Identify if there is a [Task](https://openml.github.io/openml-python/main/usage.html#key-concepts), if not, then try to create one based on the target variable and data type of the target column.
    - Once a task is created, summon [amlb](https://github.com/openml/automlbenchmark) and based on the chosen AutoML frameworks, send requests to compute servers.
    - For computation, we are using [Snellius](https://servicedesk.surf.nl/wiki/spaces/WIKI/pages/30660184/Snellius), including GPU resources.
    - Once the frameworks are done running, upload the run results back to OpenML.

## How to use?
- Simply upload a dataset to OpenML and check back in a few hours.
- This service will be available as long as compute credits provided for the Snellius supercomputer are available.

## Developer configuration and contributions
Hello future OpenML developer! So you want to re-run/make a new version of this? Just look at the rest of this documentation.

While the server aspects of this project may be more difficult to contribute to (unless you are an OpenML core developer), most of this project depends on
[the AutoML Benchmark](https://github.com/openml/automlbenchmark), which is very well documented and likely you want to focus on contributions for this library.

## Acknowledgements
This project was supported by the Dutch Scientific Research Fund (NWO) under Open Science Fund grant OSF23.2.109.
