---
title: 'MDVA-35847: Company User form not working'
description: The MDVA-35847 patch solves the issue of the Company User form not working and returning a 500 error on the front end. This patch is available when the [Quality Patches Tool (QPT)](/help/announcements/adobe-commerce-announcements/magento-quality-patches-released-new-tool-to-self-serve-quality-patches.md) 1.0.19 is installed. The patch ID is MDVA-35847. Please note that the issue was fixed in Adobe Commerce version 2.4.3.
exl-id: 1a3f4a61-0c21-460a-ae48-e792d03ed805
---
# MDVA-35847: Company User form not working

The MDVA-35847 patch solves the issue of the Company User form not working and returning a 500 error on the front end. This patch is available when the [Quality Patches Tool (QPT)](/help/announcements/adobe-commerce-announcements/magento-quality-patches-released-new-tool-to-self-serve-quality-patches.md) 1.0.19 is installed. The patch ID is MDVA-35847. Please note that the issue was fixed in Adobe Commerce version 2.4.3.

## Affected products and versions

**The patch is created for Adobe Commerce version:**

Adobe Commerce on cloud infrastructure 2.4.2

**Compatible with Adobe Commerce versions:**

Adobe Commerce (all deployment methods) 2.4.1-2.4.2

>[!NOTE]
>
>The patch might become applicable to other versions with new Quality Patches Tool releases. To check if the patch is compatible with your Adobe Commerce version, update the `magento/quality-patches` package to the latest version and check the compatibility on the [[!DNL Quality Patches Tool]: Search for patches page](https://devdocs.magento.com/quality-patches/tool.html#patch-grid). Use the patch ID as a search keyword to locate the patch.

## Issue

<u>Prerequisites</u>:

 Adobe Commerce B2B is installed.

<u>Steps to reproduce</u>:

1. Go to **Stores** > **Attributes** > **Customer**, and create a new custom customer attribute:

    * Input type = *Date*
    * Show on Storefront = *Yes*
    * Sort Order = *0*
    * Forms to Use In = *All forms*

1. Create a new company.
1. Log in as company admin on the front end.
1. Go to the Company Users sections.

<u>Expected results</u>:

The Company User form loads normally.

<u>Actual results</u>:

The Company User form does not load and returns a 500 error.

## Apply the patch

To apply individual patches, use the following links depending on your deployment method:

* Adobe Commerce or Magento Open Source on-premises: [Software Update Guide > Apply Patches](https://devdocs.magento.com/guides/v2.4/comp-mgr/patching/mqp.html) in our developer documentation.
* Adobe Commerce on cloud infrastructure: [Upgrades and Patches > Apply Patches](https://devdocs.magento.com/cloud/project/project-patch.html) in our developer documentation.

## Related reading

To learn more about Quality Patches Tool, refer to:

* [Quality Patches Tool released: a new tool to self-serve quality patches](/help/announcements/adobe-commerce-announcements/magento-quality-patches-released-new-tool-to-self-serve-quality-patches.md) in our support knowledge base.
* [Check if patch is available for your Adobe Commerce issue using Quality Patches Tool](/help/support-tools/patches-available-in-qpt-tool/check-patch-for-magento-issue-with-magento-quality-patches.md) in our support knowledge base.

For info about other patches available in QPT, refer to [Patches available in QPT](https://devdocs.magento.com/quality-patches/tool.html#patch-grid) in our developer documentation.
