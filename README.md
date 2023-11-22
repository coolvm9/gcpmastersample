# gcpmastersample
PROJECT_ID = !(gcloud config get-value core/project)
PROJECT_ID = PROJECT_ID[0]

BQ_LOCATION = 'US'
REGION = 'us-central1'
BQ_DATASET = f"{PROJECT_ID}:bqmlga4"
!bq mk --location={BQ_LOCATION} --dataset {BQ_DATASET}
