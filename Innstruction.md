You can include a README with your Power BI dashboard so that anyone who receives the `.pbix` file knows how to connect to AWS Athena and refresh the data.

---

# README – Connecting Power BI to AWS Athena

## Overview

This dashboard uses **Amazon Athena** as its data source. To refresh the data, you must install and configure the **Amazon Athena ODBC Driver** and have valid AWS IAM credentials.

---

## Prerequisites

Before opening the Power BI dashboard, ensure you have:

* Power BI Desktop installed
* Amazon Athena ODBC Driver (64-bit)
* AWS IAM Access Key ID
* AWS IAM Secret Access Key
* Access to the Athena database and S3 query results bucket

---

## Step 1 – Install Amazon Athena ODBC Driver

Download and install the latest Athena ODBC Driver (64-bit) from AWS.

Make sure the driver architecture matches your Power BI version.

---

## Step 2 – Create an ODBC Data Source (DSN)

Open:

```text
ODBC Data Sources (64-bit)
```

Click:

```text
Add → Amazon Athena ODBC Driver
```

Configure the DSN as follows:

| Parameter        | Value          |
| ---------------- | -------------- |
| Data Source Name | Amazon Athena  |
| Region           | eu-north-1     |
| Catalog          | AwsDataCatalog |
| Database         | default        |
| Workgroup        | primary        |

---

## Step 3 – Configure Authentication

Click **Authentication Options**.

Select:

```text
Authentication Type: IAM Credentials
```

Enter:

| Field         | Value                                            |
| ------------- | ------------------------------------------------ |
| Username      | AKIATAYH4LH67UEBNHDP                             |
| Password      | XtFswWS+t+blUrHNifYrm4/WwVlqcNbyH4oYAsHZ         |
| Session Token | Leave empty (unless using temporary credentials) |


---

## Step 4 – Test the Connection

Click:

```text
Test
```

If successful, a confirmation message will appear.

Then click:

```text
OK
```

to save the DSN.

---

## Step 5 – Open the Power BI Dashboard

Open:

```text
Dashboard.pbix
```

When Power BI asks for credentials:

1. Choose **ODBC**
2. Select the DSN:

   ```text
   Amazon Athena
   ```
3. Authenticate using your AWS credentials.

---

## Troubleshooting

### Authentication Failed

Verify:

* Access Key ID
* Secret Access Key
* IAM permissions


### Query Execution Error

Verify:

* Region = eu-north-1
* Catalog = AwsDataCatalog
* Database = default
* S3 Output Location is configured correctly

---

### Connection Summary

```text
DSN Name: Amazon Athena
Region: eu-north-1
Catalog: AwsDataCatalog
Database: default
Workgroup: primary
Authentication: IAM Credentials
```
