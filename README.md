# OVP Migration Flow

**Status:** Production

**Tools:** Python

**Input:** Media assets and descriptive metadata in source OVP.

**Output:** Media assets and descriptive metadata in destination OVP.

## Description

This document outlines an agnostic blueprint for migrating video content from any Source On-line Video Platform (OVP) to a Destination OVP.

## Purpose

The purpose of this document is to outline a generic blueprint for the migration of video content from any Source On-line Video Platform (OVP) to a Destination OVP. This blueprint provides a high-level overview of the key steps and considerations involved in such a migration process.

## Context

In the context of digital content migration, this blueprint serves as a guide for initiating the transition from one OVP to another. It emphasizes the importance of retrieving video information from the source platform, including metadata extraction and potential deletion of content. The document sets the stage for a seamless migration process, aligning with the API documentation and specifications of the destination OVP.

## Workflow

![image](https://github.com/user-attachments/assets/1c73b11a-6b31-4cbe-b593-7fa4894942f4)


1.  **Retrieve Video Information from Source OVP:**
    * Make a `GET` request to the Source OVP's API.
    * Authenticate using an access token and video ID.
    * Target a generic API endpoint.
2.  **Extract Video Metadata:**
    * Parse the API response (typically XML or JSON).
    * Extract metadata:
        * Title
        * Description
        * Tags
        * Download link for the highest quality version.
3.  **Download Video Asset:**
    * Use the extracted download link to download the video.
4.  **Optional: Delete Video from Source OVP:**
    * Provide the user with an option to remove the video from the Source OVP.
5.  **Ingest into Destination OVP:**
    * Follow the Destination OVP's API documentation and specifications.
    * Upload the video asset and associated metadata.
6. **Error Handling:**
    * Handle thumbnail creation errors. Example error: "Error creating thumbnail: Unable to save thumbnail to destination"


## Example OVP API Documentation Sources

* **YouTube:**
    * Source: [1]
    * Documentation URL: [YouTube Data API Documentation](https://developers.google.com/youtube/docs)
    * Description: YouTube provides a Data API that allows developers to access YouTube's features programmatically. It covers functionalities related to video uploads, playlists, video information retrieval, and more.
* **Vimeo:**
    * Source: [2]
    * Documentation URL: [Vimeo API Documentation](https://developer.vimeo.com/)
    * Description: Vimeo's API documentation offers resources for integrating Vimeo's video hosting and sharing capabilities into applications. It provides access to features like video upload, video information retrieval, and advanced privacy controls.
* **Kaltura:**
    * Source: [3]
    * Documentation URL: [Kaltura Developer Documentation](https://developer.kaltura.com/)
    * Description: Kaltura's Developer Documentation provides extensive resources for developers to leverage Kaltura's video platform capabilities. It covers video management, publishing, and monetization, as well as features like video uploading, player customization, and analytics.
* **Brightcove:**
    * Source: [4]
    * Documentation URL: [Brightcove API Documentation](https://apis.support.brightcove.com/)
    * Description: Brightcove's API documentation provides comprehensive resources for developers to interact with the Brightcove platform programmatically. It includes features related to video publishing, content management, player customization, analytics, and monetization.
