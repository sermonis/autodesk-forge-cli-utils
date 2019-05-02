# forge-cli-utils [![Build Status](https://travis-ci.org/petrbroz/forge-cli-utils.svg?branch=master)](https://travis-ci.org/petrbroz/forge-cli-utils) [![npm version](https://badge.fury.io/js/forge-cli-utils.svg)](https://badge.fury.io/js/forge-cli-utils)

Command line tools for Autodesk Forge services.

[![asciicast](https://asciinema.org/a/242800.svg)](https://asciinema.org/a/242800)

## Usage

- install the library, either in your own npm project (`npm install --save forge-cli-utils`),
  or globally (`npm install --global forge-cli-utils`)
- setup `FORGE_CLIENT_ID` and `FORGE_CLIENT_SECRET` env. vars with your app credentials
- use the following scripts for different Forge services:
  - `forge-dm` - data management
  - `forge-da` - design automation

## Examples

### Data Management

Listing buckets as full JSON:
`forge-dm list-buckets`

Listing object IDs of specific bucket:
`forge-dm list-objects my-test-bucket --short`

Listing object IDs without specifying a bucket (will show
an interactive prompt with list of buckets to choose from):
`forge-dm list-objects --short`

Getting an URN of an object:
`forge-dm object-urn my-bucket-key my-object-key`

### Design Automation

Creating a new app bundle:
`forge-da create-appbundle BundleName path/to/bundle/zipfile Autodesk.Inventor+23 "Bundle description here."`

Updating existing activity:
`forge-da update-activity ActivityName BundleName BundleAlias Autodesk.Inventor+23 --input PartFile --output Thumbnail:thumbnail.bmp`

Creating work item:
`forge-da create-workitem ActivityName ActivityAlias --input PartFile:https://some.url --output Thumbnail:https://another.url --short`

> For additional examples, check out the _tests_ subfolder.

### Model Derivative

Translating a model based on its URN:
`forge-md translate dXJuOmFkc2sub2JqZWN0czpvcy5vYmplY3Q6cG9jLWJvdXlndWVzLWltbW9iaWxpZXIvaW5wdXQucnZ0`

Showing an interactive prompt with all viewables in an URN, and then getting properties of the selected viewable:
`forge-md get-viewable-props dXJuOmFkc2sub2JqZWN0czpvcy5vYmplY3Q6cG9jLWJvdXlndWVzLWltbW9iaWxpZXIvaW5wdXQucnZ0`