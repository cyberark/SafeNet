# Pre made configurations for SafeNet


<!-- Table for the different configurations, headers are Router OS, VPN provider name, Region, file link (from configurations folder), Contributor name -->

| Router OS | VPN Provider | Region | File | Contributor |
| --- | --- | --- | --- | --- |
| pfSense | NordVPN | DE | [SafeNet.pfSense.NordVPN.DE.xml](configurations/pfSense/SafeNet.pfSense.NordVPN.DE.xml) | David El|
<!-- | pfSense | NordVPN | US | [SafeNet.pfSense.NordVPN.US.xml](configurations/pfSense/SafeNet.pfSense.NordVPN.US.xml) | David El|
| pfSense | NordVPN | UK | [SafeNet.pfSense.NordVPN.UK.xml](configurations/pfSense/SafeNet.pfSense.NordVPN.UK.xml) | David El| -->


## How to contribute
The best way to contribute to the SafeNet project is by adding pre made configurations for VPN providers that are not in the table above, this helps new users with setting up their router fast and lowers the entry barrier substantially! <br>
For the most part, VPN providers have a detailed guide on how to set up their VPN service on routers like pfSense, and you can find them easily by searching for "\<VPN Provider> \<Router OS>" (e.g. [NordVPN pfSense](https://www.google.com/search?q=NordVPN+pfSense)) on your favorite search engine.

Start by taking an already existing configuration file like [SafeNet.pfSense.NordVPN.DE.xml](configurations/pfSense/SafeNet.pfSense.NordVPN.DE.xml), import it, and change the VPN provider name, region and file name to match the new configuration.<br>
Dont forget to either export your current configuration or take a snapshot of your virtual machine before importing the new configuration, just in case something goes wrong.

The reasoning behind taking an already existing configuration is for uniformity, and to ensure that no sensitive information is left in the configuration file.

Once you've imported the configuration file, change the VPN details as described in the VPN provider guide, and test that it works. If it works, follow the steps bellow to add the configuration to SafeNet:

1. Fork the SafeNet repository
2. Export the configuration file from your router (for pfSense it is located in Diagnostics -> Backup & Restore -> Export Configuration)
3. Remove any sensitive information from the file, like passwords, usernames, etc. <b>Make sure to remove the VPN login details before committing the file!</b>
4. Use the naming scheme of <b>SafeNet.\<Router OS>.\<VPN Service>.\<Region>.xml</b> for the file name, for example <b>SafeNet.pfSense.NordVPN.DE.xml</b> with region being the region of the VPN server you are connecting to.
5. Add the file to the appropriate <b>configurations</b> folder, and update the PreMadeConfigurations.md file with the new configuration
6. Commit the changes to your forked repository and create a pull request to the main repository
