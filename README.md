# EPIC Kitchens 100 Dataset

<!-- start badges -->

<!-- end badges -->

> [EPIC-Kitchens-100](https://epic-kitchens.github.io/) is the largest dataset in first-person (egocentric) vision; itself an extension of the [EPIC-Kitchens-55 dataset](https://github.com/epic-kitchens/annotations) (formally known as EPIC-Kitchens-2018).

## Authors
Dima Damen (1)
Hazel Doughty (1)
Giovanni Maria Farinella (2)
Antonino Furnari (2)
Evangelos Kazakos (1)
Jian Ma (1)
Davide Moltisanti (1)
Jonathan Munro (1)
Toby Perrett (1)
Will Price (1)
Michael Wray (1)

* (1 University of Bristol)
* (2 University of Catania)

**Contact:** [uob-epic-kitchens2018@bristol.ac.uk](mailto:uob-epic-kitchens2018@bristol.ac.uk) <!-- TODO, should this be changed/renamed? -->

## Citing
When using the dataset, kindly reference:

TBA

## Dataset Details
The EPIC-Kitchens-100 dataset is an extension of the EPIC-Kitchens-55 dataset. Videos are distinguished as follows:

* `PXX_YY.MP4` videos originate from EPIC-Kitchens-55.
* `PXX_1YY.MP4` videos originate from the extension collected for EPIC-Kitchens-100 (thus represent new videos).



The dataset currently has 6 active benchmarks:

* Action Recognition
* Weakly Supervised Action Recognition
* Action Detection
* Action Anticipation
* Unsupervised Domain Adaptation
* Action Retrieval

We provide csv files for the train/val/test sets of each benchmark detailed below for ease of use.

Ground truth is provided for action segments as action/verb/noun labels along with the start and end times of the segment.


## Quick Start

Here you can download the annotation files for all of the challenges. For more information on each challenge, please see the paper [here]().
Download scripts are provided for the videos, RGB Frames and Flow frames [here](https://github.com/epic-kitchens/download-scripts-100).

### Action Recognition Challenge
Download the Action Recognition [train](EPIC_100_train.csv)/[val](EPIC_100_val.csv)/[test](EPIC_100_test.csv) files.

### Weakly Supervised Action Recognition Challenge
This challenge uses the Action Recognition files, download the [train](EPIC_100_train.csv)/[val](EPIC_100_val.csv)/[test](EPIC_100_test.csv) files.

### Action Detection Challenge
This challenge uses the Action Recognition files, download the [train](EPIC_100_train.csv)/[val](EPIC_100_val.csv)/[test](EPIC_100_test.csv) files.

### Action Anticipation Challenge
This challenge uses the Action Recognition files, download the [train](EPIC_100_train.csv)/[val](EPIC_100_val.csv)/[test](EPIC_100_test.csv) files.

### Unsupervised Domain Adaptation Challenge
Download the Unsupervised Domain Adaptation [source train]()/[target train]()/[target test]() files.

### Action Retrieval Challenge
Download the Action Retrieval [train]()/[test]() files.


## Important Files

We direct the reader to [RDSF](https://data.bris.ac.uk/data/dataset/2g1n6qdydwa9u22shpxqzp0t8m) for the videos and RGB/Flow frames. For ease of use, download scripts are [provided](https://github.com/epic-kitchens/download-scripts-100) (see [file downloads](#file-downloads) for more details).
We provide html and pdf alternatives to this README which are auto-generated.

* `README.md (this file)`
* `README.pdf`
* `README.html`
* [`license.txt`](#license)
* [`EPIC_100_train.csv`](EPIC_100_train.csv) ([info](#epic_100_traincsv)) ([Pickle](EPIC_100_train.pkl))
* [`EPIC_100_validation.csv`](EPIC_100_validation.csv) ([info](#epic_100_validationcsv)) ([Pickle](EPIC_100_validation.pkl))
* [`EPIC_100_test_timestamps.csv`](EPIC_100_test_timestamps.csv) ([info](#epic_100_test_timestampscsv)) ([Pickle](EPIC_100_test_timestamps.pkl))
* [`EPIC_100_noun_classes.csv`](EPIC_100_noun_classes.csv`) ([info](#epic_100_noun_classescsv))
* [`EPIC_100_verb_classes.csv`](EPIC_100_verb_classes.csv`) ([info](#epic_100_verb_classescsv))

### Additional Files

* [`EPIC_100_UDA_source_train`](EPIC_100_UDA_source_train.csv) ([info](#epic_100_UDA_source_traincsv)) ([Pickle](epic_100_source_train.pkl))
* [`EPIC_100_UDA_target_train_timestamps`](EPIC_100_UDA_target_train_timestamps.csv) ([info](#epic_100_UDA_target_train_timestampscsv)) ([Pickle](epic_100_target_train_timestamps.pkl))
* [`EPIC_100_UDA_target_test_timestamps`](EPIC_100_UDA_target_test_timestamps.csv) ([info](#epic_100_UDA_target_test_timestampscsv)) ([Pickle](epic_100_target_test_timestamps.pkl))
* [`EPIC_100_retrieval_train`](EPIC_100_retrieval_train.csv) ([info](#epic_100_retrieval_traincsv)) ([Pickle](epic_100_retrieval_train.pkl))
* [`EPIC_100_retrieval_test`](EPIC_100_retrieval_test.csv) ([info](#epic_100_retrieval_testcsv)) ([Pickle](epic_100_retrieval_test.pkl))

## File Structure

#### EPIC_100_train.csv

This CSV file contains the action annotations for the training set and contains 15 columns:

| Column Name           | Type                       | Example        | Description                                                                   |
| --------------------- | -------------------------- | -------------- | ----------------------------------------------------------------------------- |
| `uid`                 | int                        | `0`            | Unique ID for the segment as an int.                                          |
| `narration_id`        | string                     | `P01_01_0`     | Unique ID for the segment as a string with participant ID and video ID.       |
| `participant_id`      | int                        | `P01`          | ID of the participant (unique per participant).                               |
| `video_id`            | string                     | `P01_01`       | ID of the video where the segment originated from (unique per video).         |
| `narration_timestamp` | string                     | `00:00:01.089` | Timestamp of when the original narration was recorded in `HH:mm:ss.SSS`.      |
| `start_timestamp`     | string                     | `00:00:00.14`  | Start time in `HH:mm:ss.SS` of the action segment.                            |
| `stop_timestamp`      | string                     | `00:00:03.37`  | End time in `HH:mm:ss.SS` of the action segment.                              |
| `start_frame`         | int                        | `8`            | Start frame of the action.                                                    |
| `stop_frame`          | int                        | `202`          | End frame of the action.                                                      |
| `narration`           | string                     | `open door`    | Transcribed description of the English narration provided by the participant. |
| `verb`                | string                     | `open`         | Parsed verb from the narration.                                               |
| `verb_class`          | int                        | `3`            | Numeric ID of the verb's class.                                               |
| `noun`                | string                     | `door`         | First parsed noun from the narration.                                         |
| `noun_class`          | int                        | `3`            | Numeric ID of the first noun's class.                                         |
| `all_nouns`           | list of string (1 or more) | `[door]`       | List of all parsed nouns within the narration.                                |
| `all_noun_classes`    | list of int (1 or more)    | `[3]`          | Numeric ID of all of the parsed noun's classes.                               |

[Back to Important Files](#important-files)


#### EPIC_100_validation.csv

This CSV file contains the action annotations for the validation set and contains 15 columns:

| Column Name           | Type                       | Example        | Description                                                                   |
| --------------------- | -------------------------- | -------------- | ----------------------------------------------------------------------------- |
| `uid`                 | int                        | `4972`         | Unique ID for the segment as an int.                                          |
| `narration_id`        | string                     | `P01_01_11`    | Unique ID for the segment as a string with participant ID and video ID.       |
| `participant_id`      | int                        | `P01`          | ID of the participant (unique per participant).                               |
| `video_id`            | string                     | `P01_11`       | ID of the video where the segment originated from (unique per video).         |
| `narration_timestamp` | string                     | `00:00:00.560` | Timestamp of when the original narration was recorded in `HH:mm:ss.SSS`.      |
| `start_timestamp`     | string                     | `00:00:00.00`  | Start time in `HH:mm:ss.SS` of the action segment.                            |
| `stop_timestamp`      | string                     | `00:00:01.89`  | End time in `HH:mm:ss.SS` of the action segment.                              |
| `start_frame`         | int                        | `1`            | Start frame of the action.                                                    |
| `stop_frame`          | int                        | `113`          | End frame of the action.                                                      |
| `narration`           | string                     | `take plate`   | Transcribed description of the English narration provided by the participant. |
| `verb`                | string                     | `take`         | Parsed verb from the narration.                                               |
| `verb_class`          | int                        | `0`            | Numeric ID of the verb's class.                                               |
| `noun`                | string                     | `plate`        | First parsed noun from the narration.                                         |
| `noun_class`          | int                        | `2`            | Numeric ID of the first noun's class.                                         |
| `all_nouns`           | list of string (1 or more) | `[plate]`      | List of all parsed nouns within the narration.                                |
| `all_noun_classes`    | list of int (1 or more)    | `[2]`          | Numeric ID of all of the parsed noun's classes.                               |

[Back to Important Files](#important-files)


#### EPIC_100_test_timestamps.csv

This CSV file contains the action annotations for the testing set and contains 9 columns:

| Column Name           | Type                       | Example        | Description                                                                   |
| --------------------- | -------------------------- | -------------- | ----------------------------------------------------------------------------- |
| `uid`                 | int                        | `1924`         | Unique ID for the segment as an int.                                          |
| `narration_id`        | string                     | `P01_101_0`    | Unique ID for the segment as a string with participant ID and video ID.       |
| `participant_id`      | int                        | `P01`          | ID of the participant (unique per participant).                               |
| `video_id`            | string                     | `P01_101`      | ID of the video where the segment originated from (unique per video).         |
| `narration_timestamp` | string                     | `00:00:02.851` | Timestamp of when the original narration was recorded in `HH:mm:ss.SSS`.      |
| `start_timestamp`     | string                     | `00:00:02.86`  | Start time in `HH:mm:ss.SSS` of the action segment.                           |
| `stop_timestamp`      | string                     | `00:00:03.87`  | End time in `HH:mm:ss.SSS` of the action segment.                             |
| `start_frame`         | int                        | `143`          | Start frame of the action.                                                    |
| `stop_frame`          | int                        | `193`          | End frame of the action.                                                      |

[Back to Important Files](#important-files)


#### EPIC_100_noun_classes.csv

This CSV file contains information on the 300 noun classes and contains 4 columns.

| Column Name | Type                       | Example                  | Description                                                                   |
| ----------- | -------------------------- | ------------------------ | ----------------------------------------------------------------------------- |
| `id`        | int                        | `222`                    | Unique ID for the noun class.                                                 |
| `key`       | string                     | `label`                  | Key used for the noun class (all keys are a member of their own class).       |
| `instances` | list of string (1 or more) | `"['label', 'sticker']"` | All nouns within the class, including the key.                                |
| `category`  | string                     | `materials`              | Name of the higher-level noun category that this noun class belongs to.       |

[Back to Important Files](#important-files)


#### EPIC_100_verb_classes.csv

This CSV file contains information on the 97 verb classes and contains 4 columns.

| Column Name | Type                       | Example               | Description                                                                   |
| ----------- | -------------------------- | --------------------- | ----------------------------------------------------------------------------- |
| `id`        | int                        | `79`                  | Unique ID for the verb class.                                                 |
| `key`       | string                     | `let-go`              | Key used for the verb class (all keys are a member of their own class).       |
| `instances` | list of string (1 or more) | `"['let', 'let-go']"` | All verbs within the class, including the key.                                |
| `category`  | string                     | `leave`               | Name of the higher-level verb category that this verb class belongs to.       |

[Back to Important Files](#important-files)


#### EPIC_100_retrieval_train.csv

This CSV file contains the action annotations for the **action retrieval** training set and contains 15 columns:

| Column Name           | Type                       | Example        | Description                                                                   |
| --------------------- | -------------------------- | -------------- | ----------------------------------------------------------------------------- |
| `uid`                 | int                        | `0`            | Unique ID for the segment as an int.                                          |
| `narration_id`        | string                     | `P01_01_0`     | Unique ID for the segment as a string with participant ID and video ID.       |
| `participant_id`      | int                        | `P01`          | ID of the participant (unique per participant).                               |
| `video_id`            | string                     | `P01_01`       | ID of the video where the segment originated from (unique per video).         |
| `narration_timestamp` | string                     | `00:00:01.089` | Timestamp of when the original narration was recorded in `HH:mm:ss.SSS`.      |
| `start_timestamp`     | string                     | `00:00:00.14`  | Start time in `HH:mm:ss.SS` of the action segment.                            |
| `stop_timestamp`      | string                     | `00:00:03.37`  | End time in `HH:mm:ss.SS` of the action segment.                              |
| `start_frame`         | int                        | `8`            | Start frame of the action.                                                    |
| `stop_frame`          | int                        | `202`          | End frame of the action.                                                      |
| `narration`           | string                     | `open door`    | Transcribed description of the English narration provided by the participant. |
| `verb`                | string                     | `open`         | Parsed verb from the narration.                                               |
| `verb_class`          | int                        | `3`            | Numeric ID of the verb's class.                                               |
| `noun`                | string                     | `door`         | First parsed noun from the narration.                                         |
| `noun_class`          | int                        | `3`            | Numeric ID of the first noun's class.                                         |
| `all_nouns`           | list of string (1 or more) | `[door]`       | List of all parsed nouns within the narration.                                |
| `all_noun_classes`    | list of int (1 or more)    | `[3]`          | Numeric ID of all of the parsed noun's classes.                               |

[Back to Important Files](#important-files)


#### EPIC_100_retrieval_test.csv

This CSV file contains the action annotations for the **action retrieval** testing set and contains 15 columns:

| Column Name           | Type                       | Example        | Description                                                                   |
| --------------------- | -------------------------- | -------------- | ----------------------------------------------------------------------------- |
| `uid`                 | int                        | `0`            | Unique ID for the segment as an int.                                          |
| `narration_id`        | string                     | `P01_11_0`     | Unique ID for the segment as a string with participant ID and video ID.       |
| `participant_id`      | int                        | `P01`          | ID of the participant (unique per participant).                               |
| `video_id`            | string                     | `P01_11`       | ID of the video where the segment originated from (unique per video).         |
| `narration_timestamp` | string                     | `00:00:00.560` | Timestamp of when the original narration was recorded in `HH:mm:ss.SSS`.      |
| `start_timestamp`     | string                     | `00:00:00.00`  | Start time in `HH:mm:ss.SS` of the action segment.                            |
| `stop_timestamp`      | string                     | `00:00:01.89`  | End time in `HH:mm:ss.SS` of the action segment.                              |
| `start_frame`         | int                        | `8`            | Start frame of the action.                                                    |
| `stop_frame`          | int                        | `113`          | End frame of the action.                                                      |
| `narration`           | string                     | `take plate`   | Transcribed description of the English narration provided by the participant. |
| `verb`                | string                     | `take`         | Parsed verb from the narration.                                               |
| `verb_class`          | int                        | `0`            | Numeric ID of the verb's class.                                               |
| `noun`                | string                     | `plate`        | First parsed noun from the narration.                                         |
| `noun_class`          | int                        | `2`            | Numeric ID of the first noun's class.                                         |
| `all_nouns`           | list of string (1 or more) | `[plate]`      | List of all parsed nouns within the narration.                                |
| `all_noun_classes`    | list of int (1 or more)    | `[2]`          | Numeric ID of all of the parsed noun's classes.                               |

[Back to Important Files](#important-files)


## Additional Information

### File Downloads

Due to the size of the dataset we provide scripts for downloading parts of the dataset:

<!-- TODO: update this with correct information once the download scripts have been implemented, remember to explain that EPIC-Kitchens-55 and EPIC-Kitchens-100 are two different collections on RDSF. -->

* [videos]() (GB)
* [frames]() (GB)
  * [rgb-frames]() (GB)
  * [flow-frames]() (GB)

*Note: These scripts will work for Linux and Mac. For Windows users a bash 
installation should work.*

These scripts replicate the folder structure of the dataset release on RDSF, found 
[here](https://data.bris.ac.uk/data/dataset/2g1n6qdydwa9u22shpxqzp0t8m).

If you wish to download part of the dataset, instructions can be found
[here](https://github.com/epic-kitchens/download-scripts-100).

### Differences to EPIC-Kitchen-100

Whilst videos from EPIC-Kitchens-55 are used within EPIC-Kitchens-100 some of the annotations have been modified to improve the quality of the annotations. Additionally, with EPIC-Kitchens-100, the verb/noun classes have been updated to cover the annotations from the new videos. Because of this, the annotations from EPIC-Kitchens-55 cannot be used for EPIC-Kitchens-100.

<!-- TODO: Narration timestamps differences between EPIC-Kitchens-55/100 -->

### Pickle Files

We also provide pickle files for all of the main train/val/test csvs for ease of use. These files require python 3.5+ and pandas 1.0.0+ to read.
The pickle files are automatically tagged with the commit hash and version for version control purposes which can be found as follows in python:

```
>>> import pandas as pd
>>> train = pd.read_pickle('EPIC_100_train.pkl')
>>> train._metadata
{'commit_hash': 'ce7a0fb', 'version_number': '0.1'
```

showing that this version of the `EPIC_100_train.pkl` came from commit hash ce7a0fb and version number 0.1.

## License
All files in this dataset are copyright by us and published under the 
Creative Commons Attribution-NonCommerial 4.0 International License, found 
[here](https://creativecommons.org/licenses/by-nc/4.0/).
This means that you must give appropriate credit, provide a link to the license,
and indicate if changes were made. You may do so in any reasonable manner,
but not in any way that suggests the licensor endorses you or your use. You
may not use the material for commercial purposes.

## Changelog
Please see the [release history](https://github.com/epic-kitchens/EPIC-Kitchens-100-Annotations/releases) for the changelog.
