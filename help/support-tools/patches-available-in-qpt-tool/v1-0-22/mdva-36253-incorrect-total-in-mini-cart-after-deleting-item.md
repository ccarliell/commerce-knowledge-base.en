---
title: 'MDVA-36253: Incorrect total in mini cart after deleting item'
description: The MDVA-36253 patch solves the issue where the product price is not being updated if you go back to the mini cart page after deleting a product when using multi-shipping checkout step. This patch is available when the [Quality Patches Tool (QPT)](/help/announcements/adobe-commerce-announcements/magento-quality-patches-released-new-tool-to-self-serve-quality-patches.md) 1.0.22 is installed. The patch ID is MDVA-36253. Please note that the issue was fixed in Adobe Commerce 2.4.3.
exl-id: cbd436d7-7fbd-46dd-97cf-30f709da1ce5
---
# MDVA-36253: Incorrect total in mini cart after deleting item

The MDVA-36253 patch solves the issue where the product price is not being updated if you go back to the mini cart page after deleting a product when using multi-shipping checkout step. This patch is available when the [Quality Patches Tool (QPT)](/help/announcements/adobe-commerce-announcements/magento-quality-patches-released-new-tool-to-self-serve-quality-patches.md) 1.0.22 is installed. The patch ID is MDVA-36253. Please note that the issue was fixed in Adobe Commerce 2.4.3.

## Affected products and versions

**The patch is created for Adobe Commerce version:**

Adobe Commerce on cloud infrastructure 2.4.1

**Compatible with Adobe Commerce versions:**

Adobe Commerce (all deployment methods) 2.4.0-2.4.1-p1

>[!NOTE]
>
>The patch might become applicable to other versions with new Quality Patches Tool releases. To check if the patch is compatible with your Adobe Commerce version, update the `magento/quality-patches` package to the latest version and check the compatibility on the [[!DNL Quality Patches Tool]: Search for patches page](https://devdocs.magento.com/quality-patches/tool.html#patch-grid). Use the patch ID as a search keyword to locate the patch.

## Issue

Incorrect total in mini cart after deleting item.

<u>Steps to reproduce</u>:

1. Log in as a customer that has at least one address.
1. Add four products to cart (price = $10 for each).
1. Go to the cart and click **Check Out with Multiple Addresses**.
1. Remove one item.
1. Navigate back to the Home page.
1. Open the cart and check the total price.

<u>Expected results</u>:

Total is $30.

<u>Actual results</u>:

Total is $40.

## Apply the patch

To apply individual patches, use the following links depending on your deployment method:

* Adobe Commerce or Magento Open Source on-premises: [Software Update Guide > Apply Patches](https://devdocs.magento.com/guides/v2.4/comp-mgr/patching/mqp.html) in our developer documentation.
* Adobe Commerce on cloud infrastructure: [Upgrades and Patches > Apply Patches](https://devdocs.magento.com/cloud/project/project-patch.html) in our developer documentation.

## Related reading

To learn more about Quality Patches Tool, refer to:

* [Quality Patches Tool released: a new tool to self-serve quality patches](/help/announcements/adobe-commerce-announcements/magento-quality-patches-released-new-tool-to-self-serve-quality-patches.md) in our support knowledge base.
* [Check if patch is available for your Adobe Commerce issue using Quality Patches Tool](/help/support-tools/patches-available-in-qpt-tool/check-patch-for-magento-issue-with-magento-quality-patches.md) in our support knowledge base.

For info about other patches available in QPT, refer to [Patches available in QPT](https://devdocs.magento.com/quality-patches/tool.html#patch-grid) in our developer documentation.
