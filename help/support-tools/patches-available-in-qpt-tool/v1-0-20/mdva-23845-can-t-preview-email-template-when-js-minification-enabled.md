---
title: "MDVA-23845: can't preview email template when JS minification enabled"
description: The MDVA-23845 Magento patch fixes the issue when unable to preview the email template in Admin when JS minification is enabled.
exl-id: 08579251-a0aa-4e84-9d6a-3fa2999d9c05
---
# MDVA-23845: can't preview email template when JS minification enabled

The MDVA-23845 Magento patch fixes the issue when unable to preview the email template in Admin when JS minification is enabled.

This patch is available when the [Quality Patches Tool (QPT)](/help/announcements/adobe-commerce-announcements/magento-quality-patches-released-new-tool-to-self-serve-quality-patches.md) 1.0.20 is installed. The patch ID is MDVA-23845. Please note that the issue was fixed in Magento version 2.3.5.

## Affected products and versions

 **The patch is created for Magento version:** Magento Commerce Cloud 2.3.3

 **Compatible with Magento versions:** Magento Commerce and Magneto Commerce Cloud 2.3.2-2.3.4-p2

>[!NOTE]
>
>The patch might become applicable to other versions with new Quality Patches Tool releases. To check if the patch is compatible with your Adobe Commerce version, update the `magento/quality-patches` package to the latest version and check the compatibility on the [[!DNL Quality Patches Tool]: Search for patches page](https://devdocs.magento.com/quality-patches/tool.html#patch-grid). Use the patch ID as a search keyword to locate the patch.

## Issue

 <u>Steps to reproduce</u> :

1. Enable **JS minification** in **Admin > Stores > Configuration > JavaScript Settings > Minify JavaScript Files** = *Yes* .
1. Switch Magento to production mode.
1. Go to **Admin > Marketing > Communications > Email Templates** .
1. Click **Add New Template** .
1. Select the **New Order** template.
1. Click the **Load Template** button.
1. Fill up **Template Name** with **New Order.**
1. Click the **Save Template** button.
1. In the email templates grid, click on **Preview** link in the **Actions** column.

 <u>Expected results</u> :

The email template preview appears in the opened popup window, as expected.

 <u>Actual results</u> :

The email template preview does not appear in the opened popup window. The popup window is empty, and JS errors may appear.

## Apply the patch

To apply individual patches use the following links depending on your Magento product:

* Magento Commerce: DevDocs [Software Update Guide > Apply Patches](https://devdocs.magento.com/guides/v2.4/comp-mgr/patching.html) .
* Magento Commerce Cloud: DevDocs [Upgrades and Patches > Apply Patches](https://devdocs.magento.com/cloud/project/project-patch.html) .

## Related reading

To learn more about Quality Patches Tool, refer to:

* [Quality Patches Tool released: a new tool to self-serve quality patches](/help/announcements/adobe-commerce-announcements/magento-quality-patches-released-new-tool-to-self-serve-quality-patches.md) .
* [Check patch for Magento issue with Quality Patches Tool](/help/support-tools/patches-available-in-qpt-tool/check-patch-for-magento-issue-with-magento-quality-patches.md) .

For info about other patches available in QPT tool, refer to the [Patches available in QPT tool](https://support.magento.com/hc/en-us/sections/360010506631-Patches-available-in-QPT-tool-) section.
