---
title: 'MDVA-31007: custom address attributes display'
description: The MDVA-31007 patch solves the issue where custom address attributes are not correctly displayed in the order details page in the My Account area and in the backend (in the **Sales &gt; Orders** location). This patch is available when the [Quality Patches Tool (QPT)](/help/announcements/adobe-commerce-announcements/magento-quality-patches-released-new-tool-to-self-serve-quality-patches.md) 1.0.7 is installed. Please note that the issue was fixed in Adobe Commerce 2.4.2.
exl-id: 43c82b66-395f-4e33-8312-9a1994862f5f
---
# MDVA-31007: custom address attributes display

The MDVA-31007 patch solves the issue where custom address attributes are not correctly displayed in the order details page in the My Account area and in the backend (in the **Sales > Orders** location). This patch is available when the [Quality Patches Tool (QPT)](/help/announcements/adobe-commerce-announcements/magento-quality-patches-released-new-tool-to-self-serve-quality-patches.md) 1.0.7 is installed. Please note that the issue was fixed in Adobe Commerce 2.4.2.

## Affected products and versions

**The patch is created for Adobe Commerce version:**

* Adobe Commerce on cloud infrastructure 2.4.0

**Compatible with Adobe Commerce versions:**

* Adobe Commerce (all deployment methods) 2.4.0 - 2.4.0-p1

>[!NOTE]
>
>The patch might become applicable to other versions with new Quality Patches Tool releases. To check if the patch is compatible with your Adobe Commerce version, update the `magento/quality-patches` package to the latest version and check the compatibility on the [[!DNL Quality Patches Tool]: Search for patches page](https://devdocs.magento.com/quality-patches/tool.html#patch-grid). Use the patch ID as a search keyword to locate the patch.

## Issue

<u>Steps to reproduce</u>:

1. Log in to Admin backend.
1. Navigate to **Stores** > **Attributes** > **Customer Addresses**.
1. Create two attributes:

    * Set input type: *Drop-down*.
    * Set input type: *Text*.

1. Navigate to **Stores** > **Configurations** > **Customer** > **Customer Configurations**.
1. Select *Scope* as **Default Store** view.
1. Expand the **Address Template** section. Update *Text*, *Text One Line*, and *HTML* to include the two custom attributes above:

    ```php
    {{depend testdropdown}}Dropdown: {{var testdropdown}}{{/depend}}    {{depend testtext}}Text: {{var testtext}}{{/depend}}
    ```

1. Open Storefront.
1. Create and Log in with a user.
1. Go to **My Account** > **Address book**, and add a new address (fill in the two custom attributes).
1. Add a product to the cart, and place an order.
1. On the order success page, click on the **Order number** link.
1. On the order details page, observe the **Order Information** section.
1. Go to **Backend** > **Sales** > **Orders**, click on the above order, and observe the **Address information** section.

<u>Expected results</u>:

On both frontend and backend, the billing and shipping address are displayed as expected.

<u>Actual results</u>:

On both frontend and backend, the billing address is not correctly displayed. The selected option of the dropdown attribute is missing, and the value of the input attribute contains the attribute code.

## Apply the patch

To apply individual patches, use the following links depending on your deployment method:

* Adobe Commerce or Magento Open Source on-premises: [Software Update Guide > Apply Patches](https://devdocs.magento.com/guides/v2.4/comp-mgr/patching/mqp.html) in our developer documentation.
* Adobe Commerce on cloud infrastructure: [Upgrades and Patches > Apply Patches](https://devdocs.magento.com/cloud/project/project-patch.html) in our developer documentation.

## Related reading

To learn more about Quality Patches Tool, refer to:

* [Quality Patches Tool released: a new tool to self-serve quality patches](/help/announcements/adobe-commerce-announcements/magento-quality-patches-released-new-tool-to-self-serve-quality-patches.md) in our support knowledge base.
* [Check if patch is available for your Adobe Commerce issue using Quality Patches Tool](/help/support-tools/patches-available-in-qpt-tool/check-patch-for-magento-issue-with-magento-quality-patches.md) in our support knowledge base.

For info about other patches available in QPT, refer to [Patches available in QPT](https://devdocs.magento.com/quality-patches/tool.html#patch-grid) in our developer documentation.
