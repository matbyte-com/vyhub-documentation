# GExtension Import

Check out this [Youtube video](https://www.youtube.com/watch?v=NMRasZqPsTE) if you need any help.

> To use this function, GExtension version **2.7.8 or higher** is required!

## Preparing GExtension

- Make sure that access to the api (at `/api.php`) is possible.
- Disable security measurements, like the Cloudflare "under attack" mode or similar. The API must be available without solving a captcha or additional redirect. For Cloudflare, you can disable this at `Firewall -> DDoS -> HTTP DDoS attack protection -> Configure -> Ruleset sensitivity -> Essentially off`. Make sure to enable it again, after the import has been finished.

- If you want a cleaner VyHub database, you can use the `Cleanup` feature in the `Update` section of GExtension. Everything except the user deletion is safe to use. 
**If you trigger the user deletion, depending objects (like bans, warnings, packets) will not be imported for the deleted users.**

## Preparing VyHub

- Do not create any groups or serverbundles, they will be created during the import process.
- Create all packets, but **no rewards** yet.

## Importing the data

> Only admins can do this.

In the VyHub settings, navigate to `Import` and select the `GExtension` tab, if not already the case.
We will need to do the import process in **four steps**:

1. Import groups, serverbundles and users
2. Import user statistics, bans and warnings
2. Create rewards for the now available serverbundles and assign them to your packets
3. Import applied packets


### 1. Basic Data

| Attribute | Description |
| --- | --- |
| GExtension URL | The URL to your GExtension website, without `index.php` or similar. It should end with a `/`.
| API Key | The API key from your GExtension settings.

### 2. Groups, Serverbundles, Users

> The progress bars show the ratios between the received and the actual imported objects. There are several good reasons why not all objects get imported. You do not have to worry if a progress bar does not reach 100%.

In this step, the actual import process is started.

**Important: Start the process in the following order:**

1. Groups
2. Serverbundles
3. Users

**It is no problem to resume the import process at a later point of time.**

As long as the API url is the same, the same object will not be imported twice, even if the import process is started twice for the same object.

### 3. Further Data

Repeat the previous step with the remaining objects. In this step, there is no fixed order.

### 4. Packets

You can now **create the rewards** for all your packets.
You can also apply rewards to applied packets later using the `Reward Sync` dialog in the reward settings.

> If the list of GExtension packets in the packet translation dialog is empty, check your API URL and key.

| Attribute | Description |
| --- | --- |
| Excluded Rewards | A list of rewards that should not be applied to imported user packets. This can be used to not execute one-time rewards (like in-game cash or similar) again.
| Packet Translations | A list of translations from a GExtension packet to a VyHub packet. All packets that GExtension users have, will be translated to the corresponding VyHub packet that has been selected. Create a translation for every packet you want to import.

After filling in the required information, the import process for the applied packets can be started.

## Checking the result

Check if all data has been imported to VyHub.

If you encounter any problems during the import process, contact our support.

You can repeat the process to import additional packets or other data that came up since the last import. **Make sure to always use the same API URL, otherwise duplicates may occur.**

