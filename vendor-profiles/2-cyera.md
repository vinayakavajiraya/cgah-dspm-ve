### Cyera

### Rating: 2.33

#### Overview
* Deployment was complete with all the required data sources except Databricks.
* Data classification is very limited but accurate for classifed data. Many columns were left without classification like city name, driver license, date, last 8 digits of SSN and many more columns.
* Very expensive! Ahead request to force stop the discovery of remaining data after two days as cost burn down was quite high for the first 50 TB data.
* Good integration with Office 365.
* No support for databricks.
* $\textcolor{red}{\text{No posture management with current version. Will be available in next releases of Cyera platform.}}$
* $\textcolor{red}{\text{No audit trails in current version. One of the use case of role assumption was not demonstrated as the feature was not available in current version of Cyera.}}$
* $\textcolor{red}{\text{Uses most privilage mode (Administrator account is created when Cyera stack was deployed into Azure)}}$
* $\textcolor{red}{\text{Cyera Team did not agreed to perform delta scan as they mentioned that, "We need to take permission from their higher authorities for doing this in POC"}}$
* $\textcolor{orange}{\text{Control over cluster scaling in and out is not possible as it's managed by DevOps team of Cyera (Backoffice channels). Uses Karpernter or similar technologies for K8s scaling.}}$
* $\textcolor{orange}{\text{Business executives were overpowering the technical team and reviewers to perform limited tests in POC. (Proof: Please review all the meeting recordings for verification and conclusion on this observation.)}}$

#### Key Features
| Cyera Feature             | Availability  | Description | $\textcolor{Red}{\text{Notes [For Ahead Only]}}$ |
|-------------------        |--- |-------------|---|
| Data Discovery            | ✓ | Automatically identifies and catalogs sensitive data across various data sources | - Cyera was able to discover all the data stores in AWS, Azure, Snowflake and Office 365. <br/><br/> - Databricks is not supported by Cyera. |
| Data Classification       | ❕ | Data classification is based on sampling hence the classified data were quite accurate but very limited. | - Cyera's data calssification is accurate, only for limited data. <br/><br/> - Many simple columns like Driver license, city, URL or web address, ZIP code, and many more. <br/><br/> - [Please refer the screenshots for more details.](../assets/cyera/) |
| Risk Assessment           | ❕ | Evaluates data security risks and provides limited actionable insights and no data coverage tracability | |
| Access Control            | ❕ | Data access permissions monitoring was not robust and not reliable | |
| Compliance Monitoring     | ✓ | Ensures adherence to regulatory requirements and industry standards | |
| Threat Detection          | ❌ | Potential security threats and anomalies detection rate is not accurate and less reliable | |
| Data Encryption           | ❕ | Cyera team did not provide insights on how sampling data is transmitted to Cyera cloud for classification | |
| Activity Monitoring       | ✓ | Tracks and logs user activities related to sensitive data | |
| Incident Response         | ❌ | Cyera team did not demonstrate this feature and mentioned that this feature is available in future releases of their product | |
| Integration Capabilities  | ✓ | Connects with existing security tools and cloud platforms | |
| Reporting and Analytics   | ✓ | Generates high level reports and provides data visualization along with data samples for verification | |
| Automated Remediation     | ❌ | Does not or atleast this feature was not demonstrated, which offers automated solutions for addressing identified security issues. <br/> Note: Scan was incomplete due to force stop as cost burn down was high for the first 50 TB data. | |

#### <u>Strengths & Weaknesses</u>

**Strengths:**
1. Accurate data classification based on sampling
2. Complete deployment with most required data sources
3. Good integration with Office 365
4. Effective compliance monitoring
5. Strong activity monitoring capabilities
6. Good reporting and analytics with data visualization

**Weaknesses:**
1. Very expensive, with high cost burn down for initial data discovery
2. No support for Databricks
3. Lack of posture management in the current version
4. Limited risk assessment with no data coverage traceability
5. Unreliable access control and permissions monitoring
6. Inaccurate and unreliable threat detection
7. Lack of transparency in data encryption for classification process
8. Absence of incident response features in the current version
9. No automated remediation capabilities demonstrated but integration is possible with Wiz, Jira and Webhooks.
10. Incomplete data discovery due to forced stop (cost concerns)

#### [Review Required] Integration Checklist

| Resource | Integration Status | Notes |
|----------|------------|-------|
| AWS      | Yes | - S3 Buckets <br/> - RDS for Oracle, Postgres, SQL Server  |
| Azure    | Yes | - Azure AD integration <br> - Azure Blob storage access <br> - ADLS Gen 2 <br/> - Azure Database for Oracle, Postgres, SQL Server <br/> - Audit Logs were not enabled or integrated |
| Snowflake| Yes | - Set up Snowflake account integration<br>- Configure access to relevant databases and schemas<br>- Verify query history and access logging |
| Databricks| No |  |
| Office 365| Yes | - Set up Microsoft Graph API integration<br>- Configure access to relevant services (SharePoint, OneDrive, etc.)<br>- Enable audit logging for Office 365 activities |

<br/>

**Data Discovery Coverage:**

| Data Source | Discovery Coverage |
|---|---|
| AWS | 30% |
| Azure | 50% |
| Snowflake | 100% |
| Databricks | 0% |
| Office 365 | 100% |
| SQL Server on EC2 | 0% |
| **Total** | **56%** |

<br/>

**[WIP] Cost Analysis:**

| Element | Cost (USD) |
|---|---|
| Day 1 - Tuesday   | $ 281.03        | $ 24.44           |
| Day 2 - Wednesday | $ 8464.45       | $ 189.06          |
| Day 3 - Thursday  | $ 4704.03       | $ 85.28           |
| Day 4 - Friday    | $ 598.74        | $ 60.35           |
| Day 5 - Saturday  | $ 526.60        | $ 60.43           |
| Day 6 - Sunday    | $ 400.97        | $ 59.00           |
| Day 7 - Monday    | $ 361.35        | $ 19.73           |
| **Total**         | **$ 15337.17**  | **$ 498.29**      |
|||

#### Evaluation Summary
Cyera demonstrates strong capabilities in data discovery and classification across multiple cloud platforms, including AWS, Azure, Snowflake, and Office 365. However, the evaluation reveals several significant limitations:

1. Incomplete data discovery (56% total coverage) due to cost concerns and forced stoppage.
2. Lack of posture management features in the current version.
3. Limited risk assessment capabilities without data coverage traceability.
4. Unreliable access control and permissions monitoring.
5. Inaccurate and unreliable threat detection.
6. Lack of transparency in data encryption for the classification process.
7. Absence of incident response features.
8. No automated remediation capabilities, although integration is possible with third-party tools.

While Cyera shows promise in its integration capabilities with major cloud providers and services, the platform falls short in critical areas of data security posture management. The incomplete data discovery and lack of essential features like posture management, reliable risk assessment, and incident response significantly impact its overall effectiveness. 

Further development and improvements in these areas would be necessary for Cyera to provide a more comprehensive and reliable DSPM offering.

***
***