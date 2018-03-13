---
published: true
---
## /your-page?msclkid=... URLs in Analytics?

- /example-page
- /example-page?msclkid=vfd4n42ff254512cf
- /example-page?msclkid=4b4934463m4nbv
- /example-page?msclkid=3fkwo34636bv

Seeing something like this in your Google Analytics > Pages report? This is traffic from your Bing ads. I asked their support about it and the response was: 

> What you are seeing is a new feature that released earlier this year. It is designed to assist in accurate conversion tracking. Through Shared Library   URL options  "MSCLKID" it is enabled. This is the feature that is adding the variance to the landing page URL. The reason for the release of this feature is due to some changes made by other entities to their devices. It addresses certain extensions and applets that were disrupting the communication between UET tags and the Bing Ads UI.

To fix this in GA, set up a filter for all your views in Admin > Account > Filters. Use the following regex value for the Search field: **\?msclkid=(.)**
Apply to all of your views and hit save.


![clean-bing.jpg]({{site.baseurl}}/static/img/clean-bing.jpg)

