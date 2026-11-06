# Access FDRI catchment subsets of rain radar data

<img width="309" height="57" alt="UKCEH and FDRI logos" src="https://github.com/user-attachments/assets/04afdc63-663f-41e4-b29d-9419f78d76c3" />
</br>

**Author:** [Tom Keel](https://github.com/Thomasjkeel).

[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/NERC-CEH/access-FDRI-catchment-rain-radar/HEAD)

## Description
This repo contains information about how to access rain radar data (from [1 km NIMROD composite](https://catalogue.ceda.ac.uk/uuid/27dd6ffba67f667a18c62de5c3456350/)) over the 3 FDRI river catchments: 
* [River Chess at Ricksmanworth](https://nrfa.ceh.ac.uk/data/station/spatial/39088) 105 km2
* [River Severn at Dolwen](https://nrfa.ceh.ac.uk/data/station/spatial/54080) 174 km2
* [River Tweed at Peebles](https://nrfa.ceh.ac.uk/data/station/spatial/21003) 694 km2

...in each case we have extracted data in a 20km buffer around the given catchment. NIMROD data was accessed via `/badc/ukmo-nimrod/` on JASMIN, and that data is under the Open Govt. License.

<img src="https://raw.githubusercontent.com/Thomasjkeel/access-FDRI-catchment-rain-radar/refs/heads/main/figures/dolwen_rainradar_2007_07_20_0900.png" alt="catch-subset" style="width:250px;"/>


### about FDRI
The Floods and Droughts Research Infrastructure is a NERC-funded project established to fill critical gaps in flood and drought monitoring, enabling researchers, industry and government practitioners to build the UK’s resilience to extremes in a rapidly changing climate. 


### Data endpoints
All data used in this notebook is available from the JASMIN Object Store:
| s3 path | description | coverage |endpoint |
| ------- | ------- | --- | --- |
| s3://rain-radar/NIMROD-subsets/Chess-20km-buffer | Radar rainfall rate around Chess at Ricksmanworth | Apr-2014 to Oct-2026 | https://fdri-o.s3-ext.jc.rl.ac.uk |
| s3://rain-radar/NIMROD-subsets/Dolwen-20km-buffer | Radar rainfall rate around Severn at Dolwen | Apr-2014 to Oct-2026 | https://fdri-o.s3-ext.jc.rl.ac.uk |
| s3://rain-radar/NIMROD-subsets/Peebles-20km-buffer | Radar rainfall rate around Tweed at Peebles | Apr-2014 to Oct-2026 | https://fdri-o.s3-ext.jc.rl.ac.uk |

Note that you can you use the endpoint: 'http://fdri-o.s3.jc.rl.ac.uk' when working from inside JASMIN ([more info](https://help.jasmin.ac.uk/docs/short-term-project-storage/object-store/jasmin-object-store/#urls-for-internal-and-external-access)).
If you have issues accessing data from JASMIN Object Store, see [CEDA status](https://www.ceda.ac.uk/status/)

## Gallery
<img src="https://raw.githubusercontent.com/Thomasjkeel/access-FDRI-catchment-rain-radar/refs/heads/main/figures/dolwen_rainradar_jul07_timeseries.png" alt="catch-ts" style="width:250px;"/>

<img src="https://raw.githubusercontent.com/Thomasjkeel/access-FDRI-catchment-rain-radar/refs/heads/main/figures/peebles_catchment_extract.png" alt="Dowlen-Jul" style="width:250px;"/>

## How to run these notebooks
### Requirements
| Package | version | Use |
| ------- | ------- | --- |
| numpy | | data |
| xarray[io] | | data |
| dask | | data |
| matplotlib | | plotting |
| cartopy | | spatial |
| s3fs | >=2026.9.0 | cloud read |

### Notebook apps
<details>
    <summary><i><b>If you are not intending to run these notebooks locally, please click here for running options (JASMIN will offer the fastest run-times).</i></b></b></summary>

### Google Colab
**Google Account required**
- Click the "Launch in Colab" button at the top of the notebook.
- Sign in to your google account if needed (blue "Sign in" button in the top right)
- Each notebook includes a cell near the top for installing extra packages not available in the default Colab environment. Run it to install these.

**Note:** Changes you make to the notebook will not be saved by default. If you wish to save your changes, click the "Copy to Drive" text just below the menu bar at the top of the screen. This will create a separate copy of the notebook in your Google Drive and any edits you make will be saved to it.

### Binder
Click the "Launch Binder" button at the top of the notebook. Please note that it may take several minutes to load the environment. After the environment has loaded the notebook will appear and you will be able to run it. 

**Note:** Changes you make to the notebook will not be saved. There is no easy way to save edits you make when using the Binder service.

### JASMIN Notebook Service
[JASMIN](https://www.jasmin.ac.uk/about/) is a computing and data storage resource and environment for NERC researchers. If you have an account, you can make use of their own notebook service to run these notebooks. We are working on simplifying the setup, as it is a little more complicated than using Google Colab or Binder at present. For now, instructions are provided below and on the [JASMIN documentation website](https://help.jasmin.ac.uk/docs/interactive-computing/jasmin-notebooks-service/). As JASMIN is also where the datasets are stored, running notebooks from JASMIN has the advantage of faster data access times as where you are running the notebooks is physically closer to where the data is stored. 

- Once access has been granted, open up the [JASMIN Notebook Service](https://notebooks.jasmin.ac.uk/)
- Obtain a copy of the notebooks by clicking the 'Git' in the menu bar at the top of the webpage, then 'Clone a Repository'. Tick the 'Download the repository' button, and paste in the link to the repository: https://github.com/NERC-CEH/access-FDRI-catchment-rain-radar.git (this can also be obtained by clicking the big green '<> Code' button on the repository main page, clicking 'HTTPS' and copying the link shown).

</details>

## Known gaps in NIMROD composite
The data may also have gaps, owing to underlying issues with the NIMROD composite. These are known gaps:
* Dec 2022

## About this work
This work was carried as part of the UK Government funded [Floods and Droughts Research Infrastructure (FDRI)](https://fdri.org.uk/) project.
