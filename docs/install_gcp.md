# Deploying Trains Server on Google Cloud Platform

To easily deploy Trains Server on GCP, use one of our pre-built GCP Custom Images.  
We provide Custom Images for each released version of Trains Server, see [Released versions](#released-versions) below. 

Once your GCP instance is up and running using our Custom Image, [configure the Trains client](https://github.com/allegroai/trains/blob/master/README.md#configuration) to use your **trains-server**.  
The service port numbers on our Trains Server GCP Custom Image are:

- Web application: `8080`
- API Server: `8008`
- File Server: `8081`

The persistent storage configuration:

- MongoDB: `/opt/trains/data/mongo/`
- ElasticSearch: `/opt/trains/data/elastic/`
- File Server: `/mnt/fileserver/`

For examples and use cases, check the [Trains usage examples](https://github.com/allegroai/trains/blob/master/docs/trains_examples.md).

## Importing the Custom Image to your GCP account

In order to launch an instance using the Trains Server GCP Custom Image, you'll need to import the image to your custom images list.

**Note:** there's **no need** to upload the image file to Google Cloud Storage - we already provide links to image files stored in Google Storage

To import the image to your custom images list:
1. In the Cloud Console, go to the [Images](https://console.cloud.google.com/compute/images) page.
1. At the top of the page, click **Create image**.
1. In the **Name** field, specify a unique name for the image.
1. Optionally, specify an image family for your new image, or configure specific encryption settings for the image.
1. Click the **Source** menu and select **Cloud Storage file**.
1. Enter the Trains Server image bucket path (see [Trains Server GCP Custom Image](#released-versions)), for example:
    `allegro-files/trains-server/trains-server.tar.gz`
1. Click the **Create** button to import the image. The process can take several minutes depending on the size of the boot disk image.

For more information see [Import the image to your custom images list](https://cloud.google.com/compute/docs/import/import-existing-image#import_image) in the [Compute Engine Documentation](https://cloud.google.com/compute/docs).

## Launching an instance with a Custom Image

For instructions on launching an instance using a GCP Custom Image, see the [Manually importing virtual disks](https://cloud.google.com/compute/docs/import/import-existing-image#overview) in the [Compute Engine Documentation](https://cloud.google.com/compute/docs).
For more information on Custom Images, see [Custom Images](https://cloud.google.com/compute/docs/images#custom_images) in the Compute Engine Documentation.

The minimum recommended requirements for Trains Server are:
- 2 vCPUs
- 7.5GB RAM

## Upgrading

To upgrade **trains-server** on an existing GCP instance based on one of these Custom Images, SSH into the instance and follow the [upgrade instructions](../README.md#upgrade) for **trains-server**.

## Released versions

The following sections contain lists of Custom Image URLs (exported in different formats) for each released **trains-server** version.

### Latest version image (v0.14.1)

- https://storage.googleapis.com/allegro-files/trains-server/trains-server.tar.gz
