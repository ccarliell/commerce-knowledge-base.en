---
title: 'MDVA-37779: Unable to add configurable product to cart via GraphQL'
description: The MDVA-37779 Adobe Commerce patch solves the issue where it is impossible to add a configurable product to cart when the website ID is not equal to the store ID. This patch is available when the [Quality Patches Tool (QPT)](/help/announcements/adobe-commerce-announcements/magento-quality-patches-released-new-tool-to-self-serve-quality-patches.md) 1.0.24 is installed. The patch ID is MDVA-37779. Please note that the issue is scheduled to be fixed in Adobe Commerce 2.4.4. 
exl-id: 5f344896-39c3-4e17-89b8-1b987bae2968
---
# MDVA-37779: Unable to add configurable product to cart via GraphQL

The MDVA-37779 Adobe Commerce patch solves the issue where it is impossible to add a configurable product to cart when the website ID is not equal to the store ID. This patch is available when the [Quality Patches Tool (QPT)](/help/announcements/adobe-commerce-announcements/magento-quality-patches-released-new-tool-to-self-serve-quality-patches.md) 1.0.24 is installed. The patch ID is MDVA-37779. Please note that the issue is scheduled to be fixed in Adobe Commerce 2.4.4.

## Affected products and versions

**The patch is created for Adobe Commerce version:**

Adobe Commerce on cloud infrastructure 2.4.2

**Compatible with Adobe Commerce versions:**

Adobe Commerce on-premises and Adobe Commerce on cloud infrastructure 2.4.2 - 2.4.2-p1

>[!NOTE]
>
>The patch might become applicable to other versions with new Quality Patches Tool releases. To check if the patch is compatible with your Adobe Commerce version, update the `magento/quality-patches` package to the latest version and check the compatibility on the [[!DNL Quality Patches Tool]: Search for patches page](https://devdocs.magento.com/quality-patches/tool.html#patch-grid). Use the patch ID as a search keyword to locate the patch.

## Issue

It is impossible to add configurable product to the cart when the website ID is not equal to the store ID.

<u>Prerequisites</u>:

Have a second website, store and store view where website ID is not equal to the store ID.

<u>Steps to reproduce</u>:

1. Create an empty cart using GraphQl mutation `createEmptyCart`.
1. Try to add a configurable product to the cart using the `addConfigurableProductsToCart` mutation.

<u>Expected results</u>:

Product added to cart.

<u>Actual results</u>:

Get an error: *Could not add the product with SKU xxxx to the shopping cart: The website with ID 3 that was requested wasn't found. Verify the website and try again.*

## Apply the patch

To apply individual patches, use the following links depending on your deployment method:

* Adobe Commerce or Magento Open Source on-premises: [Software Update Guide > Apply Patches](https://devdocs.magento.com/guides/v2.4/comp-mgr/patching/mqp.html) in our developer documentation.
* Adobe Commerce on cloud infrastructure: [Upgrades and Patches > Apply Patches](https://devdocs.magento.com/cloud/project/project-patch.html) in our developer documentation.


## Related reading

To learn more about Quality Patches Tool, refer to:

* [Quality Patches Tool released: a new tool to self-serve quality patches](/help/announcements/adobe-commerce-announcements/magento-quality-patches-released-new-tool-to-self-serve-quality-patches.md) in our support knowledge base.
* [Check if patch is available for your Adobe Commerce issue using Quality Patches Tool](/help/support-tools/patches-available-in-qpt-tool/check-patch-for-magento-issue-with-magento-quality-patches.md) in our support knowledge base.

For info about other patches available in QPT tool, refer to the [Patches available in QPT tool](https://support.magento.com/hc/en-us/sections/360010506631-Patches-available-in-QPT-tool-) section.
