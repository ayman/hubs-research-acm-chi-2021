# Collected Data

## Poses
The dataset provided with this example has already been assigned
usable names for columns and removed all unused columns. Columns, like
`display_name`, have been removed for anonymisation. The raw data from
the updated logging code will have different column names and more
columns than seen here.  For reference, here is our format.

| Column          | Description                                                                    |
| :-------------  | :----------------------------------------------------------------------------- |
| `timestamp`     | Events timestamp                                                               |
| `uuid`          | Stable unique ID for users                                                     |
| `states`        | Hubs tags for user state within room                                           |
| `room`          | Which room, although room names inconsistenly use / and can include subscreens |
| `position_x`    | Coordinates vary based on size of room                                         |
| `position_y`    | Height (typically 1, unless using fly mode)                                    |
| `position_z`    | Coordinates vary based on size of room                                         |
| `direction_x`   | A vector, value from -1 to 1                                                   |
| `direction_y`   | A vector, value from -1 to 1                                                   |
| `direction_z`   | A vector, value from -1 to 1                                                   |
| `orientation_w` | A quaternion, a value from 0 to 1                                              |
| `orientation_x` | A quaternion, a value from -1 to 1                                             |
| `orientation_y` | A quaternion, a value from -1 to 1                                             |
| `orientation_z` | A quaternion, a value set to 0                                                 |

## User Events Summary

| Column       | Description                 |
| :----------- | :-------------------------- |
| `uuid`       | Stable unique ID for users  |
| `os`         | User's Operating System     |
| `vr_enabled` | HMD status                  |

## License
The *data* is released under [CC-BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/).
