---
title: 门户警报页 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 131b4750-ce3d-445f-be0e-6bf499734c69
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5db094dafd795b27095179b38c55e81bc36d44be
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65294951"
---
# <a name="portal-alerts-page"></a>门户警报页
图 1 显示了警报页，其中包含两个部分：  

- 主要部分显示用于创建新的警报和现有警报的列表的链接。 每个警报有一个对应的链接，您可以订阅警报。 您还可以单击要查看警报详细信息、 创建的新订阅的警报，并删除该警报的操作列中的图标。  

- **我的订阅**部分显示已在门户中定义的订阅的列表。 您可以编辑和取消订阅此列表中使用的链接现有的订阅。  

  ![门户警报页](../esb-toolkit/media/ch8-portalalertspage.gif "Ch8-PortalAlertsPage")  

  **图 1**  

  **ESB 管理门户警报页**  

  ESB 警报服务将生成警报基于条件指定的与异常中的值相匹配，如到达 ESB 管理门户。 您可以匹配，并比较系列中的异常来准确地控制哪些警报将匹配异常的每个可能的类型的字段。 在门户还可以创建映射到不同类型的定义的警报的订阅。 匹配警报发生时，这些订阅可以通知用户。  

  以下列表说明了如何使用 ESB 管理门户警报页的功能：  

- 若要创建新的警报，请单击**创建警报**页后，可以打开添加警报页顶部的链接。  

- 若要查看或编辑现有警报，请单击该警报在页的主要部分的操作列中的放大镜图标。 这将打开[警报查看器页](../esb-toolkit/alert-viewer-page.md)。  

- 若要对现有警报的订阅，单击新订阅图标以打开警报旁边的操作列[添加警报订阅和编辑订阅页](../esb-toolkit/add-alert-subscription-and-edit-subscription-pages.md)。  

- 如果打开此页以管理员身份在使用选项**管理员**选项卡菜单 (而不是从**警报**选项卡)，可以单击十字标记图标旁边的任何警报列表中的操作列删除警报和任何链接的订阅。  

- 若要编辑的现有订阅，请单击**编辑**旁边的列表中该订阅链接**我的订阅**部分中的页后，可以打开[添加警报订阅和编辑订阅页](../esb-toolkit/add-alert-subscription-and-edit-subscription-pages.md)。  

- 若要删除现有订阅，请单击**Unsubscribe**旁边的列表中该订阅链接**我的订阅**页部分。  

- 若要导出到 Microsoft Excel 的警报的完整列表，请单击**导出到 Excel**。
