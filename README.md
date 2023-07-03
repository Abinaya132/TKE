
# Download recent files from Graph API to temp location

A few sample reference links [https://learn.microsoft.com/en-us/graph/graph-explorer/graph-explorer-overview?view=graph-rest-1.0]
[https://learn.microsoft.com/en-us/onedrive/developer/rest-api/resources/site?view=odsp-graph-online]

## Step 1 
- get SITE ID of Site where the folder  you want to track is present 
```
https://graph.microsoft.com/v1.0/sites/neuron7.sharepoint.com:/sites/{site-name}
```

From the response, get the SITE ID as below 
[!sample output] (image1.png Image1)

## Step 2 
- get the drive of the Site from the SITE ID 

```
GET https://graph.microsoft.com/v1.0//sites/{site-id}/drives

```

From the response, get the DRIVE ID as below 
[!sample output] (image2.png Image2)

## STEP 3 
- From the DRIVE ID, get the list of children of the driveitem , and get the required ID from the response
```
https://graph.microsoft.com/v1.0/drives/{drive-id}/root/children
```

From the response, get the DRIVE ID as below 
[!sample output] (image3.png Image3)

## STEP 4 : 
- From the Drive id and the directory where the incremental files are placed, get list of children using this 
```
https://graph.microsoft.com/v1.0/drives/b!4lh4qqaGo0qFey1vEhWZzM2bDO1hkP9Bi4NMcZzawBrK4ouRTCx3TIpOCPWOZWHa/root:/Test:/children
```

From the response, get the download URL to get the file available in your system which can further be passed to further flows as shown here 
[!sample result] (image4.png Imag4)
