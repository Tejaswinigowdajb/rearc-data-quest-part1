# rearc-data-quest-part1
[rearc-data-quest-bls-02-f8d3c7f2-86fc-4fd8-b07b-35aa480142be.zip](https://github.com/user-attachments/files/20840766/rearc-data-quest-bls-02-f8d3c7f2-86fc-4fd8-b07b-35aa480142be.zip)


[rearc-data-quest-bls-02.zip](https://github.com/user-attachments/files/20840765/rearc-data-quest-bls-02.zip)

# BLS Dataset to S3

## Objective

This script fetches datasets from the U.S.(BLS) public repository and republishes them in an Amazon S3 bucket. It ensures files are only uploaded when they change, handles access policies, and is ready to be deployed in AWS Lambda for automation.

---

## Files Fetched

- `pr.data.0.Current`
- `pr.series`
- `pr.data.1.AllData`

These files are fetched from:  
📎 https://download.bls.gov/pub/time.series/pr/

##  Features

-  Adds a User-Agent header to comply with BLS API policies
-  Skips uploading files already in S3 by comparing file hashes 
-  Can be run  in AWS Lambda
-  Logs actions: upload/skipped/errors

---

**In AWS Lambda**

Package the script with the Lambda Layer

Use the file lambda_handler.py

IAM role must allow:

s3:PutObject, s3:GetObject, s3:HeadObject, s3:ListBucket on your bucket

**ATTACHED THE ZIP FILE FOR LAMBDA_HANDLER.PY AND REQUEST-LAYER**


**Uploaded Files in S3**

**pr.data.0.Current**
[https://rearc-data-quest-bls-02.s3.eu-north-1.amazonaws.com/bls_data/pr.data.0.Current
](https://rearc-data-quest-bls-02.s3.eu-north-1.amazonaws.com/bls_data/pr.data.0.Current)

**pr.series**
[https://rearc-data-quest-bls-02.s3.eu-north-1.amazonaws.com/bls_data/pr.series
](https://rearc-data-quest-bls-02.s3.eu-north-1.amazonaws.com/bls_data/pr.series)

**pr.data.1.AllData**
[https://rearc-data-quest-bls-02.s3.eu-north-1.amazonaws.com/bls_data/pr.data.1.AllData
](https://rearc-data-quest-bls-02.s3.eu-north-1.amazonaws.com/bls_data/pr.data.1.AllData)

