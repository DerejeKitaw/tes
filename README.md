### Connect to SharePoint Online
Connect-SPOService -Url "https://yourtenant-admin.sharepoint.com" 

### Create new site
```
New-SPOSite -Url $siteUrl -Owner "user@xxxx.onmicrosoft.com" -StorageQuota 100 -NoWait -Title $siteTitle -Template $siteTemplate
```


### Create multiple sites from `SiteCollections.csv`
> Change SiteCollections.csv location
> 
```sh
Import-Csv C:\SiteCollections.csv | ForEach-Object {New-SPOSite -Owner $_.Owner -StorageQuota $_.StorageQuota -Url $_.Url -NoWait -Template $_.Template -TimeZoneID $_.TimeZoneID -Title $_.Name}
```

###Create single modern team site
```sh
New-SPOSite -Url "https://wplrn.sharepoint.com/sites/Purchase" -Owner "admin@wplrn.onmicrosoft.com" -StorageQuota 2048 -Title "Purchase Team Site" -Template "STS###3"
```
