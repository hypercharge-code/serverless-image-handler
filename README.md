## Current usage
This is currently deployed and used in projects like bbs, machineland and gefco.
The urls are:
 - Staging: https://images.hyper1.net
 - Prod: https://7d6lx8wx33.execute-api.eu-west-1.amazonaws.com/image
 
Retrieving an image can be done using a function like this:
```
export const getImageUrl = (imageId: string | string[], width?: number, height?: number): string =>
  `${process.env.REACT_APP_IMAGES_ENDPOINT}/${btoa(
    JSON.stringify({
      key: `machineland/${imageId}`,
      edits: {
        resize: {
          width,
          height,
          fit: 'inside',
          withoutEnlargement: true
        }
      }
    })
  )}`;
  
```

Copyright 2019 Amazon.com, Inc. or its affiliates. All Rights Reserved.

Licensed under the Amazon Software License (the "License"). You may not use this file except in compliance with the License. A copy of the License is located at

    http://aws.amazon.com/asl/

or in the "license" file accompanying this file. This file is distributed on an "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, express or implied. See the License for the specific language governing permissions and limitations under the License.
