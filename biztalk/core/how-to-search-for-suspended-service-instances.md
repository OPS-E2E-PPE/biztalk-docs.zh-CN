---
title: 如何搜索挂起的服务实例 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- service instances, viewing
- service instances, Query tab [Administration Console]
- Query tab [Administration Console], service instances
- service instances, suspended
- Query tab [Administration Console], searching
- instances, suspended
- instances, services
ms.assetid: f91b1151-d879-4aa7-afc8-4cf13d928158
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9a1ddc4ebc21acf863d97007a3a5c8a092f36115
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384044"
---
# <a name="how-to-search-for-suspended-service-instances"></a>如何搜索挂起的服务实例
可以使用**查询**搜索挂起的服务实例在 BizTalk Server 管理控制台中的选项卡。 您可以搜索消息，以查找特定的消息与服务名称、 类型、 主机等相关联的特定子集。  

> [!NOTE]
>  已终止且带有未使用的消息实例有关的挂起的服务实例显示为错误代码 （"已终止且未使用的消息"）。 这些实例是不可恢复。  

> [!NOTE]
>  在结果中显示时按 URI 或错误适配器名称分组和筛选仅发送和接收端口。 不能为业务流程，这不包括在显示的结果按 URI 分组和筛选。  

## <a name="prerequisites"></a>先决条件  
 若要执行此过程，必须以 BizTalk Server Operators 组的成员的身份登录。  

### <a name="to-search-for-suspended-service-instances"></a>若要搜索挂起的服务实例  

1. 单击**启动**，单击**所有程序**，单击**Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]，然后单击**BizTalk Server 管理**。  

2. 在控制台树中，展开**BizTalk Server 管理**，然后单击 BizTalk 组。  

3. 在详细信息窗格中，单击**新查询**选项卡。  

4. 在中**查询表达式**组中，在**值**列中，选择**挂起服务实例**从下拉列表框。  

5. 在中**字段名**列，星号旁边的空下拉列表框中 (* *\\* * *)，选择一个或多项操作：  


   |         项          |                                                                                                                                                                                                                   Description                                                                                                                                                                                                                   |
   |-----------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | **应用程序名称**  |                                                                                                                                                                                                   BizTalk Server 应用程序的名称。                                                                                                                                                                                                   |
   |   **创建时间**   |                                                                                                                                                                                  查找指定日期之前或之后创建的挂起的服务实例。                                                                                                                                                                                   |
   |   **适配器错误**   | 您可以进行分组或筛选器按适配器类型的挂起的服务实例。 例如：文件、 FTP、 HTTP、 MQSeries、 MSMQ、 POP3、 SMTP、 SOAP、 或 Windows SharePoint Services。 **注意：** 在查询结果中，当 BizTalk Server 运行时使用指定的适配器时遇到错误时仅填充适配器字段。 如果运行时查询结果中未找到与该适配器，出现错误，则适配器错误字段为空。 |
   |    **错误代码**     |                                                                                                                                                 您可以进行分组或筛选的错误代码，以演示所有这些挂起，该错误代码为服务实例挂起的服务实例。                                                                                                                                                  |
   | **错误说明** |                                                                                                                                                                            您可以进行分组或筛选与指定的错误说明的挂起的服务实例。                                                                                                                                                                            |
   | **按结果进行分组**  |                                                                                                                                        可以对其进行分组或筛选结果按适配器、 应用程序，错误代码、 错误说明、 主机名称、 服务类、 服务实例状态、 服务名称或 URI。                                                                                                                                         |
   |     **Host Name**     |                                                                                                                                                                                            组或筛选器挂起的服务实例的主机名。                                                                                                                                                                                            |
   |  **实例状态**  |                                                                                                                                                                         您可以搜索已挂起但不可恢复的挂起实例或已挂起和恢复的实例。                                                                                                                                                                         |
   |  **最大匹配数**  |                                                                                                                                                                                                        若要显示的匹配项的数目。                                                                                                                                                                                                        |
   |   **服务类**   |                                                                                                                                                       您可以搜索独立适配器;消息传送;消息传送和独立的适配器;MSMQT;业务流程;或路由故障报告。                                                                                                                                                       |
   |   **服务名称**    |                                                                                                                                                                                      您可以进行分组或筛选挂起的服务实例的服务名称。                                                                                                                                                                                       |
   |  **服务类型 ID**  |                                                                                                                                                                                     您可以进行分组或筛选挂起的服务实例的服务类型 id。                                                                                                                                                                                     |
   |  **挂起时间**  |                                                                                                                                                                        您可以进行分组或筛选挂起的服务实例挂起之前或之后指定的日期。                                                                                                                                                                        |
   |        **URI**        |                                              您可以进行分组或筛选由 URI 的挂起的服务实例。 **注意：** 在查询结果中，BizTalk Server 运行时发送到指定的 URI 时遇到错误时只填充 URI。 如果在运行时找不到错误时将发送到的 URI，在查询结果中，URI 字段为空或显示"URI 不可用。"                                              |


6. 完成**值**根据需要将所选内容中所做的列**字段名**列。  

7. 继续将其他行添加到查询根据需要，通过完成**字段名**，**运算符**，并**值**列，并单击**运行查询**。  

## <a name="see-also"></a>请参阅  
 [使用管理控制台的“查询”选项卡](../core/using-the-administration-console-query-tab.md)