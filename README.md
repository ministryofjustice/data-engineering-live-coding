# Live Coding Component
A colleague has written the below function to take some data on 'stop and search' outcomes and identify which resulted in an arrest and which occurred within the desired timeframe.

Some example search outcome data is also given.

Can you write a test to assess if the function is working as expected?

```python
from datetime import datetime

def find_arrests(search_outcome_data: dict, dates: list) -> dict:
    """
    Takes in search outcome data and a set of dates, and filters the data for arrests within those dates
    """
    
    arrests = {}
    
    for incident_id, incident_data in search_outcome_data.items():
        date = datetime.strptime(incident_data["date"], '%Y-%m-%d')
        
        if incident_data["outcome"] == "arrest" and date in dates:
            arrests[incident] = incident_data
        
    return arrests


example_search_outcome_data = {
    "incident_1": {
        "date": "2024-04-01",
        "outcome": "no_action"
    },
    "incident_2": {
        "date": "2024-05-01",
        "outcome": "arrest"
    },
    "incident_3": {
        "date": "2023-06-01",
        "outcome": "arrest"
    },
    "incident_4": {
        "date": "2024-07-01",
        "outcome": "arrest"
    },
    "incident_5": {
        "date": "2024-07-01",
        "outcome": "arrest"
    }
}
```
