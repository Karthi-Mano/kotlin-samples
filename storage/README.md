# Google Cloud Storage Kotlin Sample

[![Open in Cloud Shell][shell_img]][shell_link]

[shell_img]: http://gstatic.com/cloudssh/images/open-btn.svg
[shell_link]: https://console.cloud.google.com/cloudshell/open?git_repo=https://github.com/googlecloudplatform/kotlin-samples&page=editor&working_dir=storage

## Description

This sample application demonstrates how to invoke the [Google Cloud Storage API][storage-api-docs] from Kotlin.

The app is a command-line tool that implements the following Google Cloud Storage operations:

1. Create a bucket
2. List buckets 
3. List blobs in a bucket
4. Upload a file to a bucket
5. Download a blob from a bucket
6. Delete a blob
7. Delete a bucket

Examples:
```sh 
java -jar build/libs/storage.jar create my_awesome_bucket
```
```sh 
java -jar build/libs/storage.jar upload resources/upload/dog.jpg my_awesome_bucket
```

## Quickstart

#### Setup
- [Enable][enable-storage-api] Pub/Sub API.
- Set up [authentication](https://cloud.google.com/docs/authentication/getting-started).

#### Build
- Clone the repository
  ```sh
  git clone https://github.com/GoogleCloudPlatform/kotlin-samples
  cd kotlin-samples/storage
  ```
- Build the project with Gradle Wrapper:
  ```sh
  # run with "-info" flag to print potential errors
  ./gradlew build -info
  ```
You should now have a **'storage.jar'** file under **build/libs/**

#### Running the sample

You can run Google Cloud Storage actions by supplying any of the below commands to the **storage.jar** file:

#### usage

Prints syntax of commands implemented in the sample
```sh 
java -jar build/libs/storage.jar usage
```
#### create

Creates a new bucket
```sh 
java -jar build/libs/storage.jar create <bucket>
```
#### info

Gives details about a bucket or a blob
* To list all buckets in your storage
  ```sh 
  java -jar build/libs/storage.jar info
  ```
* To list all blobs in a bucket
  ```sh 
  java -jar build/libs/storage.jar info <bucket>
  ```
#### upload
 
Uploads a file to a bucket
*  Letting the program infer blob name from **localFilePath**
   ```sh 
   java -jar build/libs/storage.jar upload <localFilePath> <bucket>
   ```
*  Providing blob name
   ```sh 
   java -jar build/libs/storage.jar upload <localFilePath> <bucket> <blob>
   ```  
#### download

Downloads a blob from a bucket to your computer
```sh 
java -jar build/libs/storage.jar download <bucket> <blob> <localFilePath>
```
#### delete

Deletes a bucket or a blob
* To delete a bucket
  ```sh 
  java -jar build/libs/storage.jar delete <bucket>
  ```
* To delete a blob
  ```sh 
  java -jar build/libs/storage.jar delete <bucket> <blob>
  ```
  
Head to [storageTest.kt][storage-sample-test] to see actual tests.

## Using IntelliJ IDE
You can simply **open** the project in IntelliJ.

## About the Client Library

This sample uses the [Google Cloud Client Library for Java][google-cloud-java].
You can read the documentation for more details on API usage and use GitHub
to [browse the source][google-cloud-java-source] and
[report issues][google-cloud-java-issues].

## Troubleshooting
 * **"Failed to detect whether we are running on Google ComputeEngine"**; **"The Application Default Credentials are not available"**: If you get these errors, make sure you set the environment variable `GOOGLE_APPLICATION_CREDENTIALS` to a path to your service account credentials. If you don't already have service account credentials, you will need to
[create them][create-creds]. 

 * If you get any **"Permission denied"** error, make sure you enabled billing for your Google Cloud project. 
 
 * **IntelliJ:** If you get this error: *"...the provided plugin org.jetbrains.kotlin.scripting.compiler.plugin.Scripting CompilerConfiguration ComponentRegistrar is not compatible with this version of compiler"*, **manually update your IDE Kotlin Plugin**.

[storage-sample-test]: test/storageTest.kt
[storage-api-docs]: https://cloud.google.com/storage/
[enable-storage-api]: https://console.cloud.google.com/flows/enableapi?apiid=storage.googleapis.com
[gradle]: https://docs.gradle.org/current/userguide/installation.html
[create-creds]: https://console.cloud.google.com/apis/credentials
[cloud-tools-intellij]: https://cloud.google.com/tools/intellij/docs/
[google-cloud-java]: https://googlecloudplatform.github.io/google-cloud-java
[google-cloud-java-source]: https://github.com/GoogleCloudPlatform/google-cloud-java
[google-cloud-java-issues]: https://github.com/GoogleCloudPlatform/google-cloud-java/issues

## Contributing changes

* See [CONTRIBUTING.md](../CONTRIBUTING.md)

## Licensing

* See [LICENSE](../LICENSE)
