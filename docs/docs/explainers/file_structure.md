---
sidebar_label: 'Overview of folder structures'
sidebar_position: 3
---

# 
## NEW TEST ENTRY

Here

## Folder structures

## consortiumpriorityperiod-library-red

This bucket is only available to the core Genes & Health team, and to companies in the Genes & Health Industry Consortium. It contains data restricted during 9 month priority access periods (e.g. exome sequencing). Specifically, read access is only for sandboxes 1 3 4 5 6 7 9 10 13.

Same storage type as `/genesandhealth/library-red`, see comments above

`/genesandhealth/consortiumpriorityperiod-library-red` is a google storage bucket `gs://qmul-sandbox-production-library-consortiumpriorityperiod-red` (read+write only for admins)

## Green folders
### green

Specific to each sandbox.

green can be read by other users in the sandbox. Users cannot write to green.

Users can download from `/genesandhealth/green` from internet/external systems.

The admin team will review data out requests, and either place the data in green (for specific users to download, short term) or `library-green` (long term availability for all users to download).

**Data in each sandbox green will be deleted approx 1 week after creation. green is not intended for long term storage, only data transfer/download.**

Same storage type as `/genesandhealth/library-red`, see comments above.

`/genesandhealth/green` is a google bucket `gs://fg-qmul-production-sandbox-1_green/` (read only for users, read+write only for admins) (replace the 1 with whichever sandbox you want)

### consortiumpriorityperiod-library-green

Access as for `consortiumpriorityperiod-library-red` but with external download (e.g. gsutil) enabled. Used for results. Not for individual level data.

`gs://qmul-sandbox-production-library-consortiumpriorityperiod-green`

## Other folders
### shared

You can 'publish' a file to `/genesandhealth/shared` by right clicking on it, and selected 'Share with all users'

`/genesandhealth/shared` is available to all other users within the TRE.

### pipelines

This is the output of the high performance compute WDL Pipelines, that the `ivm/pipeline` writes to. Users of the sandbox have read only access.

Specific to each sandbox.

This is slower storage of large capacity (\>8 PiB @ Feb 2022)

### Public datasets bucket

We also maintain a bucket for public datasets. This is not visible from within the TRE. Much of the data is mirrored in `genesandhealth/library-green/` within the TRE.

`gs://genesandhealth_publicdatasets/`

## Copying between Google Buckets within the TRE

Is permitted from within the TRE, subject to user read/write permissions as above.

Admins may copy from Google Buckets to external systems. However external copy from external Google Buckets direct to/from TRE Google Buckets is prohibited for security reasons.

## Backups

Data in selected folders is protected from accidental deletion or alteration by the Google Object Versioning service. Specifically, for data in these folders -

**Shared folders**

`/genesandhealth/library-red` , 1 version, 30 days

`/genesandhealth/consortiumpriorityperiod-library-red`, 1 version, 30 days

`/genesandhealth/nhsdigital-sublicence-red`, 1 version, 30 days

**Sandbox-specific folders**

`/genesandhealth/red`, 2 versions, 30 days

`/genesandhealth/pipeline`, 1 version, 7 days

we will keep either a) the prior version of the data prior to a change (or deletion) by a user for 30 days , or b) two prior versions of the data prior to a change (or deletion) by a user for 30 days.

This allows the prior version to be restored, in the event of accidental erasure or deletion.

To say this another way: imagine you accidentally alter or delete a file in the `/genesandhealth/library-red` folder. Then the version of the file prior to its removal can be restored, for up to 30 days after the change. In the sandbox-specific `/genesandhealth/red` folder, two prior versions of the file will be kept, each for 30 days after the change leading to its creation.

Restoring a prior version of an accidentally removed or modified file requires utilities only available to administrators: if you need this, contact us using Slack or writing to [hgi@sanger.ac.uk](mailto:hgi@sanger.ac.uk), including the word "Urgent" in the subject header.

## Figure of Directory Structure
