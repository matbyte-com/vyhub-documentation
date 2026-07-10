# Navigation

In the navigation settings, it is possible to change the navigation bar, the footer and the help menu.
It is possible to change the links, add new links or create your own pages.

Use the `Location` selector at the top to switch between the `Header`, `Footer` and `Help` navigation.

## Navigation Link Attributes

Add a new link with `Add Navigation Link` or edit an existing one with the `edit` button.

| Attribute               | Description                                                                                       |
|-------------------------|--------------------------------------------------------------------------------------------------|
| Title                   | The label of the navigation link.                                                                |
| Sublink                 | Turns the link into a dropdown entry under a parent link, allowing dropdown menus.               |
| Parent Navigation Link  | Shown when `Sublink` is enabled: the parent link this entry is nested under.                     |
| Location                | Where the link is shown: `Header`, `Footer` or `Help`. Not shown for sublinks.                   |
| Enabled                 | Affects the visibility of the navigation link.                                                   |
| Required Property       | [Optional] Specify a property which controls the visibility of the link. (advanced settings)     |
| Icon                    | [Optional] An icon shown next to the link.                                                        |
| Type                    | Either `Link` (points to a URL) or `HTML Content` (points to an HTML page). (advanced settings)   |
| Link                    | Shown for type `Link`: an absolute path (`/...`) or full URL (`https://...`).                    |
| HTML Page               | Shown for type `HTML Content`: the HTML page to display.                                          |

The `Required Property` field and the `HTML Content` type are only available when advanced settings are enabled.

## Enable / Disable Navigation

`Navigation Links` can be enabled / disabled by pressing the `edit` button.  
Set the checkbox `Enabled` and confirm. Disabled default links remain in the list but are hidden from users.
Default links cannot be deleted.

## Custom Links

External pages or internal paths can easily be linked by adding a new navigation link with the type `Link`.

## HTML Pages

You can create custom **[HTML pages](html_pages.md)** which also support JavaScript (JavaScript is only allowed for
admins, otherwise the content is sanitized). To show an HTML page in the navigation, add a navigation link with the
type `HTML Content`.

HTML pages are managed in the `HTML Pages` section (visible when advanced settings are enabled). When adding or
editing a page you can set:

| Attribute       | Description                                                                       |
|-----------------|-----------------------------------------------------------------------------------|
| Title           | The title of the HTML page.                                                        |
| Requirement Set | [Optional] Restrict access to the page to users matching a requirement set.       |
| Wrapper         | Whether the page content is displayed inside the standard page wrapper.           |
| Content         | The HTML content, edited in the rich-text editor.                                  |

You can also upload a `.txt`, `.html` or `.htm` file to fill the content editor.

## Update Order of Navigation Links

Drag and drop the `navigation links` (and their sublinks) into the order you want them to be in.
The new order is saved automatically.
