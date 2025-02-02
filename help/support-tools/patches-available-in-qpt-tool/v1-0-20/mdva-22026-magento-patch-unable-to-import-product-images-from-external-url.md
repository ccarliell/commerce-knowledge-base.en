---
title: "MDVA-22026: Can't import product images from external URL"
description: The MDVA-22026 patch fixes the issue of being unable to import product images from an external URL.
exl-id: 29043c6c-daf2-4925-85bf-49eeeee3742c
---
# MDVA-22026: Can't import product images from external URL

The MDVA-22026 patch fixes the issue of being unable to import product images from an external URL.

This patch is available when the [Quality Patches Tool (QPT)](/help/announcements/adobe-commerce-announcements/magento-quality-patches-released-new-tool-to-self-serve-quality-patches.md) 1.0.20 is installed. The patch ID is MDVA-22026. Please note that the issue was fixed in Adobe Commerce version 2.3.4.

## Affected products and versions

 **The patch is created for Adobe Commerce version:** Adobe Commerce on cloud infrastructure 2.3.2-p2

 **Compatible with Adobe Commerce versions:** Adobe Commerce on-premises and Adobe Commerce on cloud infrastructure  2.3.2-2.3.3-p1

>[!NOTE]
>
>The patch might become applicable to other versions with new Quality Patches Tool releases. To check if the patch is compatible with your Adobe Commerce version, update the `magento/quality-patches` package to the latest version and check the compatibility on the [[!DNL Quality Patches Tool]: Search for patches page](https://devdocs.magento.com/quality-patches/tool.html#patch-grid). Use the patch ID as a search keyword to locate the patch.

## Issue

 <u>Steps to reproduce</u>:

1. In Admin, go to **System** > **Import**.
1. Set **Entity Type** = *Products*.
1. Set **Import Behavior** = *Add/Update*.
1. Set **Allowed Errors Count** = *10000*.
1. Select the file for import.
1. Click the **Check Data** button (which should validate the file).
1. Click the **Import** button.

 <u>Expected results</u>:

Successful import of products from CSV files, including images from external URLs, as expected.

 <u>Actual results</u>:

Unsuccessful import of products from CSV files, including images from external URLs, and receive a similar error:

```php
1. Imported resource (image) could not be downloaded from external resource due to timeout or access permissions in row(s): 4, 5, 8, 9, 16, 18, 20, 21, 22, 23, 26, 27, 28, 52, 53, 55, 58, 63, 70, 71, 77, 78, 83, 84, 91
```

## Apply the patch

To apply individual patches use the following links depending on your deployment method:

* Adobe Commerce or Magento Open Source on-premises: [Software Update Guide > Apply Patches](https://devdocs.magento.com/guides/v2.4/comp-mgr/patching.html).
* Adobe Commerce on cloud infrastructure: [Upgrades and Patches > Apply Patches](https://devdocs.magento.com/cloud/project/project-patch.html).

## Related reading

To learn more about Quality Patches Tool, refer to:

* [Quality Patches Tool released: a new tool to self-serve quality patches](/help/announcements/adobe-commerce-announcements/magento-quality-patches-released-new-tool-to-self-serve-quality-patches.md).
* [Check patch for Adobe Commerce issue with Quality Patches Tool](/help/support-tools/patches-available-in-qpt-tool/check-patch-for-magento-issue-with-magento-quality-patches.md).

For info about other patches available in QPT tool, refer to the [Patches available in QPT tool](https://support.magento.com/hc/en-us/sections/360010506631-Patches-available-in-QPT-tool-) section.
