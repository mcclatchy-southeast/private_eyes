# Private Eyes

North Carolina law enforcement agencies in recent years have installed hundreds of cameras across the state that capture data on every vehicle passing by — 24 hours a day, seven days a week.

The data these cameras capture on millions of cars can be accessed by law enforcement for weeks without a warrant. And the biggest player in the industry, Flock Safety, allows departments to link data collected by these privately-owned cameras, vastly increasing the surveillance power of even the smallest department.

Below, you'll find links to our reporting and resources and data that powered The News & Observer's investigation into how use of these devices has grown, a trend that's concerned privacy advocates.

*NOTE: The following findings are still preliminary and remain subject to change with additional reporting and fact checking.*

## Read the series

*Read our three-part series planned for early May 2024.*

## How we did this story

No agency tracks the use of automated license plate readers across the state. So The News & Observer began a reporting project in 2023 to find out just how widespread the devices have become among law enforcement agencies.

The project focused on fixed automated license plate readers, rather than those mounted in police or sheriff's vehicles, because of an ongoing debate in the N.C. General Assembly about allowing the stationary devices on state-maintained roads and highways.
The industry's dominant company Flock Safety, several years ago began offering clients the ability to publish "transparency portals" providing high-level details of their ALPR programs. This can include data on usage policies, the number of cameras and details about the frequency of alerts and searches for each department.

The portals are optional for each client. In July 2023, Flock Safety declined to provide a list of these transparency sites for its law enforcement clients. So The News & Observer set out to find as many as possible.

The N&O created an initial list of web addresses after looking for transparency portals on multiple search engines. Because the pattern of the web addresses were relatively consistent, the N&O also created a list of known Flock clients and possible URLs, which it regularly tested with code.

More web addresses were added after The N&O began surveying more than 150 North Carolina law enforcement agencies to ask about their use of ALPR vendors and whether they had launched a transparency portal for their own activity.

The N&O supplemented its lists with records from the State Bureau of Investigation, which provided details on which agencies obtained access to data extracts from the National National Crime Information Center, which tracks vehicles and license plates of wanted suspects. This data is linked to an agency's Flock Safety system to match and provide automatic alerts on vehicles of interest that pass by the license plate cameras leased by the agency.

After building the list, the N&O used code to regularly collect data on each site from late July to mid-April to better understand, based on publicly available information, how the devices are used.

Details gathered from the sites also revealed which police and sheriff's departments across the country were granted access to an agency's camera data. The N&O used this list of "external organizations" to construct and test for additional transparency portals, based on the previously discovered standard URL pattern.

In all, the project as of mid-April collected data on more than 360 Flock transparency sites for agencies across the country.

It's hard to know how many of the company's more than 5,000 clients have active transparency portals — or what percentage of those sites The N&O's list captured.

In April, Flock did provide a list of 33 North Carolina agency portals. Comparing the two lists, The N&O's was missing 3 of active sites, while the company omitted one from the reporter's list.

N&O reporters also requested the locations of ALPR devices from several law enforcement agencies across the state to examine demographics and neighborhood characteristics of their placement. The city of Greensboro was one of the few municipalities that provided these locations, which The N&O mapped using GIS software.

The N&O used the [Open-Source Routing Machine Project](https://project-osrm.org/) to calculate distances between the cameras and the center of each Guilford County block group, a Census area roughly the size of a neighborhood that generally contains several thousand people. 

After filtering only for block groups containing Greensboro's city limits and matching each block group's closest camera with 5-year 2022 American Community Survey data, the N&O calculated the demographics of neighborhoods within a 5-minute drive of a camera compared to those further away.

The N&O is making the data collected from the law enforcement survey and the Flock transparency sites [available publicly for all uses](https://github.com/mcclatchy-southeast/private_eyes).

## Get the data

The following files [can be downloaded](https://github.com/mcclatchy-southeast/private_eyes/tree/main/data) from the `data` directory in this repo. File names are appended with a timestamp indicating when they were generated, in the format `YYYYMMDDHHMM`.

Use of this data is granted to researchers, policymakers and the public under [an MIT License](https://github.com/mcclatchy-southeast/private_eyes/blob/main/LICENSE).

Please cite/credit/attribute all uses to: `The News & Observer` or `an analysis by The News & Observer`. And if our data makes it into your work, let us know!

To download:
 - Clone our repository
 - Download the entire directory as a zip file
 - Download individual files by right-clicking on the `Raw` or `Download` button and clicking "Save as..."

![Download options](https://github.com/mcclatchy-southeast/private_eyes/blob/main/images/download_options.png)

Have questions? Spot an error in our data? Contact Tyler Dukes at [mtdukes@newsobserver.com](mailto:mtdukes@newsobserver.com).


### Data dictionary/field layout

### agencyYYYYMMDD
Master list of all law enforcement agencies with an assigned ID, as of the date the latest data was pulled. An agency's presence on this list does not indicate whether it uses ALPR devices.

| field |description  |
|:--|:--|
|id| unique identifier for law enforcement agency|
|name| law enforcement agency name |
|notes| free text notes field |

### agency_accessYYYYMMDD
Lookup table linking law enforcement agencies to others with external access to data through the Flock ALPR system, according to the source agency's transparency portal, as of the date the latest data was pulled.

| field |description  |
|:--|:--|
|src_agency| name of agency where ALPR data originates |
|external_agency| name of agency with external access to ALPR data |
|src_agency_id| id of source/originating agency |
|external_agency_id| id of agency with external access |

### public_search_auditYYYYMMDD
Combined public search audit data from all known transparency portals captured regularly during the period from late July 2023 to late April 2024.

| field |description  |
|:--|:--|
|id| unique identifier for law enforcement agency |
|agency| law enforcement agency name |
|url| URL of the transparency portal |
|accessed| date public search audit data was last updated |
|updated| date public search audit data was last updated |

### Acknowledgements

Private Eyes was reported and written by News & Observer investigative reporter Tyler Dukes. News & Observer transportation reporter Richard Stradling contributed reporting. Freelance investigative reporter Jessica Jaglois assisted with public records from Tennessee. | McClatchy data visualization and development by Susan Merriam | Logo design by TK | Design and development by David Newcomb | Art direction, illustrations and animation by Sohail Al-Jamea | Photos, drone footage and videos by News & Observer and Charlotte Observer visual journalists Robert Willett, Travis Long & Kevin Keister | Print design by Mike Homan | Audience outreach and engagement by Laura Brache and Elizabeth Walters at The News & Observer | Edited by Cathy Clabby, McClatchy Southeast investigations editor.
