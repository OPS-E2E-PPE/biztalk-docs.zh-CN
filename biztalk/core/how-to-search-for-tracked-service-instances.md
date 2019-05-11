---
title: 如何搜索跟踪的服务实例 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b6337df9-8c2e-4d4a-a64b-cc040f83bd91
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d1ff8801c272859e6a138fcb1e4e618226de10a5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65383980"
---
# <a name="how-to-search-for-tracked-service-instances"></a>如何搜索跟踪的服务实例
可以使用**查询**选项卡中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中搜索所有跟踪的服务实例。 若要查找服务实例，可以搜索名称和版本的程序集，其生存期、 名称或实例 ID 的服务类、 主机名、 错误代码和服务实例的状态的开始和结束时间。  

## <a name="prerequisites"></a>先决条件  
 若要执行此过程，您必须登录以成员的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Operators 组。  

### <a name="to-search-for-tracked-service-instances"></a>若要搜索跟踪的服务实例  

1. 单击**启动**，单击**程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]。  

2. 在控制台树中，展开**BizTalk Server 管理**，然后单击 BizTalk 组。  

3. 在详细信息窗格中，单击**新查询**选项卡。  

4. 在中**查询表达式**组中，在**值**列中，选择**跟踪的服务实例**从下拉列表框。  

5. 在中**字段名**列，星号旁边的空下拉列表框中 (* *\\* * *)，选择一个或多项操作：  


   |          项           |                     Description                      |
   |-------------------------|------------------------------------------------------|
   |    **程序集名称**    |    服务实例的程序集的名称。    |
   |  **程序集版本**   |           服务实例的版本。           |
   |      **结束时间**       |          服务实例的结束时间。           |
   |     **错误代码**      | 与服务实例相关联的任何错误代码。 |
   |      **Host Name**      |        服务实例的主机名。        |
   |   **最大匹配数**   |          若要显示的匹配项的数目。           |
   |    **服务类**    |          服务实例的类。          |
   | **服务实例 ID** |               服务实例 id。               |
   |    **服务名称**     |          服务实例的名称。           |
   |     **Start Time**      |       服务实例的开始时间。        |
   |        **状态**        |          服务实例的状态。          |


6. 完成**值**根据需要将所选内容中所做的列**字段名**列。  

7. 继续将其他行添加到作为相应的查询，通过完成**字段名**，**运算符**，并**值**列，并单击**运行查询**。  

## <a name="see-also"></a>请参阅  
 [使用管理控制台的“查询”选项卡](../core/using-the-administration-console-query-tab.md)