# Themes and Customizability

VyHub can be customized in various aspects. You can create your own theme, add custom navigation links, create custom HTML pages, and more.

The biggest customization option is the `Shop-Only` mode - this mode disables or hides everything that is not shop-related. This mode can be enabled in the `General` settings.

You can find predefined themes in the settings under `Themes` on the top-right.

## Theme

### Attributes

| Attribute                                                          | Description                                                                          |
|-------------------------------------------------------------------|-------------------------------------------------------------------------------------|
| Header / Footer / Primary / Secondary / Success / Warning / Error Color | The colors of the theme.                                                       |
| Light Header Color                                                | Uses light-colored text/icons in the header (for dark header colors).               |
| Header Container                                                   | Constrains the header content to a centered container. (advanced settings)          |
| Darkmode                                                           | Enables the dark theme variant.                                                     |
| Background Image                                                   | Upload/URL of a background image (leave empty if a color is preferred).             |
| Background Color                                                  | Background color (is overwritten by the background image, if set).                  |
| Logo                                                              | [Optional] Logo displayed in the top left corner (leave empty if no logo is wanted).|
| Logo Width                                                        | Width of the logo (slider, 50-150).                                                 |
| Show Community Name                                               | Displays the community name in the header.                                          |
| Custom CSS                                                        | [Optional] Add custom CSS to your instance. (advanced settings)                     |
| Featured Servers for Shop Only                                   | Shop-only mode: up to two servers shown in the shop-only header.                    |

`Header Container` and `Custom CSS` (and the `Success` / `Warning` / `Error` colors) are only available when advanced
settings are enabled. `Featured Servers for Shop Only` is only shown when shop-only mode is enabled, which then hides
the `Show Community Name`, `Logo Width` and `Header Container` options.

## Custom navigation links and websites

You can add custom navigation links to external websites or write your own HTML.  
Find more information in the **[navigation](navigation.md)** section.

## Custom CSS 

Besides the predefined themes or the simple options in the theme settings, you can add custom CSS to your instance.

> It might be necessary to use the `!important` keyword to focus on objects properly.
