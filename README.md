Try gradle-aws-s3-sync - a gradle plugin to sync local to S3
======

### Prepare your local plugin
*1*. Clone the repo:
```
$ git clone https://github.com/lifuzu/gradle-aws-s3-sync.git
```
*2*. Build and Publish to Local Maven Repo
```
$ ./gradlew clean build pTML
```

### Run the demo
*1*. Clone the repo:
```
$ git clone https://github.com/lifuzu/try-gradle-aws-s3-sync.git
```
*2*. Config your credentials in ~/.gradle/gradle.properties:
```
awsAccessKey = <Your aws access key here>
awsSecretKey = <Your AWS secret key here>
```
*3*. Config your bintray access key in ~/.gradle/gradle.properties:
```
bintrayUser = <Your bintray user name here>
bintrayKey = <Your bintray key here>
```
*4*. Config your bucket name in build.gradle, ln. 17, here:
```
ext {
    aws = [accessKey: awsAccessKey, secretKey: awsSecretKey]
    s3 = [bucket: "<your_bucket_name>/"]
    local = [directory: "pool"]
}
```

### NOTE:
If you have an error like this:
```
UP Local [.../gradle-devel/try-gradle-aws-s3-sync/pool/hello.txt] => S3[bucket_name/]
  Listing objects in service                                              :deploy FAILED
``` 
try to create a .cache folder under the same directory as build.gradle
