# What's up here?
This directory contains localized release notes for this App. Every time a new release (push to master) 
was created, the developer has to give information about what was changed.

# Why?
Based on the provided information, we will create a changelog (What's new) for Google Play Store and Apple App Store.

## Do I really have to provide translations?
Yes, you have to! Although, there is a fallback mechanism. If not given, we will use the English ones.

## Which translations do I have to provide?
For every countries native language where we are publishing our App + English.

# How?
Simply open each `release_notes.txt` file underneath the corresponding internationalized folder, replace the current content with your information and commit it.

⚠️ Always replace the content. Only your changes should be there afterwards ⚠️ 

# And then?
During the CI/CD build, the information provided here are copied over to the `ios/fastlane metadata` and `android/fastlane/metadata` 
folders. From there, fastlane can use them to provide the changelog in the correct platform format.

# I'm interested in the current metadata
Fastlane is able to fetch the current published metadata from the stores. There are two prerequisites:

* Fastlane ( `gem install fastlane -NV` ) installed on your device
* You have management access rights for the stores:
  * Username + Password for the App Store
  * Api json for Google Play

## ios

* `cd ios/`
* `fastlane deliver init`
* Enter App Store credentials
* You will find the complete metadata set underneath `ios/fastlane/metadata`

For more information see https://docs.fastlane.tools/actions/deliver/#deliver

## android

* `cd android/`
* `fastlane supply init -j <your-api-key.json>`
* You will find the complete metatadata set underneath `android/fastlane/metadata`

For more information see https://docs.fastlane.tools/actions/supply/#supply
  
