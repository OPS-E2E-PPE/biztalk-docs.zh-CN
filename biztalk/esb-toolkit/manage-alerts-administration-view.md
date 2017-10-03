---
title: "管理警报 （管理视图） |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 27f8bf7d-15b7-448d-8c13-e4969b90d021
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bc5472e96414fe5141de27630ebe3c810d2df28c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="manage-alerts-administration-view"></a>管理警报 （管理视图）
图 1 显示管理视图，管理员可以使用它来查看所有警报和其活动的摘要的列表中的通知页。 一个表显示对于每个警报的行。 每行都显示警报的名称、 创建者的姓名、 （如警报激活数内最后一个小时、 天或月），该警报的常规统计信息的链接的警报的订阅服务器上，若要查看列表和一个操作列，包含一套 cli 的计数ckable 图标，以对警报执行操作。  
  
 ![管理警报页](../esb-toolkit/media/ch8-managealertspage.jpg "Ch8 ManageAlertsPage")  
  
 **图 1**  
  
 **ESB 管理门户管理通知 （管理视图） 页**  
  
 以下列表说明如何使用 ESB 管理门户管理通知页的功能：  
  
-   单击**创建警报**页后，可以创建新的警报顶部的链接。  
  
-   单击**导出到 Excel**链接以将警报的列表导出为 Microsoft Excel 电子表格。  
  
-   单击 +**查看订户**行显示用于警报的订阅服务器列表中的链接。 在行中，展开该列表和一个删除图标将出现在为每个，使管理员能够从警报中删除订阅服务器操作列。 同时，该链接将更改到-**隐藏的订阅服务器**，并可折叠的订阅服务器列表。  
  
-   单击操作列以该行中的警报执行某项任务中的图标。 （按它们出现的顺序） 的图标和任务如下所示：  
  
    -   **查看警报详细信息。** 此图标显示所选警报的详细信息。  
  
    -   **查看历史记录**。 此图标显示包含所选警报的所有激活的表。  
  
    -   **将订户添加**。 此图标允许管理员将订户添加到所选警报。  
  
    -   **编辑警报**。 此链接允许管理员编辑警报的详细信息。  
  
    -   **删除警报**。 此链接删除的警报和所有关联的订阅。