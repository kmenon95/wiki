# Snyk-AppSec-scripts

This repository contains scripts designed to facilitate Snyk Security products' usage, particularly focusing on data retrieval and member management functionalities.

## Scripts Overview

1. **Snyk Settings Data Fetch (Snyk_sast_settings.py)**
   - **Description**: This script fetches settings data for Snyk, focusing on Snyk Code and DockerSCM settings if enabled for any integration or organization. It generates a report as a workflow artifact which can be downloaded from the latest run.
   - **Workflow**: The script is scheduled to run automatically on a daily basis. To obtain the latest report, download the artifact from the most recent workflow run. [click here](https://github.com/DigitalInnovation/Snyk-AppSec-scripts/actions/workflows/Snyk_org_setting_fetch.yml)

2. **Snyk Organization Members List Fetch (Org_Members_List.py)**
   - **Description**: This script retrieves a comprehensive list of members within Snyk organizations, including their respective roles. It produces a final report that can be downloaded upon completion.
   - **Workflow**: This script is manually triggered. To run it, initiate the "Fetch Snyk Org Members" workflow. [Click here](https://github.com/DigitalInnovation/Snyk-AppSec-scripts/actions/workflows/Members_List.yml)

3. **Snyk Single Organization Members List Fetch (Single_Org_Members_List.py)**
   - **Description**: This script fetches the member list for a specific Snyk organization based on the provided OrgID, including group admins. The resulting report can be accessed as an artifact post-successful execution.
   - **Workflow**: To utilize this script, manually trigger the "Fetch members for single Org" workflow and provide the desired OrgID at dispatch. [Click here](https://github.com/DigitalInnovation/Snyk-AppSec-scripts/actions/workflows/Single_org_member_List.yml)
  
4. **Leaver Workflow (Leaver.py)**
   - **Description**: This workflow helps identify leavers from M&S who still have access to our AppSec tools (Snyk and Semgrep). It is scheduled to run daily at midnight and can also be manually triggered. No inputs are required.
   - **Workflow**: [Click here](https://github.com/DigitalInnovation/Snyk-AppSec-scripts/actions/workflows/Leaver.yml)

5. **Fetch Y Accounts from M&S Snyk (service_accounts.py)**
   - **Description**: This workflow identifies service accounts or Y-accounts tagged with Snyk. The active Y-accounts tagged with Snyk can be found at [Snyk Y-accounts List](https://devopssec.engineering.mnscorp.net/Products/Snyk-Open-Source/Snyk-Yaccounts/).
   - **Workflow**: [Click here](https://github.com/DigitalInnovation/Snyk-AppSec-scripts/actions/workflows/y-account.yml)

6. **Delete Snyk User from Group (Snyk_user_remove.py)**
   - **Description**: This workflow helps remove users from a Snyk group. Update the `input/users_to_delete_snyk.csv` file with the list of users and userIDs who are identified as leavers before executing the workflow. The output artifact is a deletion report.
   - **Workflow**: [Click here](https://github.com/DigitalInnovation/Snyk-AppSec-scripts/actions/workflows/user_remove.yml)


## Usage

- **Prerequisites**: Ensure you have the necessary permissions and credentials configured to access Snyk resources.
- **Workflow Execution**:
   - For automated reports (Snyk Settings Data Fetch): Download the report artifact from the latest workflow run.
   - For organization-wide member reports (Snyk Organization Members List Fetch): Trigger the "Fetch Snyk Org Members" workflow.
   - For specific organization member details (Snyk Single Organization Members List Fetch): Run the "Fetch members for single Org" workflow, providing the OrgID as instructed.
   - For identifying leavers (Leaver Workflow): The workflow runs daily and can be triggered manually if needed.
   - For fetching Y-accounts (Fetch Y Accounts): Trigger the workflow to get the list of Y-accounts tagged with Snyk.
   - For deleting Snyk users (Delete Snyk User from Group): Update the `input/users_to_delete_snyk.csv` file and then manually trigger the workflow to remove the listed users.


## ✍️ Contributors

We welcome contributions from the M&S community to keep this repository up to date with best practices tailored for Marks & Spencer. If you'd like to contribute:

1. Create a branch with a descriptive name (e.g., `feature/add-new-best-practice`).

2. Make your contributions.

3. Create a pull request to submit your changes. Please provide a clear description of the changes and why they are valuable for M&S.

4. Your pull request will be reviewed, and upon approval, it will be merged.

Thank you for helping us make this resource better for Marks & Spencer!
