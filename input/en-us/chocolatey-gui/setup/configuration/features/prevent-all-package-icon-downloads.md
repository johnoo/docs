---
Order: 130
xref: prevent-all-package-icon-downloads
Title: Prevent All Package Icon Downloads
Description: Allows control over whether an attempt is made to download icons associated with packages.
---

By default, when using the [DefaultToTileViewForLocalSource](xref:default-to-tile-view-for-local-source), [DefaultToTileViewForRemoteSource](xref:default-to-tile-view-for-remote-source), or the [ShowAdditionalPackageInformation](xref:show-additional-package-information) features, Chocolatey GUI will attempt to download the icon for the package from the URL that is defined within the nuspec file for the package.  For the most part, this works without any problems, however, when being used within an air gapped network, with no internet access, the end result looks like this:

![Showing what happens when Chocolatey GUI runs with no external internet access](/assets/images/chocolatey-gui/feature_prevent_all_package_icon_downloads_1.png "Showing what happens when Chocolatey GUI runs with no external internet access")

With the PreventAllPackageIconDownloads feature enabled, no attempt will be made to download the icon associated with the package, and instead the default Chocolatey icon will be used for each package.  The result being the following:

![Showing what happens when Chocolatey GUI runs with no external internet access with PreventAllPackageIconDownloads enabled](/assets/images/chocolatey-gui/feature_prevent_all_package_icon_downloads_2.png "Showing what happens when Chocolatey GUI runs with no external internet access with PreventAllPackageIconDownloads enabled")

> :memo: **NOTE**
>
> This is a Chocolatey for Business feature, and will require install of the [Chocolatey GUI Licensed Extension](xref:chocolatey-gui-licensed-extension)

> :memo: **NOTE**
>
> If Chocolatey GUI has been run before enabling this feature, make sure to [purge any existing icons](xref:gui-purge-icons) that may have been cached

## Resources

Below is a short video which shows this feature in action:

## Example

This feature can be enabled, for the currently logged in user, by running the following command:

```powershell
chocolateyguicli feature enable --name="'PreventAllPackageIconDownloads'"
```

This feature can be disabled, for the currently logged in user, by running the following command:

```powershell
chocolateyguicli feature disable --name="'PreventAllPackageIconDownloads'"
```

Or, to enable/disable it globally at the machine level, run the following commands:

```powershell
chocolateyguicli feature enable --name="'PreventAllPackageIconDownloads'" --global

chocolateyguicli feature disable --name="'PreventAllPackageIconDownloads'" --global
```

## Default Value

The default value for this feature is disabled.

## Availability

The ability to control this feature from the Chocolatey GUI Settings screen has existed since Chocolatey GUI v0.18.0.

The ability to control this feature from the command line using `chocolateyguicli` has existed since Chocolatey GUI
v0.18.0.