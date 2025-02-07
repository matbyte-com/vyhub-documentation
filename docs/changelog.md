# Changelog

## v3.0.0-beta7

Released: 2025-02-07

> This is a beta release. The frontend may contain bugs, the backend is stable. Please report all issues that you encounter.

**Backend:**

- Fix double notifications when having more than 2 accounts linked together
- Improve error message when TS3 credentials are missing
- Fix PayPal subscriptions not working without customer address
- Update dependencies

**Frontend:**

- Improve position of help icon in forms
- Add descriptions for the GMOD reserved slots feature
- Fix setting secret values in server form (like TS3 username/password) not possible
- Improve server form and add option to disable GMOD ban sync

**On-Prem:**

- The docker image now uses alpine and is smaller now

**Update notes:**

- If you are using vyhub-gmod, make sure to update to [version 2.0.9](https://github.com/matbyte-com/vyhub-gmod/releases)

## v3.0.0-beta6

Released: 2025-01-26

> This is a beta release. The frontend may contain bugs, the backend is stable. Please report all issues that you encounter.

**Frontend:**

- Fix a problem with the welcome overlay that could not be clicked away


## v3.0.0-beta5

Released: 2025-01-26

> This is a beta release. The frontend may contain bugs, the backend is stable. Please report all issues that you encounter.

**Frontend:**

- Fix problems with some missing form elements (ending memberships, webhook url, ...)
- Fix a problem with homepage builder form (editing mode exited too early)
- Fix a problem with doubled notifications
- Improve performance of the shop page

## v3.0.0-beta4

Released: 2025-01-21

> This is a beta release. The frontend may contain bugs, the backend is stable. Please report all issues that you encounter.

**Frontend:**

- Fix server-side table pagination

## v3.0.0-beta3

Released: 2025-01-19

> This is a beta release. The frontend may contain bugs, the backend is stable. Please report all issues that you encounter.

**Frontend:**

- Fix homepage builder
- Fix reward settings
- Fix payment gateway settings
- Smaller improvements

## v3.0.0-beta1

Released: 2025-01-16

> This is a beta release. The frontend may contain bugs, the backend is stable. Please report all issues that you encounter.

**Frontend:**

- Update the frontend framework from Vue 2 to Vue 3
- Add Shop-only mode
- Add Theme picker with import/export functionality
- Add the ability to hide avatars of specific users
- Replace WYSIWYG editor with a new one, now allows tables and HTML editing
- Allow specifying a purchase amount limit for address-free purchases
- Disable user attribute chart animations for charts with more than 365 data points
- Limit length of address fields
- Fix the ASA download link
- Visual improvements of Forum
- Various improvements

**Backend:**

- Add Teamspeak3 channel reward
- Limit length of address fields
- Mark rewards with a server limit as executed if executed on all servers
- Send invoices as email attachment
- Fix problems with too long bans
- Improve the reward retry mechanism
- Remove packet `abstract` field
- Sort user purchases correctly by date

## v2.2.4

Released: 2024-07-30

API/Web:

- [API] Improve PayPal logging
- [API] Remove usages of non-existing `user_show` property
- [WEB] Improve server setup dialog
- [WEB] Fix notification link for news


## v2.2.3

Released: 2024-07-10

API/Web:

- [API] Fix paysafecard integration not working when using certificate auth
- [WEB] Add option to hide statistic widgets on the shop page


## v2.2.2

Released: 2024-07-03

Web:

- [WEB] Fix editing rewards in non-advanced mode not possible
- [WEB] Improve CMS edit dialog
- [WEB] Fix navigation links pointing to the same domain but other subdomain
- [WEB] Improve FIVEM setup and reward templates
- [WEB] Fix some form elements sometimes not saving data correctly

FiveM:

- Released version [2.2.0](https://github.com/matbyte-com/vyhub-fivem/releases)
    - Add support for QBCore and FiveM vanilla
    - Further improvements
    - **Breaking:** The reward string replacement `%esx_name%` has been renamed to `%char_name%`

## v2.2.1

Released: 2024-05-07

Web/API:

- [API] Fix creating/editing memberships took too long with many registered users
- [API] Update Discord server status on restart
- [Web] Smaller improvements

## v2.2.0

Released: 2024-05-01

Web/API:

- [API] Improve performance of user groups and permissions (everything should be faster now)
- [API] Add more [replacements](guide/shop/reward.md#variable-replacements) for HTTP rewards (`%user_type%` and `%user_identifier%`)
- [API/Web] Add support for [Source RCON servers](game/source.md)
- [API/Web] Add option to limit rewards to specific servers
- [API/Web] Add support/feedback form to settings
- [Web] [Forum] Improve forum admin feature
- [Web] Fix regex of HTTP links
- [Web] Smaller design improvements and more in-line help

## v2.1.3

Released: 2024-04-03

Web/API:

- [API] Add translated emails
- [API] Reduce notification/email interval from 10 to 5 minutes
- [API] Fix wrong access control check in `/v1/user/address/{uuid}` endpoint
- [API/Web] Add group protection option
- [API/Web] Improve first steps guide
- [API/Web] Allow selfhosted frontend when using VyHub Cloud
- [Web] Improve some icons
- [Web] Smaller visual improvements and bugfixes

Garry's Mod (vyhub-gmod 2.0.5):

- Fix changing of a players group not always working
- Fix problem with too long ban time
- Add proper error message when language files are missing
- Remove color tags before printing to server console

## v2.1.2

Released: 2024-03-26

Web/API:

- [API] Improve performance of Discord and Ts3 bot
- [API/Web] Add option to delete users (Beta)
- [API/Web] [Forum] Show avatars in reactions list
- [Web] [Forum] Correctly show admin badge for forum admin groups
- [Web] Show new `vh_setup` command for GMOD servers
- [Web] Correctly reload user after removing update status
- [Web] Update translations

VyHub.net:

- Add `serverstore.io` as available subdomain for VyHub instances

## v2.1.1

Released: 2024-03-13

Web/API:

- [API/WEB] Add option to enable an alternative shop view (list view within a category)
- [API/WEB] Add option to show a news text on the shop page
- [WEB] [Forum] Remove delete button from first post
- [WEB] [Forum] Fix reactions not working in some special situations
- [WEB] Small design improvements
- [WEB] Fix editing packets sometimes not working in advanced mode

## v2.1.0

Released: 2024-03-10

Web/API:

- [API] Update supported stripe version to 2023-10-16
- [API/WEB] Add option to make comments viewable for the user
- [API/WEB] Add new add-on for branding removal
- [API/WEB] [Forum] Add option to configure admin users for a topic
- [API/WEB] [Forum] Add group label to users posts
- [API/WEB] [Forum] Add forum statistics to the user dashboard
- [API/WEB] [Forum] Add last forum activities to user dashboard
- [API/WEB] [Forum] Deleting of posts is now allowed (when edit_post setting is enabled)
- [WEB] [Forum] Improve responsiveness of Forum
- [WEB] Fix "new users" widget not working correctly
- [WEB] Improve dashboard design

## v2.0.19

Released: 2024-02-25

Web/API:

- [API] **`GET /user`  endpoint now is paginated**
- [API] `GET /user` can now sort by last online date  
- [API] `GET /user` now only returns users that match the query
- [API] Improve mail sending
- [API] Fix forum addon not correctly disabled
- [API|WEB] Show non-secret payment gateway attributes
- [WEB] Add dedicated search page
- [WEB] Add default images for shop categories and packets
- [WEB] Improve user quick-search
- [WEB] Improve quickstart guide
- [WEB] Fix profile menu not shown on small screens
- [WEB] Add instruction video for minecraft login
- [WEB] Smaller visual improvements

Update notes:

- The `GET /user` endpoint now returns a paginated result which may breaks
existing implementations. (Only relevant for custom API integrations)

## v2.0.18

Released: 2024-02-13

Web/API:

- [API] Fix problems with mails being sent multiple times
- [API] Heavily improve server dashboard performance
- [API] Heavily improve ban performance
- [API] Add regular sync of steam user data
- [WEB] Improve layout of the property chips in the group settings

## v2.0.17

Released 2024-01-22

Web/API:

- [WEB] Open credits history when clicking on credits in header
- [WEB|API] Limit length of forum thread

## v2.0.16

Released 2024-01-16

VyHub now support **Ark Survival Ascended (ASA)**

Web/API:

- [WEB|API] Add Ark Survival Ascended to VyHub

## v2.0.15

Released 2023-12-25

Web/API:

- [API] Fix problem with gameserver requests being rate limited (code 429)
- [API] Performance and stability improvements

## v2.0.14

Released 2023-12-21

VyHub now supports **7 Days To Die**

Web/API:

- [WEB|API] Add 7 Days to Die support to VyHub

## v2.0.13

Released: 2023-12-15

Web/API:

- [API] PayPal: Fix subscription payments (broken due to a PayPal API change)
- [WEB] Correctly hide servers widget on mobile when no servers are configured
- [WEB] Refresh servers widget when news page is loaded

Update notes:

- It is **HIGHLY** recommend to install this update if you are using **PayPal Subscription Payments**


## v2.0.12

Released: 2023-12-12

Web/API:

- [WEB] FiveM: Change displayed login command to /vylogin


## v2.0.11

Released: 2023-12-12

Web/API:

- [WEB|API] Add option to edit warnings
- [WEB|API] Add option to delete tickets
- [WEB|API] Add option to hide servers
- [API] Add Discord notification after new ticket
- [API] Add issuer option to Discord notifications

## v2.0.10

Released: 2023-12-08

Web/API:

- [API] Fix PayPal (Easy) payment gateway not using correct cart packet prices
- [API] Fix problem with applying packets when the packet should upgrade itself


## v2.0.9

Released: 2023-12-06

Web/API:

- [API] Fix pending stripe subscription payments are not processed if the according option is set
- [API] Fix applied packet directly disables itself if configured so
- [WEB] Fix purchase status translation error

## v2.0.8

Released: 2023-11-24

VyHub self-hosting (on-prem) is out! You can now host VyHub on your own server.

Web/API:

- [API] Disable steam login when no steam gameserver is configured
- [API|WEB] Use category names instead of ID's in categories
- [WEB] Open login dialog when adding packets to cart and not logged in
- [WEB] Homepage builder: headlines in dark-mode
- [WEB] Homepage builder: Add ability to open custom header links in new tab
- [WEB] Sort servers in server status alphabetically
- [WEB] Add account overview to cart

## v2.0.7  

Released: 2023-11-19

Web/API:

- [WEB] Enable Rust dashboard
- [WEB] Improve navigation settings (Navigation sublink icons and title)
- [WEB] Redirect from /home to /news when page-builder is disabled

## v2.0.6

Released: 2023-11-14

VyHub now supports Rust.  

Web/API:

- [API] Add [PayPal (easy)](guide/shop/payment_gateway.md) payment gateway
- [WEB|API] Add support for Rust

## v2.0.5

Released: 2023-10-22

Web/API:  

- [API] Show user logs and comments also for all linked users
- [WEB] Small visual improvements


## v2.0.4  

Released: 2023-10-12  

Web/API:  

- [WEB] Fix color menu shown behind the design sidebar
- [API] Ability to handle precreated servers through partners

## v2.0.3  

Released: 2023-10-05  

Web:  

- [WEB] Fix generation of commands that are shown for Minecraft server setup  
- [WEB] Disabled categories are no longer shown on category page  

## v2.0.2  

Released: 2023-10-05

Web/API:  

- [WEB|API] Add option to limit top-donators to a specific timerange (e.g. show the top donators of the last 30 days)
- [WEB] Fix an issue where `Add Post` button in forum was not shown
- [WEB] Improve the horizontal scroll bar and fix an issue where the scroll bar was not shown on Chrome
- [API] Fix an issue with the last-purchases widget where not only the last purchases where shown  

## v2.0.1

Released: 2023-09-29

Web/API:  

- [WEB] Fix an issue with account linking
- [WEB] Fix the displaying of forum threads
- [WEB] Add the option to use the default header in the page-builder

## v2.0.0

Released: 2023-09-26  

Web/API:  

- [WEB] Update frontend design (UI) and user experience (UX)
- [WEB|API] Add homepage builder
- [WEB|API] Add forum reactions
- [WEB|API] Add forum labels
- [WEB|API] Improve user linking


FiveM (v2.0.0)  

- Add FiveM support to VyHub  


Minecraft (v2.0.0)  

- Move `/login` command to `/vylogin`
- Improve user registration when server is set to `offline` mode


Update notes:    
- The Minecraft Plugin must be updated to be able to work with the new `/vylogin` command   
- The new homepage builder is disabled by default. You can enable it in the theme settings

## v1.5.13

Released: 2023-08-12

Web/API:

- [API] Discord: Improve error handling and add better logging
- [API] Improve sending of emails
- [API] Fix subscription cancellations were not working since 1.5.12
- [WEB] Fix failing permission check on server dashboard
- [WEB] Smaller design improvements


## v1.5.12

Released: 2023-08-04

- [WEB] Fix bug when adding a group was not possible due to advanced settings mode
- [WEB] Fix bug when editing navigation-sublinks
- [WEB] Improve design of recommended packets in cart
- [WEB|API] Add restart button for Teamspeak integration
- [API] Improve Teamspeak startup and logging

## v1.5.11

Released: 2023-08-01

- [WEB|API] Add recommended packages to cart view
- [WEB|API] Add ability to ban people from website using negated properties (`shop_use`, `forum_post`, `ticket_create`)
- [WEB|API] Add ability to set custom name for the credits
- [WEB|API] Add ability to set custom images for payment-gateways
- [WEB|API] Add advanced mode
- [API] Send abandoned cart follow-up mail  
- [API] Improve server-dashboard performance
- [WEB] Improve translations

Update notes:

- Some options are now considered advanced. Activate the `Show advanced settings` option to see them again.
- Website bans: the website ban group needs to be added manually. Just add it and give it the respective negative properties (advanced_settings_mode must be enabled)

## v1.5.10  

Released: 2023-07-17  

- [WEB] Raise max HTML character length
- [WEB|API] Add HTTP-Rewards

## v1.5.9  

Released: 2023-07-16

- [WEB] Fix edit forum post

----

Released 2023-07-13

Minecraft (v1.5.1)

- Fix creation of config-file after startup
- Add BungeeCord support
- Add Velocity support

## v1.5.8  

Released: 2023-07-10

- [WEB|API] Support for custom CSS
- [WEB] Improve team-page when avatar is not found

Minecraft (v1.5.0):

- Add support for Bukkit/Spigot/Paper versions from 1.12+ with Java 8+
- Remove strict LuckPerms requirement (Only disable group-sync, when LuckPerms is not found)
- Add internationalization

## v1.5.7

Released: 2023-07-05

- [WEB|API] Add option to prohibit users from creating threads in topics
- [WEB|API] Threads without posts are now displayed in frontend as well
- [API] Fix creation of bans with game-plugins under some circumstances

## v1.5.6

Released: 2023-07-04

- [WEB] Fix forum thread view when logged in under some circumstances
- [API|WEB] Add requirement set tester to test requirements sets against users
- [API] Improve handling of requirement sets when no formula or wrong formula is set

## v1.5.5

Released: 2023-06-25

Web/API:

- [API] Change default currency to EUR
- [API] Disable "all packets" option when creating a discount with packets specified
- [API] Fix GExtension group import
- [API] Improve E-Mail template
- [API] Various performance improvements
- [API|WEB] Add option to unlink accounts (for admins)
- [API|WEB] Add option to add Google Analytics tag
- [API|WEB] Fix problems with theme colors
- [Web] Add beginner guide
- [Web] Fix group form
- [Web] Fix user/ban comment spacing
- [Web] Fix forum thread view when not logged in
- [Web] Improve mobile view of home/news page
- [Web] Improve mobile view of log page
- [Web] Improve server dashboard
- [Web] Improve "no data" message
- [Web] Improve link user dialog

Garry's Mod (v1.5.1):

- Performance improvements
- Add options to limit execution of reward scripts/commands
- Add options to disable ban/group sync

Update notes:

- vyhub-gmod v1.5.1 disables the execution of Lua script rewards by default. Script execution can be enabled in the `sv_config.lua` or by executing this command in the server console: `vh_config reward_disable_scripts false`
    - Script execution will be kept enabled if `sv_config.lua` is not replaced during update 

## v1.5.4

Released: 2023-06-14

Web/API:

- [API] Discord: Remove bot started log message
- [API] Discord: Improve error handling
- [API] Sync Discord/Ts3 groups on first login
- [WEB] Discord: Add button to restart bot
- [WEB] Fix button to edit a users credits was not visible
- [WEB] Fix ban details could not be seen when not logged in
- [WEB] Improve mobile view of new users


## v1.5.3

Released: 2023-06-10

Web/API:

- [API] Fix creation of bans under some circumstances
- [WEB] Show groups on user dashboard at all time

## v1.5.2

Released: 2023-06-09

Web/API:

- [API|WEB] Add `maximum ban length` property to groups  
- [WEB] Add in-game purchase notification to reward templates

Discord:

- Add chat notifications. All settings regarding the chat notification are done through Discord by interacting with the bot.

## v1.5.1

Released: 2023-06-05

Web/API:

- [API] Fix creation of groups
- [WEB] Fix select all property btn on group creation

## v1.5.0

Released: 2023-06-04

Web/API:

- [API|WEB] Rework Logs. Logs are now saved on a dedicated logging-server and are better tagged.
- [API|WEB] Add user and ban comments
- [API|WEB] Add further and improve existing shop statistics
- [WEB] Add reward presets. Presets can be used out of the box are may inspire your own rewards.
- [WEB] Improve FAQ design

Teamspeak Integration:

- Use additional ssh query port field for connection to server.
- Use existing port to create the connection link on the homepage.

Update notes:

- Due to the restructuring of the logs, old logs are not available in the UI. Old logs can be downloaded at the bottom of the logs page.

## v1.4.6

Released: 2023-05-12

Web/API:

- [API|WEB] Add ability to add rewards to already applied packets.
- [WEB] Add embed video functionality to editor (only for admins)
- [WEB] Fix field to remove image-url of packets

## v1.4.5

Released: 2023-05-07

Web/API:

- [API] Improve performance of ban and warn endpoints
- [WEB] Fix removing of nav icons not working
- [WEB] Fix open graph tags for high available instances

## v1.4.4

Released: 2023-05-06

Web/API:

- [WEB] Add ability to specify external ban-protest URL
- [WEB] Shop: Add option to show packet title over packet image
- [API] Add `GET /ban/{uuid}` endpoint
- [API] Add `GET /warning/{uuid}` endpoint
- [API] Fix user attribute history missing entries for days without value in some cases
- [API] Fix missing translations for invoices
- [API|WEB] Make serverbundles sortable
- [API|WEB] Update translations

## v1.4.3

Released: 2023-05-02

Web/API:

- [API] Fix number of top-donators returned by API
- [WEB] Add ability to specify number of top-donators for widget
- [WEB] Add ability to search for users using SteamID32
- [WEB] Add ability to set open graph tags for instance

Update notes:
  - There is no migration for your community description and favicon
    - Please set them to your desired values in the settings manually.

## v1.4.2

Released: 2023-04-24

Web/API:

- [API] Fix notification mails
- [WEB] Add top-donator widget
- [WEB] Add ability to specify custom text for donation goal and top-donator widgets
- [WEB] Improve responsiveness of header

Garry's Mod:

- [Server] Improve HTTP error messages

Minecraft: 

- [Server] Fix error for new players and on VyHub user creation

Update notes:

- The following game integrations can be updated:
    - Garry's Mod -> v1.4.2
    - Minecraft -> v1.4.1

## v1.4.1

Released: 2023-04-09

Web/API:

- [API] Forum: Fix post count
- [API] Fix error when trying to delete a serverbundle with existing warnings
- [API] Fix team page

Garry's Mod:

- [Client] Fix server dashboard icons
- [Server] Fix error for new players and on VyHub user creation
- [Server] Smaller improvements

Update notes:

- The following game integrations can be updated:
    - Garry's Mod -> v1.4.1

## v1.4.0

Released: 2023-04-05

Central:

- VyHub instances are now free to use, [but paid with a small revenue commission](central/account.md) 
- Add VyHub Balance panel
- Add Affiliate panel

Web/API:

- [API] Add `DELETE /user/{uuid}/membership/by-group` endpoint: Remove a group membership of a user by using a group id
- [API] Improve search for log entries
- [API|Web] Add new add-on: [Forum](guide/forum.md) 
- [API|Web] Add Teamspeak integration
- [API|Web] Add translated invoices
- [API|Web] Add option to buy packets for other users
- [API|Web] Improve reordering of shop packets
- [API|Web] Discord: Add option to use role-ids in group mappings
- [Web] Add option to duplicate packets
- [Web] Add discount code generator
- [Web] Add option to select all properties when creating / editing groups
- [Web] Add pagination for the payments of a purchase
- [Web] Add secondary color
- [Web] Improve table colors for bans, warnings, tickets and on the server dashboards


Update notes:

- **Important:** Our terms of service have changed to reflect the changes in the pricing of instances. Therefore, the next time you extend your instance, you need to agree to our new terms of service and privacy policy.

## v1.3.4

Released: 2022-12-29

Web/API:

- Fix invoice generation not working sometimes
- Fix navigation sublinks sometimes not deletable
- Stripe: Add more payment gateways
- Stripe: Add more payment gateways for subscriptions

## v1.3.3

Released: 2022-12-20

Web/API:

- Display exact amount when showing the donation goal progress
- Make new server API keys to use the `integration_token` property
- Regulary check for new subscription payments
- Fix 500 error that could happen when creating a membership
- Fix legal page not working on a new instance
- Fix footer and page title not working on first visit of the webpage
- Rework GeoIP
- Update translations

Garry's Mod:

- Fix warning reason not correctly transmitted when using the in-game dashboard
- Fix problems with `ply:SetUserGroup` when no admin addon is used
- Improve some console messages

## v1.3.2

Released: 2022-12-04

Web/API:

- Fix problem where ban-protests could not be created

## v1.3.1

Released: 2022-11-26

Web/API:

- Fix problem with new navigation settings (making changes was not possible)
- Improve design of navigation settings

Garry's Mod:

- Add german translation
- Fix loading problem of in-game dashboard

Update notes:

- **Important:** Due to a problem with the latest update, the admin menu in the navigation is visible for all users. To
  fix this, go to the navigation settings, edit the admin menu entry and insert `admin_menu` as required property.
  ***This problem only occurs when the instance has been upgraded from 1.2.x to 1.3.0.***

## v1.3.0

Released: 2022-11-23

Web/API:

- Improve navigation settings by allowing to create sub-menus and by limiting access with requirement sets.
- Make it possible to add navigation links to footer and help-menu
- Fix icon picker

Garry's Mod:

- Add warning/ban dashboard for Garry's Mod (`!dashboard`)
- Make it possible to translate on [translate.matebyte.com](https://translate.matbyte.com/projects/vyhub/vyhub-gmod/).
  More parts will be translatable soon.
- Improve ban/warn messages

Update notes:

- If you have used custom navigation links in the past, they will be resetted to a default value.
    - Your custom HTML pages won't be lost, but they need to be linked again.
- The following game integrations need to be updated:
    - Garry's Mod -> v1.3.0

## v1.2.1

Released: 2022-10-22

- Improve packet images and titles
- Only display serverbundles on the home page that contain servers
- Fix error when importing GExtension statistics
- Fix paysafecard certificates

## v1.2.0

Released: 2022-10-09

- Add easier server setup process
- Add packet subcategories
- Add support for custom packet price
- Add option to include tax in packet price
- Add option to limit coupon usages by user
- Add option to accept pending stripe payments
- Add support for two packet relations: Disable, Upgrade
- Add option to execute reward again if the packet gets extended (e.g. by a subscription payment)
- Add string replacements for packet name and purchase amount
- Add support for client certificate auth for paysafecard API (experimental)
- Add option to download all invoices in a given timerange as ZIP
- Show how often a coupon has been used
- Fix problems with Mojang API
- Fix credit refund
- Small design improvements
- Several bugfixes

Update notes:

- The following game integrations should be updated:
    - Garry's Mod -> v1.2.0
    - Minecraft -> v1.2.0

## v1.1.4

Released: 2022-08-27

- Support stripe API version 2022-08-01
- Rework serverbundle tokens (introduce new `integration_token` property which contains all required properties)
- Hide customer address by default during checkout
- Improve better handling for unreachable steam API
- Improve error handling for Minecraft auth requests
- Fix refunding a purchase was not possible in some cases
- Improve french translations

Update notes:

- The following game integrations should be updated if not already the case:
    - Garry's Mod -> v1.1.5
    - Minecraft -> v1.1.3

## v1.1.3

Released: 2022-08-10

- Add ban protests
- Make it possible to set color for header and footer
- Make it possible to ban players by steamid in Garrys's Mod
- Finish [reserved slots](game/gmod.md#reserved-slots) in Garry's Mod

Update notes:

- The following game integrations need to be updated:
    - Garry's Mod

## v1.1.2

Released: 2022-07-31

- Fix coupon payment requests cannot be deleted

## v1.1.1

Released: 2022-07-26

- Fix credit history view of other users
- Improve first start guide
- Smaller bugfixes

## v1.1.0

Released: 2022-07-19

- Add [minecraft](game/minecraft.md) integration
- Add [adverts](guide/adverts.md)
- Add URL to get to a users dashboard by its in-game id, see [user](guide/user.md).
- Allow deletion of payment gateways, packets and purchases
- Add server details dialog
- Fix notification mails
- Fix problem with pending PayPal payments
- Make it possible to format packet descriptions
- Several bugfixes

Update notes:

- The following game integrations need to be updated:
    - Garry's Mod
- Serverbundle API keys need to be regenerated

## v1.0.0

Released: 2022-06-17

- Add server dashboard (current online users)
- Add FAQ system
- Add last online for users
- Add ability for manually adding credits to users and see credit history
- Add support for free packets
- Add support for PayPal subscriptions
- Make it possible to add multiple memberships at once (for multiple bundles)
- Improve property picker
- Improve error messages
- Improve redirect after login
- Smaller fixes

Update notes:

- If you used PayPal in the past, you need to add the webhook id in the settings. Follow
  the [guide](guide/shop/payment_gateway.md).
- The following game integrations need an update:
    - Garry's Mod
