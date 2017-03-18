# The Amazon S3 Background Transfer Sample

This sample demonstrates how to use `AWSS3TransferUtility` to download / upload files in background.

## Requirements

* Xcode 8 and later
* iOS 8 and later

## Using the Sample

1. The AWS Mobile SDK for iOS is available through [CocoaPods](http://cocoapods.org). If you have not installed CocoaPods, install CocoaPods:

		sudo gem install cocoapods
		pod setup

1. To install the AWS Mobile SDK for iOS, simply add the following line to your **Podfile**:

		pod 'AWSS3'

	Then run the following command:
	
		pod install

1. Create an Amazon S3 bucket. (For details on creating a bucket in the Amazon S3 console, see [Create a Bucket](http://docs.aws.amazon.com/AmazonS3/latest/gsg/CreatingABucket.html).)

1. Upload a image in the bucket. Open `Constants.m` or `Constants.swift` and update the following lines with the appropriate constants:

	Swift

        let S3BucketName: String = "YourS3BucketName"

	Objective-C

        NSString *const S3BucketName = @"YourS3BucketName";
        NSString *const S3DownloadKeyName = @"YourDownloadKeyName";
		
1. In the [Amazon Cognito console](https://console.aws.amazon.com/cognito/), use Amazon Cognito to create a new identity pool. Obtain the `PoolID` constant. Make sure the [role](https://console.aws.amazon.com/iam/home?region=us-east-1#roles) has full permissions for the bucket you created.

1. Open `S3BackgroundTransferSampleObjC.xcworkspace` or `S3BackgroundTransferSampleSwift.xcworkspace`.

1. Open `Info.plist` and update the following lines with the appropriate constants:
  
AWS --> CredentialsProvider --> CognitoIdentity --> Default --> Region      // eg. USEast1
AWS --> CredentialsProvider --> CognitoIdentity --> Default --> PoolId
AWS --> Cognito --> Default --> Region                                      // eg. USEast1
AWS --> S3TransferUtility --> Default --> Region                            // eg. USEast1

1. Build and run the sample app.
