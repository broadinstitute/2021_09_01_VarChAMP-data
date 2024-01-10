# Image-based Profiling for [VarChAMP](https://github.com/broadinstitute/2021_09_01_VarChAMP)

This repository was derived from a [template repository](https://github.blog/2019-06-06-generate-new-repositories-with-repository-templates/) located at https://github.com/cytomining/profiling-template.
The purpose of the repository is to weld together a versioned data processing pipeline with versioned processed output data for a single image-based profiling experiment.

## Notes

To download the data in this repo, first, clone this repo

```bash
git clone git@github.com:broadinstitute/2021_09_01_VarChAMP-data.git
```

then, download the profiles

```bash
cd 2021_09_01_VarChAMP-data
dvc pull
```

### AWS configuration

The DVC cache is stored in an AWS S3 bucket. 
To access the files stored via DVC, you will need to created a IAM user with the `AmazonS3ReadOnlyAccess` policy attached:

```json
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Action": [
                "s3:Get*",
                "s3:List*",
                "s3-object-lambda:Get*",
                "s3-object-lambda:List*"
            ],
            "Resource": "*"
        }
    ]
}
```
