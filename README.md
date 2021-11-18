# Hotjar User Attributes - GTM Tag (Web)
**Hotjar User Attributes** is a Tag Template for **Google Tag Manager (Web)**. This is an unofficial Template for [**Hotjar User Attributes**](https://help.hotjar.com/hc/en-us/articles/4402892526487-What-are-User-Attributes-), and not made by Hotjar.

![Hotjar User Attributes Tag](https://github.com/gtm-templates-knowit-experience/gtm-hotjar-user-attributes/blob/main/images/hotjar-user-attributes-tag.png)

## Tag Settings
### User ID Settings
### Only track Users with User ID
If selected, User Attributes will only be tracked for Users with a User ID. You must input your own User ID with this setting. See [**Hotjar FAQ about handling User IDs**](https://help.hotjar.com/hc/en-us/articles/360033640653-Identify-API-Reference#handling-user-ids).

If User Attributes are missing on some parts of the site, but User ID is available, User ID will still be collected on this part of the site.

### Track all Users
If selected, User Attributes will be tracked for all Users, whether they have a User ID or not.

Do not send PII as User Attributes unless you have a User ID. [**See Hotjar FAQ**](https://help.hotjar.com/hc/en-us/articles/360061197694-User-Attributes-FAQs#sent_pii).

### User Attributes
Type in **User Attribute Name(s)** and select [**User Attribute Value(s)**](https://help.hotjar.com/hc/en-us/articles/360033640653#user-attribute-values) from the Variable dropdown.

## Tag Setup in Google Tag Manager
This Tag should always be triggered after the Hotjar Tag. One way is to add this Tag as a **Cleanup Tag** to your **Hotjar Tag** as shown in the image. The User Attributes Tag is named **Hotjar User Attributes - CT** in the image (**CT** is an abbreviation for Custom Template).

![Hotjar Tag with Hotjar User Attributes Tag as Cleanup Tag](https://github.com/gtm-templates-knowit-experience/gtm-hotjar-user-attributes/blob/main/images/hotjar-tag-with-hotjar-user-attributes-cleanup-tag.png)

If you are using this Tag on a **SPA site** (Single Page Application), Hotjar recommends that you make an [**Identify API call on every route**](https://help.hotjar.com/hc/en-us/articles/360061197694-User-Attributes-FAQs#FAQ_3).

This means translated to this Tag, that every change that happens on the site that may update/change User Attributes should trigger the Hotjar User Attribute Tag. That could be a **History Change Event**, **Login Event**, **Signup Event** and more.

## Tag Failure Message
If you test the Hotjar User Attributes Tag in **Google Tag Manager Preview/Debug Mode**, you may experience to see a failure message as shown below. No User Attributes will be collected if the Tag fails/shows a failure message.

![Hotjar User Attributes Tag Failure](https://github.com/gtm-templates-knowit-experience/gtm-hotjar-user-attributes/blob/main/images/hotjar-user-attributes-tag-failed.png)

### Failure Message occurs when "Only track Users with User ID" is selected
If you have selected to only track Users with a User ID, and you are previewing without a User ID (you aren't logged into the site), you will get the failure message.

### Failure Message occurs when "Track all Users" is selected
If you have selected to track all Users (also those without a User ID), and you are previewing when no User Attributes are available on the page, you will get the failure message.
