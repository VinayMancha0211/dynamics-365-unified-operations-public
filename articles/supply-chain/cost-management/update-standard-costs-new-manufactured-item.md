---
title: Update standard costs for a new manufactured item
description: Learn about updating standard costs for a new manufactured item, including a list of guidelines for defining costing versions.
author: prasungoel
ms.author: prasungoel
ms.reviewer: kamaybac
ms.search.form: CostingVersion, InventStdCostConv
ms.topic: how-to
ms.date: 03/17/2025
ms.custom: 
  - bap-template
---

# Update standard costs for a new manufactured item

[!include [banner](../includes/banner.md)]

This article provides guidance for updating standard costs for a new manufactured item.

The following guidelines assume that you use a two-version approach to update standard costs. In this approach, one costing version contains the standard costs that were originally defined for the frozen period, and the second costing version contains the incremental updates that pertain to the new manufactured items. The incremental updates are entered as cost records in the second costing version, and eventually they're enabled. The two-version approach requires that you define a second costing version. Here are the guidelines for defining this costing version:

- Assign a costing type of **Standard cost**.
- Assign a significant identifier that indicates the contents of the costing version, such as **2016-UPDATES**.
- In the **Allow price types** field group, make sure that **Cost price** is set to **Yes**.
- Allow cost records to be entered for all sites (that is, leave the **Site** field blank). If you enter a site, cost records can be entered only for that site.
- Use a fallback principle of **Active**.

To add new manufacturing items throughout the frozen period, follow these steps.

1. Use the **Costing version setup** page to enable cost records to be entered into the second costing version that contains the incremental updates. Prevent the activation of pending costs, where activation is allowed after pending costs have been completely and accurately defined. Indicate a blank from-date as a policy in the costing version, and then enter the from-date when you enter each cost record. The from-date should represent a date before the new items are purchased or manufactured.
1. Use the **Item price** page to enter cost records for new purchased items. For each cost record, enter the costing version that contains incremental updates, and use a from-date that comes before the expected manufacturing date for new manufactured items.
1. Calculate the cost of new manufactured items by using the **Calculation** page. Open the **Calculation** page from the **Costing version maintenance** page, and then select the costing version that contains the incremental updates. Use the selection criteria to specify the new manufactured item and any one of its manufactured components. In a multilevel product structure, you might also have to specify any parent item that contains the new manufactured items as a component. Enter a from-date for the bill of materials (BOM) calculation that corresponds to the start of manufacturing for the new manufactured items. The from-date should be in the effective dates for the item’s BOM version and route version. **Note:** A missing cost record can indicate a new manufactured item. BOM calculations can be limited to items that have missing costs.
1. Verify the completeness and accuracy of the calculated costs for new manufactured items. Use the **Complete** page to review the calculated costs for each item cost record, and also review any Action center warning messages. Alternatively, use the **Calculation** page to review the calculated costs.
1. Use the **Costing version setup** page to change the blocking flag to allow activation of the pending cost records in the second costing version.
1. Use the **Activate prices** page (which you open from the **Costing version maintenance** page) to enable all pending cost records in the second costing version. You can also enable the pending cost records for individual items by clicking the **Activate** button on the **Item price** page.
1. Use the **Costing version setup** page to change the blocking flags in the second costing version to prevent additional data maintenance. The blocking policies prevent the entry of new pending costs and the activation of pending costs.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
