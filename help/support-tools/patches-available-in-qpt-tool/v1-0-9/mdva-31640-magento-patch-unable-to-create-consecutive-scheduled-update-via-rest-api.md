---
title: 'MDVA-31640 patch: unable to create consecutive scheduled update via REST API'
description: The MDVA-31640 patch fixes the issue where a new scheduled update for the special price cannot be created for multiple stores using REST API, if the start date of the update coincides with the end date of the previously existing update. This patch is available when the [Quality Patches Tool (QPT)](/help/announcements/adobe-commerce-announcements/magento-quality-patches-released-new-tool-to-self-serve-quality-patches.md) 1.0.9 is installed. Please note that the issue was fixed in Adobe Commerce 2.4.2.
exl-id: 8d91db3d-7c94-4757-8087-4cf53cad81e7
---
# MDVA-31640 patch: unable to create consecutive scheduled update via REST API

The MDVA-31640 patch fixes the issue where a new scheduled update for the special price cannot be created for multiple stores using REST API, if the start date of the update coincides with the end date of the previously existing update. This patch is available when the [Quality Patches Tool (QPT)](/help/announcements/adobe-commerce-announcements/magento-quality-patches-released-new-tool-to-self-serve-quality-patches.md) 1.0.9 is installed. Please note that the issue was fixed in Adobe Commerce 2.4.2.

## Affected products and versions

**The patch was created for Adobe Commerce version:**

Adobe Commerce on cloud infrastructure 2.3.5-p1

**Compatible with Adobe Commerce versions:**

Adobe Commerce on cloud infrastructure and Adobe Commerce on-premises 2.3.1 - 2.3.5-p2, 2.4.0, 2.4.0-p1

>[!NOTE]
>
>The patch might become applicable to other versions with new Quality Patches Tool releases. To check if the patch is compatible with your Adobe Commerce version, update the `magento/quality-patches` package to the latest version and check the compatibility on the [[!DNL Quality Patches Tool]: Search for patches page](https://devdocs.magento.com/quality-patches/tool.html#patch-grid). Use the patch ID as a search keyword to locate the patch.

## Issue

Fixes the issue where a new scheduled update for the special price cannot be created for multiple stores using REST API, if the start date of the update coincides with the end date of the previously existing update.

<u>Steps to reproduce</u>:

1. Set up an additional website, store, and store view.
1. Create two simple products: "product1" and "product2".
1. Assign product1 to one website and product2 to both websites.
1. Create a scheduled update for the special price for the product1 on the store view for the store with ID 1. Use REST API `POST` request to `rest/V1/products/special-price` with the following payload:
    `{        "prices": [            {                "price": 15,                "store_id": 1,                "sku": "product1",                "price_from": "2021-11-15 04:00:00",                "price_to": "2021-11-15 04:10:00"            }        ]    }`
1. Create a scheduled update for the special price for the product2 on both store views for stores with ID 1 and 2 using REST API `POST` request to `rest/V1/products/special-price` with the following payload (the `price_from` date is the same as `price_to` date in the previous request):
    `{        "prices": [            {                "price": 14,                "store_id": 1,                "sku": "product2",                "price_from": "2021-11-15 04:10:00",                "price_to": "2021-11-15 04:15:00"            },            {                "price": 13,                "store_id": 2,                "sku": "product2",                "price_from": "2021-11-15 04:10:00",                "price_to": "2021-11-15 04:15:00"            }        ]    }`

<u>Expected results</u>:

Scheduled update with the special price change is created on both store views.

<u>Actual results</u>:

Adobe Commerce throws an error. Scheduled update is not created.

## Apply the patch

To apply individual patches, use the following links depending on your deployment method:

* Adobe Commerce or Magento Open Source on-premises: [Software Update Guide > Apply Patches](https://devdocs.magento.com/guides/v2.4/comp-mgr/patching/mqp.html) in our developer documentation.
* Adobe Commerce on cloud infrastructure: [Upgrades and Patches > Apply Patches](https://devdocs.magento.com/cloud/project/project-patch.html) in our developer documentation.

## Related reading

To learn more about Quality Patches Tool, refer to:

* [Quality Patches Tool released: a new tool to self-serve quality patches](/help/announcements/adobe-commerce-announcements/magento-quality-patches-released-new-tool-to-self-serve-quality-patches.md) in our support knowledge base.
* [Check if patch is available for your Adobe Commerce issue using Quality Patches Tool](/help/support-tools/patches-available-in-qpt-tool/check-patch-for-magento-issue-with-magento-quality-patches.md) in our support knowledge base.

For info about other patches available in QPT, refer to the [Patches available in QPT](https://devdocs.magento.com/quality-patches/tool.html#patch-grid) in our developer documentation.
