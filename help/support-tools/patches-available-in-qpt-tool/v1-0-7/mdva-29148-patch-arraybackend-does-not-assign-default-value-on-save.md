---
title: 'MDVA-29148: ArrayBackend does not assign default value on save'
description: The MDVA-29148 patch solves the issue where `\Magento\Eav\Model\Entity\Attribute\Backend\ArrayBackend` does not assign the default value on save. This patch is available when the [Quality Patches Tool (QPT)](/help/announcements/adobe-commerce-announcements/magento-quality-patches-released-new-tool-to-self-serve-quality-patches.md) 1.0.7 is installed. Please note that the issue was fixed in Adobe Commerce 2.4.2.
exl-id: 7b2f5c18-0e7a-485b-a07e-700e435697fd
---
# MDVA-29148: ArrayBackend does not assign default value on save

The MDVA-29148 patch solves the issue where `\Magento\Eav\Model\Entity\Attribute\Backend\ArrayBackend` does not assign the default value on save. This patch is available when the [Quality Patches Tool (QPT)](/help/announcements/adobe-commerce-announcements/magento-quality-patches-released-new-tool-to-self-serve-quality-patches.md) 1.0.7 is installed. Please note that the issue was fixed in Adobe Commerce 2.4.2.

## Affected products and versions

**The patch is created for Adobe Commerce version:**

Adobe Commerce on cloud infrastructure 2.3.3-p1.

**Compatible with Adobe Commerce versions:**

Adobe Commerce (all deployment methods) >=2.3.0 <2.4.2.

>[!NOTE]
>
>The patch might become applicable to other versions with new Quality Patches Tool releases. To check if the patch is compatible with your Adobe Commerce version, update the `magento/quality-patches` package to the latest version and check the compatibility on the [[!DNL Quality Patches Tool]: Search for patches page](https://devdocs.magento.com/quality-patches/tool.html#patch-grid). Use the patch ID as a search keyword to locate the patch.

## Issue

When a product is created via an import script or the REST API, attributes that use the `\Magento\Eav\Model\Entity\Attribute\Backend\ArrayBackend` backend model and have a default value are not assigned the default value.

<u>Steps to reproduce</u>:

1. Create a new global attribute that uses the `\Magento\Eav\Model\Entity\Attribute\Backend\ArrayBackend` backend model and a non-empty default value.
1. Use the REST API to create a new product.
1. Fetch that new product from the REST API and confirm that the attribute is not present in the product's custom attributes.

<u>Expected results</u>:

The custom attribute default value was saved to the product attribute.

<u>Actual results</u>:

The custom attribute default value was not saved to the product attribute.

## Apply the patch

To apply individual patches, use the following links depending on your deployment method:

* Adobe Commerce or Magento Open Source on-premises: [Software Update Guide > Apply Patches](https://devdocs.magento.com/guides/v2.4/comp-mgr/patching/mqp.html) in our developer documentation.
* Adobe Commerce on cloud infrastructure: [Upgrades and Patches > Apply Patches](https://devdocs.magento.com/cloud/project/project-patch.html) in our developer documentation.

## Related reading

To learn more about Quality Patches Tool, refer to:

* [Quality Patches Tool released: a new tool to self-serve quality patches](/help/announcements/adobe-commerce-announcements/magento-quality-patches-released-new-tool-to-self-serve-quality-patches.md) in our support knowledge base.
* [Check if patch is available for your Adobe Commerce issue using Quality Patches Tool](/help/support-tools/patches-available-in-qpt-tool/check-patch-for-magento-issue-with-magento-quality-patches.md) in our support knowledge base.

For info about other patches available in QPT, refer to [Patches available in QPT](https://devdocs.magento.com/quality-patches/tool.html#patch-grid) in our developer documentation.
