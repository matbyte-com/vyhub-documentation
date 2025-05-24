# Custom Domain

Read this guide for further information on how to use your own domain with VyHub.  
You do not need to use your own domain; we offer you a free **vyhub.app** or **serverstore.io** domain (e.g.,
gaming.vyhub.app or your-community.serverstore.io).

> A domain name is the name of a website (like vyhub.net or google.com)

We do provide a detailed [guide](#buy-your-own-domain-using-namecheap) on how to set up your custom domain
with [Namecheap](https://namecheap.pxf.io/MXzdRY).

## General Steps

1. Buy your own domain at a domain name registrar of your choice (
   e.g. <a href="https://namecheap.pxf.io/MXzdRY" rel="nofollow">Namecheap*</a>)
2. Set the domains CNAME record to the corresponding VyHub URL

### CNAME Value

Usually at registrars, the CNAME record consists of two parts:
- **Name/Host**: The subdomain or root domain you want to use.
  - This value has to match the url you set as frontend url in your VyHub instance.
  - For the root domain (e.g., your-community.de), use `@` (not supported by every registrar).
  - For a subdomain (e.g., shop.your-community.de), use `shop`.
- **Value/Points to**: The value you need to set, which is provided on the instance details page of your VyHub instance.
  - This value has to match the value shown on your instance details page.
  - Example: `your-community.vyhub.app` or `your-community.serverstore.io`

### Set the domains CNAME record

> You need to set the CNAME record to our servers, that you can reach VyHub with your domain.

Please search and follow the tutorials on how to set the CNAME record provided by your registrar.

**Caution when using Cloudflare**:
You need to set the proxy status to DNS only. Otherwise, the CNAME will not work.

Some guides are linked below:

- [Namecheap](https://namecheap.pxf.io/x9a6z3)
- [GoDaddy](https://www.godaddy.com/help/add-a-cname-record-19236)
- [OVH](https://help.ovhcloud.com/csm/en-gb-dns-edit-dns-zone?id=kb_article_view&sysparm_article=KB0039608)
- [Cloudflare](https://community.cloudflare.com/t/how-do-i-add-a-cname-record/59)


### My domain registrar does not support CNAME records for the root domain

Many domain registrars do not offer the ability to set a CNAME record for the root domain (e.g., your-community.de).

When your domain registrar does not support CNAME records for the root domain, you can use a subdomain (e.g.
`www.your-community.de`) and
redirect your root domain to the subdomain.

**Redirecting the root domain to the subdomain**
Redirect `your-community.de` to `www.your-community.de`

### Debugging with the CNAME checker

You set your CNAME, but the instance is still not loading?
Please check whether the values shown on your instance page match up with the values in
the [CNAME-checker](https://mxtoolbox.com/SuperTool.aspx?action=cname)

1. Use the CNAME checker linked in the instance details of your VyHub instance
2. Check whether the values match up (next two screenshots)
   ![Get the values ](../assets/custom_domain_guide/debug_instance_details.png)
   ![Check the values in the CNAME checker](../assets/custom_domain_guide/debug_domain_checker.png)

The values match and it is still not loading? Contact us!

### Further help?

Watch our [YouTube video](https://www.youtube.com/watch?v=RQYqynCzfyI) or
contact us.


---------------------------

## Buy your own domain using Namecheap

In this guide, we will use <a href="https://namecheap.pxf.io/MXzdRY" rel="nofollow">Namecheap</a>, which offers good
prices and is one of the biggest registrars in the world.

We also offer a video guide on how to buy a domain with Namecheap [here](https://www.youtube.com/watch?v=RQYqynCzfyI).

### Choose your desired domain name, add to cart and checkout

![Enter a domain name](../assets/custom_domain_guide/example_domain_search.jpg)
Enter a domain name and check for its availability

![Add to cart](../assets/custom_domain_guide/domain_add_cart.jpg)
Add to cart and follow the checkout process

> You do not need to add any of the "recommended packages" namecheap offers.

### CNAME Value

![Find the CNAME value](../assets/custom_domain_guide/instance_details_page.png)
Find the value on the instance details page

### Setting the CNAME with a Namecheap.com domain

Follow this <a href="https://namecheap.pxf.io/x9a6z3" rel="nofollow">guide</a> provided by namecheap.

1. Sign in to your Namecheap account
2. Select `Domain list` on the left
3. Click the `Manage` button next to your domain
4. Navigate to the `Advanced DNS` tab
5. Click `Add New Record` in the `Host Records` section
6. Select `CNAME Record`
7. Enter the CNAME value from your instance in the `Value` column
8. Enter Host value
    - Root Domain (e.g. your-community.de) | Value: `@`
    - Subdomain (e.g. shop.your-community.de) | Value: `shop`
9. Click the `Save All Changes` button

<sub>Disclaimer: This post contains affiliate links, and we may earn a small commission when you click on the links at
no additional cost to you.</sub>

