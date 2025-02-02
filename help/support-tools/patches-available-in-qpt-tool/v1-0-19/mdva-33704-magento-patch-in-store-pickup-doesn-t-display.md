---
title: "MDVA-33704 patch: In-store pickup doesn't display"
description: The MDVA-33704 patch solves the issue where products with in-store pickup option will not display as a shipping method.
exl-id: 2c5c7627-5d2e-44d2-9579-314dbd31ee8b
---
# MDVA-33704 patch: In-store pickup doesn't display

The MDVA-33704 patch solves the issue where products with in-store pickup option will not display as a shipping method.

This patch is available when the [Quality Patches Tool (QPT)](/help/announcements/adobe-commerce-announcements/magento-quality-patches-released-new-tool-to-self-serve-quality-patches.md) 1.0.19 is installed. The patch ID is MDVA-33704. Please note that the issue is scheduled to be fixed in Adobe Commerce version 2.4.3.

## Affected products and versions

 **The patch is created for Adobe Commerce version:** Adobe Commerce on cloud infrastructure 2.4.0-p1

 **Compatible with Adobe Commerce versions:** Adobe Commerce on-premises and Adobe Commerce on cloud infrastructure 2.4.0-2.4.2

>[!NOTE]
>
>The patch might become applicable to other versions with new Quality Patches Tool releases. To check if the patch is compatible with your Adobe Commerce version, update the `magento/quality-patches` package to the latest version and check the compatibility on the [[!DNL Quality Patches Tool]: Search for patches page](https://devdocs.magento.com/quality-patches/tool.html#patch-grid). Use the patch ID as a search keyword to locate the patch.

## Issue

<u>Prerequisite</u>:<br>

**Pick in Store** enabled

<u>Steps to reproduce</u>:

1. Add a product to the cart.
1. Go to Checkout.
1. Add shipping information, and choose any shipping method other than in-store pickup.
1. Select **Proceed to payment**, but then do not proceed to the payment page.
1. Instead go back to the **Contact & Shipping** section.
1. Select **Pickup**.
1. Select **Store** and **Click to Payment**.
1. Note that your shipping address is automatically entered as a billing address.
1. Refresh the webpage.

<u>Expected results</u>:

The in-store pickup option will display as a shipping method, as expected.

<u>Actual results</u>:

The in-store pickup option will not display as a shipping method.

## Apply the patch

To apply individual patches, use the following links depending on your deployment method:

* Adobe Commerce or Magento Open Source on-premises: [Software Update Guide > Apply Patches](https://devdocs.magento.com/guides/v2.4/comp-mgr/patching/mqp.html) in our developer documentation.
* Adobe Commerce on cloud infrastructure: [Upgrades and Patches > Apply Patches](https://devdocs.magento.com/cloud/project/project-patch.html) in our developer documentation.

## Related reading

To learn more about Quality Patches Tool, refer to:

* [Quality Patches Tool released: a new tool to self-serve quality patches](/help/announcements/adobe-commerce-announcements/magento-quality-patches-released-new-tool-to-self-serve-quality-patches.md) in our support knowledge base.
* [Check if patch is available for your Adobe Commerce issue using Quality Patches Tool](/help/support-tools/patches-available-in-qpt-tool/check-patch-for-magento-issue-with-magento-quality-patches.md) in our support knowledge base.

For info about other patches available in QPT tool, refer to the [Patches available in QPT](https://support.magento.com/hc/en-us/sections/360010506631-Patches-available-in-QPT-tool-) section.
