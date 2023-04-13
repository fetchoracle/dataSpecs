# Fetch Data Specifications


This repository contains specifications of data requested from, reported to, and retrieved from Fetch oracles. Each specification is called a `Query`.

- [For Fetch Users](#for-fetch-users)
- [For Fetch Reporters](#for-fetch-reporters)
- [Create new Query type](#create-new-query-type)

## For Fetch Users:

### **Price data**:
First check if the price data is already being reported [here](https://github.com/fetchoracle/telliot-feeds/tree/main/src/telliot_feeds/feeds). If it is not, [please fill this out.](https://github.com/fetchoracle/telliot-feeds/issues/new/choose)

Need a spot price from Fetch? Generate a unique identifier, or query ID, for the `asset/currency` pair using [this tool](https://queryidbuilder.herokuapp.com/). After, use that ID to [pay reporters](https://github.com/fetchoracle/autoPay) to put that data on-chain. Then retrieve the reported spot price from the oracle [like this](https://docs.fetch.io/fetch/getting-data/introduction).

### **Custom data**:
First, check in [`/types`](./types/) if there's already a query type that defines the data you need.

If not, [create a new query type](#create-new-query-type), [pay reporters](https://github.com/fetchoracle/autoPay) to put that data on-chain, and retrieve that data from a Fetch oracle [like this](https://docs.fetch.io/fetch/getting-data/introduction).

## For Fetch Reporters:
To find out what data to report, there's two options:
- Use our [reporter client](https://github.com/fetchoracle/telliot-feed-examples) to automatically report the expected response of queries that Fetch users are funding.
- Check for newly funded queries, then refer to that query's expected response in [`/types`](./types/) for the required data to report. Be sure to read the dispute considerations section for that query.


## Create New Query Type
To create a new Query, or specification, for custom data you need from Fetch oracles, there's two options:
- Make an issue with [this template](https://github.com/fetchoracle/dataSpecs/issues/new?assignees=&labels=&template=new_query_type.yaml&title=%5BNew+Query+Type%5D%3A+) and the Fetch team will help with the next steps.

After creating the new query type in this repo, [here](https://github.com/fetchoracle/telliot-feeds/issues/new/choose) are some next steps for getting reporters to support your data.


## Contribute<a name="how2contribute"> </a>  
Join our [discord](https://discord.gg/DxSG2bPECw), help us with issues here on Github, or feel free to reach out anytime [info@fetch.io](mailto:info@fetch.io).


## Maintainers <a name="maintainers"> </a> 
This repository is maintained by the [Fetch team](https://github.com/orgs/fetchoracle/people).


## Copyright

Fetch Inc. 2022
