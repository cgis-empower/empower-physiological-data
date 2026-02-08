# empower-physiological-data

Anonymised physiological data recorded in the EMPOWER European project: https://project-empower.eu

This dataset includes the physiological data recorded in three pilot sessions and a two weeks RCT trial, implemented between 2023 and 2025.

## Dataset important information:

- There are no duplicate participants in any of the datasets. Each participant has been recorded only once.
- The identifiers are **unique** and **consistent** only in the contenxt of a set (ex. pilot 1). Same identifier in Pilot 1 and Pilot 2 are indicating a different resources
- For each participant (id_student) there have been one or multiple sessions (id_session) which contained one or multiple activities (id_activity)

## Known issues

- Due to some technical issues, during Pilot 2 no accelerometer data has been recorded
- Constrained by some sensor SDK updates, we needed to change the structure of the IBI recorded data after Pilot 2
- In Pilot 3, for comparison reasons, we have included the legacy data recording approach (used in Pilot 1) in the fields labeled with _\_depr_ suffix

## Acknowledgement

The acquiring of this data and the research leading to these results have been carried out in the "EMPOWER. Design and evaluation of technological support tools to empower stakeholders in digital education" project, which has received funding from the European Union's Horizon Europe programme, under grant agreement No 101060918. Views and opinions expressed are however those of the authors(s) only and do not necessarily reflect those of the European Union. Neither the European Union nor the granting authority can be held responsible for them.

## More details

For more details on this dataset, please reach out to: teodor.stefanu[at]cs.utcluj.ro
