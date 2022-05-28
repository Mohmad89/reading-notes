# Amazon S3 

* is an object storage service that offers industry-leading scalability, data availability, security, and performance. 

## Features of Amazon S3

1. Storage Classes :  
    - this means that there's a set of Storage class designed for different use cases.
2. Storage Management :  
    - Amazon S3 has storage management features that you can use to manage costs, meet regulatory requirements, reduce latency, and save multiple distinct copies of your data for compliance requirements.
    - S3 Lifecycle : Configure a lifecycle policy to manage your objects and store them cost effectively throughout their lifecycle
    - S3 Object Lock :  Prevent Amazon S3 objects from being deleted or overwritten for a fixed amount of time or indefinitely
    - S3 Replication :  Replicate objects and their respective metadata and object tags to one or more destination buckets
    - S3 Batch Operations :  Manage billions of objects at scale with a single S3 API request or a few clicks in the Amazon S3 console
3. Access Management  :  
    - Amazon S3 provides features for auditing and managing access to your buckets and objects.
4. Data Processing :  
    - To transform data and trigger workflows to automate a variety of other processing activities at scale
    - S3 Object Lambda : Filter rows, dynamically resize images, redact confidential data, and much more.
5. Storage Logging and Monitoring : 
    - monitor and control how your Amazon S3 resources are being used.
    - Automated monitoring tools
        1. Amazon CloudWatch metrics for Amazon S3 
        2. AWS CloudTrail 
    - Manual Monitoring tools  :  
        1. Server access logging 
        2. AWS Trusted Advisor

## How Amazon S3 Works 

* first we create a buckets and specify a bucket name , then you upload your data to that bucket as objects in Amazon S3. Each object has a key (or key name)
![](image/s3%20Word.jpg)

1. Buckets : Container of Object.
2. Object : Objects are the fundamental entities stored in Amazon S3. Objects consist of object data and metadata.
3. Keys :  is the unique identifier for an object within a bucket.


## S3 Versioning 

* You can use S3 Versioning to keep multiple variants of an object in the same bucket.

## Version ID 

* When you enable S3 Versioning in a bucket, Amazon S3 generates a unique version ID for each object added to the bucket

## S3 Access Points 

*  Access Points are attached to buckets that you can use to perform S3 object operations, such as GetObject and PutObject.
* Access Points simplify managing data access at scale for shared datasets in Amazon S3.

## Access Control Lists (ACLs)

* You can use ACLs to grant read and write permissions to authorized users for individual buckets and objects. Each bucket and object has an ACL attached to it as a subresource.


# S3 Configuration 

1. execute the command "amplify add storage"
2. Puch your change "amplify puch"
3. Install Amplify Libraries 
    - implementation 'com.amplifyframework:aws-storage-s3:1.35.4'
    - implementation 'com.amplifyframework:aws-auth-cognito:1.35.4'
4. initialize Amplify Storage 
    - Amplify.addPlugin(new AWSCognitoAuthPlugin());
    - Amplify.addPlugin(new AWSS3StoragePlugin())
5. Uploading data to your bucket : 
    - Amplify.Storage.uploadFile(  
            "ExampleKey",  
            exampleFile,  
            result -> Log.i("MyAmplifyApp", "Successfully uploaded: " + result.getKey  ()),  
            storageFailure -> Log.e("MyAmplifyApp", "Upload failed", storageFailure)
    );
    - 

