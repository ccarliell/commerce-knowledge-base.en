---
title: 'MDVA-31969 patch: import products .csv images duplicated'
description: The MDVA-31969 patch fixes the issue where images are duplicated when importing two products .csv files. This patch is available when the [Quality Patches Tool (QPT)](/help/announcements/adobe-commerce-announcements/magento-quality-patches-released-new-tool-to-self-serve-quality-patches.md) 1.0.14 is installed.
exl-id: 2a3c9cce-1f71-4f27-807e-12beffc379d2
---
# MDVA-31969 patch: import products .csv images duplicated

The MDVA-31969 patch fixes the issue where images are duplicated when importing two products .csv files. This patch is available when the [Quality Patches Tool (QPT)](/help/announcements/adobe-commerce-announcements/magento-quality-patches-released-new-tool-to-self-serve-quality-patches.md) 1.0.14 is installed.

## Affected products and versions

**The patch is created for Adobe Commerce version:**

Adobe Commerce on cloud infrastructure 2.3.4-p2

**Compatible with Adobe Commerce versions:**

Adobe Commerce on cloud infrastructure and Adobe Commerce on-premises 2.3.3 - 2.3.4-p2, 2.4.0 - 2.4.1

>[!NOTE]
>
>The patch might become applicable to other versions with new Quality Patches Tool releases. To check if the patch is compatible with your Adobe Commerce version, update the `magento/quality-patches` package to the latest version and check the compatibility on the [[!DNL Quality Patches Tool]: Search for patches page](https://devdocs.magento.com/quality-patches/tool.html#patch-grid). Use the patch ID as a search keyword to locate the patch.

## Issue

New product images are created in the `pub/media` folder, even if the same image already exists, when importing products.

<u>Steps to reproduce</u>:

1. Create a directory for images: `mkdir var/import-images`
1. Add images inside the path `<install dir>/var/import-images`.
1. Import the product .csv file twice.

<u>Expected results</u>:

Products end up with each product image attached once.

<u>Actual results</u>:

Products end up with product images duplicated.

## Apply the patch

To apply individual patches, use the following links depending on your deployment method:

* Adobe Commerce or Magento Open Source on-premises: [Software Update Guide > Apply Patches](https://devdocs.magento.com/guides/v2.4/comp-mgr/patching/mqp.html) in our developer documentation.
* Adobe Commerce on cloud infrastructure: [Upgrades and Patches > Apply Patches](https://devdocs.magento.com/cloud/project/project-patch.html) in our developer documentation.

## Related reading

To learn more about Quality Patches Tool, refer to:

* [Quality Patches Tool released: a new tool to self-serve quality patches](/help/announcements/adobe-commerce-announcements/magento-quality-patches-released-new-tool-to-self-serve-quality-patches.md) in our support knowledge base.
* [Check if patch is available for your Adobe Commerce issue using Quality Patches Tool](/help/support-tools/patches-available-in-qpt-tool/check-patch-for-magento-issue-with-magento-quality-patches.md) in our support knowledge base.

For info about other patches available in QPT, refer to the [Patches available in QPT](https://devdocs.magento.com/quality-patches/tool.html#patch-grid) in our developer documentation.
