# empower-physiological-data

Anonymised physiological data recorded in the EMPOWER European project: https://project-empower.eu

This dataset includes the physiological data recorded in three pilot sessions and a two weeks RCT trial, implemented between 2023 and 2025.

## Dataset important information:

- This dataset is split into units: _pilot 1_, _pilot 2_, _pilot 3_ and _rct_
- As will be obvious from the timestamps, the units are in chronological order: _pilot 1_ (summer 2023), _pilot 2_ (spring 2024), _pilot 3_ (fall 2024) and _rct_ (spring 2025)
- There are no duplicate participants in any of units. Each participant has been recorded only once.
- The identifiers are **unique** and **consistent** only in the context of a unit (ex. _pilot 1_, _pilot 2_). Same identifier in _pilot 1_ and _pilot 2_ are indicating a different resource (participant, session, activity)
- For each participant (id_student) there have been one or multiple sessions (id_session) which contained one or multiple activities (id_activity)
- Benefiting from sensor SDK updates, we have changed the structure of the IBI recorded data after _pilot 2_, for finer granularity. In _pilot 1_, we had one agregated value / second. From _pilot 2_, we have been able to read up to 5 values each second
- In _pilot 3_, for comparison reasons, we have included the agregated value used in _pilot 1_, in the fields labeled with _\_depr_ suffix

## Known issues

- Due to some technical issues, during Pilot 2 no accelerometer data has been recorded

## Data structure

The files in the dataset have the following structure:

### Accelerometer files

- **timestamp** - Epoch Unix Timestamp in UTC, measured in milliseconds
- **id_student** - identifier of the participant; unique and consistent only in the context of a unit (ex. _pilot 1_, _pilot 2_)
- **id_session** - identifier of the recording session; unique and consistent only in the context of a unit (ex. _pilot 1_, _pilot 2_); _NULL_ values indicate moments between sessions, when participant still wore the sensor
- **id_activity** - identifier of the recording activity; unique and consistent only in the context of a unit (ex. _pilot 1_, _pilot 2_); _NULL_ values indicate moments between activities, when participant still wore the sensor
- **value_x, value_y, value_z** - the values recorded from the accelerometer

### Heart activity files

- **timestamp** - Epoch Unix Timestamp in UTC, measured in milliseconds
- **id_student** - identifier of the participant; unique and consistent only in the context of a unit (ex. _pilot 1_, _pilot 2_)
- **id_session** - identifier of the recording session; unique and consistent only in the context of a unit (ex. _pilot 1_, _pilot 2_); _NULL_ values indicate moments between sessions, when participant still wore the sensor
- **id_activity** - identifier of the recording activity; unique and consistent only in the context of a unit (ex. _pilot 1_, _pilot 2_); _NULL_ values indicate moments between activities, when participant still wore the sensor
- **value_heart_rate** - value recorded for the heart rate
- **status_heart_rate** - indicates the quality of the **value_heart_rate**; 10 = valid value; _anything else_ = invalid value
- **value_ibi** - (only in _pilot 1_) value recorded as in between heart beats interval
- **status_ibi** - (only in _pilot 1_) indicates the quality of the **value_ibi**; 11 = valid value; _anything else_ = invalid value
- **value_ibi\_[0..4]** - (from _pilot 2_) value recorded as in between heart beats interval, with better granularity than in _pilot 1_
- **status_ibi\_[0..4]** - (from _pilot 2_) indicates the quality of the **value_ibi\_[0..4]**; 11 = valid value; _anything else_ = invalid value
- **value_ibi_depr** - (from _pilot 3_) value recorded as in between heart beats interval, using the agregated algorithm from _pilot 1_
- **status_ibi_depr** - (from _pilot 3_) indicates the quality of the **value_ibi_depr**; 11 = valid value; _anything else_ = invalid value

## How to use this dataset

The files included in the dataset are in CSV format, each of them being archived as a ZIP for compliance with GitHub maximum file size limit.

The structure of the files has been presented above. After download and decompression, you can process the CSV files with any programming language (Python, .NET, etc.), or even with Excel or similar applications (only files with less than 100.000 records) to compute Heart Rate Variability related indices or to process movement amplitude.

Based on the available identifiers, data will provide at least information on activity vs rest physiological response.

## Acknowledgement

The acquiring of this data and the research leading to these results have been carried out in the "EMPOWER. Design and evaluation of technological support tools to empower stakeholders in digital education" project, which has received funding from the European Union's Horizon Europe programme, under grant agreement No 101060918. Views and opinions expressed are however those of the authors(s) only and do not necessarily reflect those of the European Union. Neither the European Union nor the granting authority can be held responsible for them.

## More details

For more details on this dataset, please reach out to: teodor.stefanut[at]cs.utcluj.ro
