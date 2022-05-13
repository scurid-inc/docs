Scurid platform enables you to deliver files to your IoT edge devices, with specific identity context. Allowing you to manage and transfer different configurations bound to specific identity, even on same device! This brings unique capabilities for your devices in scenarios where devices are shared as a service with variety of end users. Scurid Edge Agent handles this separate configurations and downloads automatically.

### Pre-requisite
1. Scurid Agent on the device must be running
2. Identity for which packages are being downloaded must be already approved.  

## Overview

3. Downloading files

## Step 1 :  Stage the files via Scurid App
1. Log into the app and navigate to the desired approved identity ![approved identity](https://storage.cloud.google.com/scurid/public/docs/images/approvedIdentityForUpload.png){ width=800 }
2. Click on context menu to add the path ![context menu - add path](https://storage.cloud.google.com/scurid/public/docs/images/contextMenuAddPath.png){ width=800 }
Once added path will be displayed on the identity card  ![context menu - add path](https://storage.cloud.google.com/scurid/public/docs/images/approvedIdentityWithPath.png){ width=800 }
3. Click on the the context menu again to click on Upload Package option to upload and stage the files ![context menu - add path](https://storage.cloud.google.com/scurid/public/docs/images/uploadPackage.png){ width=800 }
4. Done.

### Step 2 :  Getting authorized token
1. Scurid edge agent exposes `DownloadFiles` API endpoint, which will download any content from the server
2. To download contents endpoint expects `authorized token`,  `identity` & `path` which is optional. If no path is provided then the contents will be downloaded at default location defined via `-pkg` flag

=== "DownloadFiles"

    === "go"
        ```golang
        // getting the token
        conn, err := grpc.Dial(configs.GRPCServerURL, grpc.WithInsecure())
	        if err != nil {
		    panic(err)
	    }

	    c := scuridEdgeAgentAPI.NewScuridEdgeAgentAPIClient(conn)

	    t, err := c.GetToken(context.Background(), &scuridEdgeAgentAPI.GetTokenReq{Username: did})
	    if err != nil {
		    log.Errorln(err)
		    return
        }
	    ctx := context.Background()
	    metadata.AppendToOutgoingContext(ctx, "authorization", t.GetToken())
	    res, err := c.DownloadFiles(ctx, &scuridEdgeAgentAPI.DownloadFilesReq{
		    Identity: did,
		    Path:     downloadPath,
        })

        ```