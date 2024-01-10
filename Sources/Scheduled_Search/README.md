<img src="https://github.com/CrowdStrike/CrowdStream_and_Cribl-Stream_CrowdStrike_Wiki/blob/main/Visuals/cs-logo.png?raw=true" width=70% height=70%>

> [!IMPORTANT] <br>
> In order for this sample configuration to work, the API credentials must be properly scoped. <br>
> The scope required is: Scheduled Reports - Read <br>
> This sample source also requires a custom event breaker

# Scheduled Search Source Configuration Specifics
> Scheduled Search collection requires some advanced configuration as opposed to other REST collectors. <br>
___
Table of Contents: <br>
[Section 1: Before Creating the REST Collector](#section-1-before-creating-the-rest-collector) <br>
[Section 2: REST Collector Configuration Specifics](#section-2-rest-collector-configuration-specifics) <br>
[Section 3: Event Breakers configuration](#section-3-event-breakers-configuration) <br>
[Section 4: Validate, Save and Commit configuration](#section-4-validate-save-and-commit-configuration) <br>

---

## Section 1: Before Creating the REST Collector <br>
> In order to configure the collection of a Scheduled Search, the search ID needs to be identified. The easiest way to accomplish this is via the Falcon UI.
>### Step 1: Navigate to the Scheduled Search page in the Falcon UI <br>
> <img src="https://github.com/CrowdStrike/CrowdStream_and_Cribl-Stream_CrowdStrike_Wiki/blob/main/Visuals/scheduled_search/scheduled_search.png?raw=true" width=50% height=50%> <br>
>### Step 2: Locate Scheduled Search to be collected in the available searches <br>
> <img src="https://github.com/CrowdStrike/CrowdStream_and_Cribl-Stream_CrowdStrike_Wiki/blob/main/Visuals/scheduled_search/sch_sear_locate.png?raw=true" width=70% height=70%> <br>
> [!NOTE] <br>
> If this is going to be a scheduled collection, ensure that the status is 'Active'. In addition, if possible, try and ensure that the collection will not be running when the collection is attempted.<br>
>### Step 3: Select the Scheduled Search to be collected in the available searches <br>
> Once the Scheduled Search has been selected, "Scheduled search details" will be present on the right side of the screen. <br>
> <img src="https://github.com/CrowdStrike/CrowdStream_and_Cribl-Stream_CrowdStrike_Wiki/blob/main/Visuals/scheduled_search/sch_sear_details.png?raw=true" width=70% height=70%> <br>
>### Step 4: Record the Scheduled Search ID in the URL <br>
> In the URL of the Scheduled Search details page, locate and record the ID:
> <img src="https://github.com/CrowdStrike/CrowdStream_and_Cribl-Stream_CrowdStrike_Wiki/blob/main/Visuals/scheduled_search/sch_sear_url.png?raw=true" width=70% height=70%> <br>
---
## Section 2: REST Collector Configuration Specifics <br>

>### Step 1: Open the REST Collector configuration <br>
> <img src="https://github.com/CrowdStrike/CrowdStream_and_Cribl-Stream_CrowdStrike_Wiki/blob/main/Visuals/scheduled_search/sch_sear_collect_filter_id.png?raw=true" width=70% height=70%> <br>
>### Step 2: Configure the Scheduled Report ID filter value<br>
> Navigate to 'Collector Settings' -> 'Discover parameters' and locate the Value expression for the 'filter' Name:<br>
> <img src="https://github.com/CrowdStrike/CrowdStream_and_Cribl-Stream_CrowdStrike_Wiki/blob/main/Visuals/scheduled_search/sch_sear_disc_fil_value_1.png?raw=true" width=70% height=70%> <br>
> If needed the filter can be opened in 'Advanced Mode' by selecting the box with the arrow to the right. This will open a popup window showing the complete parameter configuration: <br>
> <img src="https://github.com/CrowdStrike/CrowdStream_and_Cribl-Stream_CrowdStrike_Wiki/blob/main/Visuals/scheduled_search/sch_sear_collect_filter_detailed.png?raw=true" width=70% height=70%> <br>
> Ensure that the 'scheduled_report_id' field value is configured wih the report ID collected from the Falcon UI. If this collector will run on a schedule then also validate that the 'last_updated_on" field value calculation aligns with that timeframe. <br> 
---

## Section 3: Event Breakers configuration <br>
> This Collector Configuration does require a specific Event Breaker which can be downloaded from here: [Event Breakers](https://github.com/CrowdStrike/CrowdStream_and_Cribl-Stream_CrowdStrike_Wiki/tree/main/Event_Breakers) <br>
>### Step 1: Open the Event Breakers setting in the REST Collector configuration <br>
> In the REST Collector configuration, navigate to 'Result Settings' -> 'Event Breakers' <br>
> <img src="https://github.com/CrowdStrike/CrowdStream_and_Cribl-Stream_CrowdStrike_Wiki/blob/main/Visuals/scheduled_search/sch_sear_eb_general.png?raw=true" width=70% height=70% > <br>
>### Step 2: Assign the 'CrowdStrike_Scheduled_Search' Event Breaker ruleset <br>
> From the 'Event Breaker ruleset' dropdown, select 'CrowdStrike_Scheduled_Search'. If this selection is not present, ensure that the Event Breaker ruleset has been uploaded and commmitted.  <br>
> <img src="https://github.com/CrowdStrike/CrowdStream_and_Cribl-Stream_CrowdStrike_Wiki/blob/main/Visuals/scheduled_search/sch_sear_eb_select.png?raw=true" width=70% heigh=70% > <br>
---
## Section 4: Validate, Save and Commit configuration <br>
>### Step 1: Validate that all the necessary changes have been made<br>
> Ensure that all the necessary changes and modifications have been completed. <br>
>### Step 2: Save the REST Collector configuration <br>
> In the bottom right corner select 'Save'
> <img src="https://github.com/CrowdStrike/CrowdStream_and_Cribl-Stream_CrowdStrike_Wiki/blob/main/Visuals/scheduled_search/sch_sear_save.png?raw=true" width=70% height=70%><br>
>### Step 3: Commit and Deploy Changes <br>
> In the top right corner select 'Commit & Deploy' <br>
> <img src="https://github.com/CrowdStrike/CrowdStream_and_Cribl-Stream_CrowdStrike_Wiki/blob/main/Visuals/scheduled_search/sch_sear_commit.png?raw=true" width=50% height=50%><br>

