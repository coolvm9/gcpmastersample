## Cheatsheet

## gcloud config configurations (used by cli) 
### Create active and set project id or  
gcloud config configurations create [NAME]



## Auth
### Use these for making calls to google provided tools like gcloud, gsutil
gcloud auth application-default login 
gcloud auth login
gcloud auth revoke


### for user written applications SDK (Java Or Python)
#### create service account
gcloud iam service-accounts create SERVICE_ACCOUNT_NAME
gcloud projects add-iam-policy-binding PROJECT_ID --member="serviceAccount:SERVICE_ACCOUNT_NAME@PROJECT_ID.iam.gserviceaccount.com" --role=ROLE
#### Set this variable 
export GOOGLE_APPLICATION_CREDENTIALS=key.json

#### Search order
- ADC searches for credentials in the following locations:
1. GOOGLE_APPLICATION_CREDENTIALS environment variable
2. User credentials set up by using the Google Cloud CLI
3. (for services on GCP, like CE, Cloud Functions) The attached service account, returned by the metadata server
   1. Many Google Cloud services let you attach a service account that can be used to provide credentials for accessing Google Cloud APIs. If ADC does not find credentials it can use in either the GOOGLE_APPLICATION_CREDENTIALS environment variable or the well-known location for Google Account credentials, it uses the metadata server to get credentials for the service where the code is running.
   2. [ADC Reference](https://cloud.google.com/docs/authentication/application-default-credentials)

### passing token
[Passing Application Token](https://cloud.google.com/sdk/gcloud/reference/auth/application-default/print-access-token)


### Create Service Account, generate key, set APPLICATION CREDENTIALS
gcloud iam service-accounts create my-account  
gcloud iam service-accounts keys create key.json --iam-account=my-account@my-project.iam.gserviceaccount.com
export GOOGLE_APPLICATION_CREDENTIALS=key.json



gcloud auth list
gcloud config get-value project
gcloud config list project
gcloud services enable documentai.googleapis.com



gcloud storage cp gs://cloud-samples-data/documentai/codelabs/specialized-processors/procurement_multi_document.pdf .

gcloud storage cp gs://cloud-samples-data/documentai/codelabs/specialized-processors/google_invoice.pdf .