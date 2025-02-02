---
title: 'MDVA-20376: no such entity with customerId'
description: The MDVA-20376 patch solves the issue of a *No such entity with customerId = 1* error for logged-in customers after order placement. This patch is available when the [Quality Patches Tool (QPT)](https://devdocs.magento.com/guides/v2.4/comp-mgr/patching.html#mqp) 1.0.13 is installed. Please note that the issue was fixed in Adobe Commerce version 2.3.4.
exl-id: a12865d0-4ac2-444f-b8b6-22cae249f5d4
---
# MDVA-20376: no such entity with customerId

The MDVA-20376 patch solves the issue of a *No such entity with customerId = 1* error for logged-in customers after order placement. This patch is available when the [Quality Patches Tool (QPT)](https://devdocs.magento.com/guides/v2.4/comp-mgr/patching.html#mqp) 1.0.13 is installed. Please note that the issue was fixed in Adobe Commerce version 2.3.4.

## Affected products and versions

**The patch is created for Adobe Commerce version:**

Adobe Commerce on cloud infrastructure 2.3.2

**Compatible with Adobe Commerce versions:**

Adobe Commerce (all deployment methods) 2.3.2 - 2.3.3-p1

>[!NOTE]
>
>The patch might become applicable to other versions with new Quality Patches Tool releases. To check if the patch is compatible with your Adobe Commerce version, update the `magento/quality-patches` package to the latest version and check the compatibility on the [[!DNL Quality Patches Tool]: Search for patches page](https://devdocs.magento.com/quality-patches/tool.html#patch-grid). Use the patch ID as a search keyword to locate the patch.

## Issue

Logged-in customers receive *No such entity with customerId = 1* error after order placement.

<u>Steps to reproduce</u>:

1. Navigate to the storefront, and log in as a registered user.
1. Place an order.
1. In the CLI, go to `var/log` and you will see the `exception.log` file.

<u>Expected results</u>:

No errors should appear in the logs, as expected.

<u>Actual results</u>:

The exception log fills up with errors similar to:

```php
report.CRITICAL: No such entity with customerId = 1 {"exception":"[object] (Magento\\Framework\\Exception\\NoSuchEntityException(code: 0): No such entity with customerId = 1 at /mnt/data/home/nyarlaga/dev/232/vendor/magento/framework/Exception/NoSuchEntityException.php:50)"} []
```

## Apply the patch

To apply individual patches, use the following links depending on your deployment method:

* Adobe Commerce or Magento Open Source on-premises: [Software Update Guide > Apply Patches](https://devdocs.magento.com/guides/v2.4/comp-mgr/patching/mqp.html) in our developer documentation.
* Adobe Commerce on cloud infrastructure: [Upgrades and Patches > Apply Patches](https://devdocs.magento.com/cloud/project/project-patch.html) in our developer documentation.

## Related reading

To learn more about Quality Patches Tool, refer to:

* [Quality Patches Tool released: a new tool to self-serve quality patches](/help/announcements/adobe-commerce-announcements/magento-quality-patches-released-new-tool-to-self-serve-quality-patches.md) in our support knowledge base.
* [Check if patch is available for your Adobe Commerce issue using Quality Patches Tool](/help/support-tools/patches-available-in-qpt-tool/check-patch-for-magento-issue-with-magento-quality-patches.md) in our support knowledge base.

For info about other patches available in QPT, refer to [Patches available in QPT](https://devdocs.magento.com/quality-patches/tool.html#patch-grid) in our developer documentation.
