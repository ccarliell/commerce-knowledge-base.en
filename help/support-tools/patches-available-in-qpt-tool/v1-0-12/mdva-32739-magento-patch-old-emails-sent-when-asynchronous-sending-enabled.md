---
title: 'MDVA-32739 patch: old emails sent when asynchronous sending enabled'
description: The MDVA-32739 patch fixes the issue where enabling [asynchronous email notifications](https://devdocs.magento.com/guides/v2.4/performance-best-practices/configuration.html#asynchronous-email-notifications) sends out old sales emails. This patch is available when the [Quality Patches Tool (QPT)](/help/announcements/adobe-commerce-announcements/magento-quality-patches-released-new-tool-to-self-serve-quality-patches.md) 1.0.12 is installed. Please note that the issue is scheduled to be fixed in Adobe Commerce 2.4.2.
exl-id: 8cf4ef8a-f2f2-47fb-9f69-0eedcc10ba8b
---
# MDVA-32739 patch: old emails sent when asynchronous sending enabled

The MDVA-32739 patch fixes the issue where enabling [asynchronous email notifications](https://devdocs.magento.com/guides/v2.4/performance-best-practices/configuration.html#asynchronous-email-notifications) sends out old sales emails. This patch is available when the [Quality Patches Tool (QPT)](/help/announcements/adobe-commerce-announcements/magento-quality-patches-released-new-tool-to-self-serve-quality-patches.md) 1.0.12 is installed. Please note that the issue is scheduled to be fixed in Adobe Commerce 2.4.2.

## Affected products and versions

 **The patch is created for Adobe Commerce version:**

 Adobe Commerce on cloud infrastructure 2.3.5-p2

 **Compatible with Adobe Commerce versions:**

 Adobe Commerce on cloud infrastructure and Adobe Commerce on-premises 2.3.0 - 2.4.1

>[!NOTE]
>
>The patch might become applicable to other versions with new Quality Patches Tool releases. To check if the patch is compatible with your Adobe Commerce version, update the `magento/quality-patches` package to the latest version and check the compatibility on the [[!DNL Quality Patches Tool]: Search for patches page](https://devdocs.magento.com/quality-patches/tool.html#patch-grid). Use the patch ID as a search keyword to locate the patch.

## Issue

<u>Steps to reproduce</u>:

1. Disable asynchronous email sending.
1. Create an order and make sure sending of the email is failing.
1. Enable asynchronous sending.

<u>Expected results</u>:

Emails are sent out only for those orders, shipments, invoices and credit memos, which were created after the last asynchronous sending update.

<u>Actual results</u>:

The old email will be sent out via the cronjob.

## Fix

With the fix included in the patch, Adobe Commerce will select orders that are created after the asynchronous sending method has been last ran and will send the email for such orders.

By default, it will select with an offset of -1 day.

You can change this value (to -2 days for example) by modifying `di.xml`.

## Apply the patch

To apply individual patches, use the following links depending on your deployment method:

* Adobe Commerce or Magento Open Source on-premises: [Software Update Guide > Apply Patches](https://devdocs.magento.com/guides/v2.4/comp-mgr/patching/mqp.html) in our developer documentation.
* Adobe Commerce on cloud infrastructure: [Upgrades and Patches > Apply Patches](https://devdocs.magento.com/cloud/project/project-patch.html) in our developer documentation.

## Related reading

To learn more about Quality Patches Tool, refer to:

* [Quality Patches Tool released: a new tool to self-serve quality patches](/help/announcements/adobe-commerce-announcements/magento-quality-patches-released-new-tool-to-self-serve-quality-patches.md) in our support knowledge base.
* [Check if patch is available for your Adobe Commerce issue using Quality Patches Tool](/help/support-tools/patches-available-in-qpt-tool/check-patch-for-magento-issue-with-magento-quality-patches.md) in our support knowledge base.

For info about other patches available in QPT, refer to the [Patches available in QPT](https://devdocs.magento.com/quality-patches/tool.html#patch-grid) in our developer documentation.
