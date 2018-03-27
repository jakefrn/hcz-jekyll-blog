---
published: false
---
## Troubleshooting: When GA 'New Users' is greater than FB Campaign's 'Link Clicks'

There's already a very [helpful article](http://www.stateofdigital.com/facebook-ads-google-analytics-data-mismatch/) about reasons for differences in reported traffic between these platforms, but each of the scenarios described are when traffic in Google Analytics in LESS than Facebook's reported Link Clicks for a campaign. In my case I was seeing the opposite- more New Users in GA coming from "facebook / cpc" than FB's reported Link Clicks, how could this be possible?

![facebook-analytics-1.jpg]({{site.baseurl}}/_posts/facebook-analytics-1.jpg)

Assuming you're using UTM parameters in your FB ad sets, it's possible that this UTM-tagged URL is now "out there" being shared on other sources (e.g. linked on another website, in an email newsletter, etc.). So when someone clicks on it, off of Facebook, GA now attributes that new user as "source=facebook" and "medium=cpc." You can investigate this potential issue by creating a custom segment in GA with source/medium set to "facebook / cpc" (or whatever convention your UTM was manually configured to), then pulling up the "Referral Traffic" report. 

In my case, there was nothing under the Referral report, so with same segmented audience still applied in GA, I drilled into the "Geo > Location" report, and found a 33% of New Users were actually coming from the country of Peru (and few dozen from Philippines) even though my FB campaign did not have any South American or Asian countries targeted. After posting my findings in the #Measure Slack (a community for analytics and SEM), it was pointed out by [@williamvicary](https://medium.com/@williamvicary) that Facebook filters out link clicks from bots; while GA does not (or at least, not exactly the same way). So subtracted those 80ish spam "users" gets me 110 New Users in GA which is close enough (for me) to what FB was reporting.




