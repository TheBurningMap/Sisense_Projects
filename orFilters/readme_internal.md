# Or Filters
**Author**: Adi Lewenstein  
**Last updated**: Jul 20 2018  
**Plugin Version**: 1.0  
**Last Tested on Version**: 7.1.2  
**Originally Developed for**: Sandpiper Books *(tier 4)*  
**Community Article**:  

## Description
This plugin enables dashbaord designers to apply an OR operator over a group of dashboard filters, rather than the default AND behavior


## Prerequisites
**Supporting Data Model**:  Complex data models (where measures are taken from multiple fact tables) might require a key table.

## Installation
1. Download the plugin
2. Extract the `.zip` file to `C:\Program Files\Sisense\PrismWeb\Plugins`
    - If the folder does not exist, please create it before extracting the `.zip` file.
3. Refresh your dashboard


## Implementation
### Data Model Adjustment:  
The plugin works by removing the selected filters from the filters section of the widgets' JAQLs and adding them as alternative *attributes* of another field. When that filtered field is the fact table's primary key, the records that would be fetched from that same fact table are the ones meeting *either one* of the selected filters, thus meeting the OR operation.

* If the dashbaord contains measures from multiple fact tables, you will not be able to choose a PK from only one of those facts, as it might create Many to Many issues. Instead, you should consider creating a key table to   
* If your dashbaord only queries a single fact table, the model should not require any modification  


### Activation  
Add the following dashboard script to the dashbaords on which you want to enable the OR operation:




## Limitations