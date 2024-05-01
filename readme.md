![A Flock camera on Hillsborough Street in Raleigh, N.C., in January 2024](https://github.com/mcclatchy-southeast/private_eyes/blob/main/images/flock_tel_013024.jpg)

# Private Eyes

North Carolina law enforcement agencies in recent years have installed hundreds of cameras across the state that capture data on every vehicle passing by — 24 hours a day, seven days a week.

The data these cameras capture on millions of cars can be accessed by law enforcement for weeks without a warrant. And the biggest player in the industry, Flock Safety, allows departments to link data collected by these privately-owned cameras, vastly increasing the surveillance power of even the smallest department.

Below, you'll find links to our reporting and resources and data that powered The News & Observer's investigation into how use of these devices has grown, a trend that's concerned privacy advocates.

*NOTE: The following findings are still preliminary and remain subject to change with additional reporting and fact checking.*

## Read the series

* [Camera by camera, North Carolina police build growing network to track vehicles](https://www.newsobserver.com/news/state/north-carolina/article286920890.html)<br/>May 1, 2024 // *Tyler Dukes*
* [Private Eyes: How we tracked the spread of license plate readers across North Carolina](https://www.newsobserver.com/news/state/north-carolina/article287835755.html)<br/>May 1, 2024 // *Tyler Dukes*

## How we did this story

No agency tracks the use of automated license plate readers across the state. So The News & Observer began a reporting project in 2023 to find out just how widespread the devices have become among law enforcement agencies.

The project focused on fixed automated license plate readers, rather than those mounted in police or sheriff’s vehicles, because of an ongoing debate in the N.C. General Assembly about allowing the stationary devices on state-maintained roads and highways.

The industry’s dominant company, Flock Safety, several years ago began offering clients the ability to publish “transparency portals” providing high-level details of their ALPR programs. This can include data on usage policies, the number of cameras and details about the frequency of alerts and searches for each department.

The portals are optional for each client. In July 2023, Flock Safety declined to provide a list of these transparency sites for its law enforcement clients. So The News & Observer set out to find as many as possible.

The N&O created an initial list of web addresses after looking for transparency portals on multiple search engines. Because the pattern of the web addresses were relatively consistent, the N&O also created a list of known Flock clients and possible URLs, which it regularly tested with code.

More web addresses were added after The N&O began surveying more than 160 North Carolina law enforcement agencies to ask about their use of ALPR vendors and whether they had launched a transparency portal for their own activity.

The N&O supplemented its lists with records from the State Bureau of Investigation, which provided details on which agencies obtained access to data extracts from the National Crime Information Center, which tracks vehicles and license plates of wanted suspects. This data is linked to an agency’s Flock Safety system to match and provide automatic alerts on vehicles of interest that pass by the license plate cameras leased by the agency.

After building the list, the N&O used code to regularly collect data on each site from late July to mid-April to better understand, based on publicly available information, how the devices are used.

Details gathered from the sites also revealed which police and sheriff’s departments across the country were granted access to an agency’s camera data. The N&O used this list of “external organizations” to construct and test for additional transparency portals, based on the previously discovered standard URL pattern.

In all, the project as of mid-April collected data on more than 360 Flock transparency sites for agencies across the country.

It’s hard to know how many of the company’s more than 5,000-plus law enforcement clients have active transparency portals — or what percentage of those sites The N&O’s list captured.

In April, Flock did provide a list of 33 North Carolina agency portals. Comparing the two lists, The N&O’s was missing 3 of the active sites, while the company omitted one from the reporter’s list.

N&O reporters also requested the locations of ALPR devices from several law enforcement agencies across the state to examine demographics and neighborhood characteristics of their placement. The city of Greensboro was one of the few municipalities that provided these locations, which The N&O mapped using GIS software.

The N&O used the [Open-Source Routing Machine Project](https://project-osrm.org/) to calculate distances between the cameras and the center of each Guilford County block group, a census area roughly the size of a neighborhood that generally contains several thousand people.

After filtering only for block groups containing Greensboro’s city limits and matching each block group’s closest camera with 5-year 2022 American Community Survey data, the N&O calculated the demographics of neighborhoods within a 5-minute drive of a camera compared to those further away.

The N&O is making the data collected from the law enforcement survey and the Flock transparency sites [available publicly for all uses](https://github.com/mcclatchy-southeast/private_eyes).

## Get the data

The following files [can be downloaded](https://github.com/mcclatchy-southeast/private_eyes/tree/main/data) from the `data` directory in this repo.

Use of this data is granted to researchers, policymakers and the public under [an MIT License](https://github.com/mcclatchy-southeast/private_eyes/blob/main/LICENSE).

Please cite/credit/attribute all uses to: `The News & Observer` or `an analysis by The News & Observer`. And if our data makes it into your work, let us know!

To download:
 - Clone our repository
 - Download the entire directory as a zip file
 - Download individual files by right-clicking on the `Raw` or `Download` button and clicking "Save as..."

![Download options](https://github.com/mcclatchy-southeast/private_eyes/blob/main/images/download_options.png)

Have questions? Spot an error in our data? Contact Tyler Dukes at [mtdukes@newsobserver.com](mailto:mtdukes@newsobserver.com).

### Data dictionary/field layout

### [nc_agency_surveyYYYYMMDD](https://github.com/mcclatchy-southeast/private_eyes/blob/main/data/nc_agency_survey20240430.csv)
A listing of North Carolina law enforcement agencies using ALPR vendors, according to a survey of 160+ agencies conducted by The News & Observer August 2023 to April 2024, records from the State Bureau of Investigation and a review of contracts and Flock transparency portals, updated as of the file name date.

|field|description |
|:--|:--|
| id | unique identifier for law enforcement agency |
| name | law enforcement agency name |
| type | type of agency (sheriff’s office, police department, etc. |
| city | city location of main headquarters |
| county | county location of main headquarters |
| notes | free text notes field noting source of data or any discrepancies |
| company | name of ALPR vendor used by agency |
| cams_confirmed | number of cameras installed, as confirmed by agency |
| cams_portal | number of cameras indicated by the Flock portal, if applicable |
| flock_portal_url | Flock portal URL, if applicable |
| document_url | Contract or SBI letter noting ALPR use, if applicable |

### [latest_usageYYYMMDD](https://github.com/mcclatchy-southeast/private_eyes/blob/main/data/latest_usage04262023.csv)
The latest usage data scraped from all known law enforcement agency Flock transparency portals, as of the file name date. Layout is identical to the full usage file, just filtered for the most recent date.

| field |description  |
|:--|:--|
|id| unique identifier for law enforcement agency |
|agency| law enforcement agency name |
|updated| date usage data was last updated |
|accessed| date usage data was last updated by the scraper |
|url| URL of the transparency portal |
|data_retention_in_days| number of days data is retained, absent any exceptions |
|number_of_owned_cameras| number of cameras owned by agency |
|external_organizations_with_access| list of external law enforcement agencies with access to ALPR data |
|hotlists_alerted_on| list of hotlists on which ALPR data will alert |
|vehicles_detected_in_the_last_30_days| number of vehicles detected in the last 30 days |
|hotlist_hits_in_the_last_30_days| number of hotlist hits generated in the last 30 days |
|searches_in_the_last_30_days| number of searches performed by law enforcement officers in the last 30 days. |
|public_search_audit| binary indicator of whether the agency's transparency portal includes a CSV file of public information from the last 30 days of searches by officers |

### [agency_usageYYYYMMDD](https://github.com/mcclatchy-southeast/private_eyes/blob/main/data/agency_usage04262023.csv)
Combined usage data scraped from all known law enforcement agency Flock transparency portals, as of the date the latest data was accesssed. File contains all 118 days of data captured periodically from July 27, 2023, through the file name date.

| field |description  |
|:--|:--|
|id| unique identifier for law enforcement agency |
|agency| law enforcement agency name |
|updated| date usage data was last updated |
|accessed| date usage data was last updated by the scraper |
|url| URL of the transparency portal |
|data_retention_in_days| number of days data is retained, absent any exceptions |
|number_of_owned_cameras| number of cameras owned by agency |
|external_organizations_with_access| list of external law enforcement agencies with access to ALPR data |
|hotlists_alerted_on| list of hotlists on which ALPR data will alert |
|vehicles_detected_in_the_last_30_days| number of vehicles detected in the last 30 days |
|hotlist_hits_in_the_last_30_days| number of hotlist hits generated in the last 30 days |
|searches_in_the_last_30_days| number of searches performed by law enforcement officers in the last 30 days. |
|public_search_audit| binary indicator of whether the agency's transparency portal includes a CSV file of public information from the last 30 days of searches by officers |

### [agency_policies](https://github.com/mcclatchy-southeast/private_eyes/blob/main/data/agency_policies.csv)
Policy data scraped from each law enforcement agency's Flock transparency portal. Policies are captured only once unless they change.

| field |description  |
|:--|:--|
|id| unique identifier for law enforcement agency |
|agency| law enforcement agency name |
|updated| date policy was last updated |
|accessed| date policy was last updated by the scraper |
|url| URL of the transparency portal |
|hash| hash generated by the scraper of policy contents. used when testing for policy changes |
|whats_detected| list of items detectable by Flock cameras |
|whats_not_detected| list of items not detectable by Flock cameras |
|acceptable_use_policy| policy of acceptable usage |
|prohibited_uses| prohibited usage |
|access_policy| policy for access to data |
|hotlist_policy| policy for handling hits to hotlist items |

### [agency_accessYYYYMMDD](https://github.com/mcclatchy-southeast/private_eyes/blob/main/data/agency_access20240426.csv)
Lookup table linking law enforcement agencies to others with external access to data through the Flock ALPR system, according to the source agency's transparency portal, as of the date the latest data was pulled.

| field |description  |
|:--|:--|
|src_agency| name of agency where ALPR data originates |
|external_agency| name of agency with external access to ALPR data |
|src_agency_id| id of source/originating agency |
|external_agency_id| id of agency with external access |

### [public_search_auditYYYYMMDD](https://github.com/mcclatchy-southeast/private_eyes/blob/main/data/public_search_audit20240426.csv)
Public search audit data from all known transparency portals captured regularly during the period from late July 2023 to late April 2024. The file here is combined using distinct search ids assigned by Flock.

| field |description  |
|:--|:--|
|id| unique identifier for law enforcement agency |
|agency| law enforcement agency name |
|url| URL of the transparency portal |
|accessed| date public search audit data was last updated |
|updated| date public search audit data was last updated |

### [transparency_url_statusYYYMMDD](https://github.com/mcclatchy-southeast/private_eyes/blob/main/data/transparency_url_status20240429.csv)
List of transparency portal URLs periodically attempted by the scraper, last attempted as of the file name date.

| field |description  |
|:--|:--|
|agency_id| unique identifier for law enforcement agency |
|url_attempted| URL of the transparency portal tested. transparency portals have a base url of `https://transparency.flocksafety.com/` |
|last_attempt_date| date of last attempt to access |
|status_code| status code returned in latest access attempt |
|notes| free text notes field. shows `New valid url` if url has been added since an initial check |

### [agencyYYYYMMDD](https://github.com/mcclatchy-southeast/private_eyes/blob/main/data/agency20240426.csv)
Master list of all law enforcement agencies with an assigned ID, as of the date the latest data was pulled. An agency's presence on this list does not indicate whether it uses ALPR devices.

| field |description  |
|:--|:--|
|id| unique identifier for law enforcement agency|
|name| law enforcement agency name |
|notes| free text notes field |

## Acknowledgements

Private Eyes was reported and written by News & Observer investigative reporter Tyler Dukes. News & Observer transportation reporter Richard Stradling contributed reporting. Charlotte Observer public safety reporter Ryan Oehrli, Wichita Eagle investigative reporter Chance Swaim and Tennessee-based freelance investigative reporter Jessica Jaglois assisted with public records. | Edited by Cathy Clabby | Data visualization and design by Susan Merriam | Development and design by David Newcomb | Illustrations and animation by Sohail Al-Jamea | Photos, drone footage and videos by News & Observer and Charlotte Observer visual journalists Robert Willett, Travis Long & Kevin Keister | Audience outreach and engagement by Laura Brache and Elizabeth Walters
