---
title:  "Amplify push Error - Resource is not in StackUpdateComplete"
date: 2022-12-20 14:38:21 -0500
categories: [Amplify, Tips and Tricks]
tags: [writing]
---

## When pushing to amplify, you might come across an error - <br>
```"["Index: 0 State: {"deploy":"waitingForDeployment"} Message: Resource is not in the state stackUpdateComplete"]"```

Here are a few ways you may fix this - 
#### Option 1. From the s3 bucket for this project, delete the file "deployment-state.json" (make sure to keep a backup copy).
Try pushing again to Amplify.

#### Option 2. If the error persists, locate the cloudformation stack for the Amplify project. Under "Stack actions", select "Detect drift"
    
This should show you which resources are not in sync with the cloudformation stack. This usually happens when admin edits to any of the resources in your amplify project are made from outside of Amplify.
Along with identifying the resources which are drifted, it will also tell you exactly which file has differences in it (Along with the expected file).
Change the actual file to what is expected and check drift again. This should usually remove the drift. 
Try pushing to amplify again.

#### Option 3. Go to the root cloudformation stack for the Amplify project, and look for the exact resource which failed (Status should in red color with "rollback").
    
If you dig deep enough into the exact resource which fails, it will give you the reason for why it is failing. For example, I was trying to add an index to an already existing table. I went to the datasdk cloudformation stack. In the events tab, I scrolled until I found the reason for the rollback, which was the Deck table. The error message basically said that the read/write capacity units were not enough. 
This was because the "Deck" table was in "provisioned" mode. After changing to "On-demand", the amplify push worked (it took a long time though).