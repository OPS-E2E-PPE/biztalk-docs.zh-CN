---
title: 如何控制结果列表的大小 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- results list [Orchestration Debugger], deleting columns
- results list [Orchestration Debugger], limiting list size
- Orchestration Debugger, results list
- results list [Orchestration Designer]
- results list [Orchestration Debugger], adding columns
ms.assetid: 4d41003f-5ea9-4599-8ec0-737c342ffdbd
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0081408f3d09852f61a4b22822e8b71a1d9b5fc2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385661"
---
# <a name="how-to-control-the-size-of-the-results-list"></a>如何控制结果列表的大小
上**组中心**页[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，查询结果窗格中包含列过多的需要进行滚动才能查看它们的信息。 可以添加或删除窗格以显示所需的信息中的列。 若要添加或删除列，右键单击任何部分查询结果窗格中的单击**添加/删除列**上下文菜单上。  

## <a name="prerequisites"></a>先决条件  
 必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Administrators 组才能执行此过程。  

### <a name="to-add-or-remove-columns-in-the-results-list"></a>若要添加或删除列在结果列表  

1. 右键单击任意单元**查询结果**列表，，然后单击**添加/删除列**上下文菜单上。  

   > [!NOTE]
   >  结果列表中已存在的项显示在右侧**显示的列**。 结果列表中不存在的项出现在下的左侧**可用列**。  

2. 若要添加某一列，选择某一项从**可用的列**然后单击**添加**将该列移到列表**显示的列**。  

3. 若要删除某一列，选择某一项从**显示的列**然后单击**删除**将该列移到列表**可用列**。  

   您可以控制该查询使用在创建或运行查询时提供的筛选器返回的结果数。  

## <a name="columns-in-the-query-results-list"></a>在查询中的列的结果列表  
 发起该查询的视图底部的查询结果窗格中显示查询结果。 不能直接访问结果列表。 上下文菜单显示所有可以在当前处于活动状态的视图中选定的记录执行的操作。 例如，如果该记录包含服务实例 ID，则与服务相关的操作显示。 如果没有消息 ID，则显示与消息相关的操作。  

 因为您可能不需要此完整的列表中包含的所有信息，可以选择你想要查看，这些的列，或者可以替换已删除的列。 当按时间排序结果列表时，请实例可排序到毫秒，即使出现在列表中没有毫秒为单位。 当你重复使用已保存的查询结果将显示仅选择每次运行查询的列。  

 下表显示在结果列表中显示的项的完整列表。  


|                              |                                                                                                                                           |
|------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------|
| **服务或消息字段** |                                                              **说明**                                                              |
|         服务名称         |                                                       服务实例的名称。                                                       |
|          事件类型          |                    服务 （例如，消息传送 （报告为管道），业务流程，传输适配器） 的类型。                     |
|      错误说明       |                                                 如果发生了错误的说明。                                                 |
|            State             |                                              运行查询时的操作的状态。                                               |
|          错误代码          |                                                    如果发生了错误代码。                                                     |
|    解密证书    |                                   显示与消息或服务相关的证书信息。                                   |
|           Duration           |                                                    若要完成该操作的时间。                                                    |
|          端口名称           |                                                实例的流中涉及的端口。                                                 |
|          签名           |                                               消息的数字签名信息。                                               |
|             大小             |                                                       以字节为单位的消息的大小。                                                       |
|          Start Time          |                                                        启动操作的时间。                                                        |
|           结束时间           |                                                         操作结束时间。                                                         |
|          部分计数          |                                                      消息中的部分数。                                                      |
|            聚会             |                                              启动操作的参与方的标识符。                                              |
|             URI              |                                                       发起方的 URI。                                                        |
|          TimeStamp           |                                                        启动操作的时间。                                                        |
|             主机             |                                          运行服务实例的 BizTalk 主机的名称。                                           |
|        程序集名称         |                                      实现服务实例的.NET 程序集的名称。                                      |
|       程序集版本       |                                                  相关程序集的版本号。                                                  |
|       部署时间        | 服务实例程序集部署到的时间[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 |
|         活动 ID          |     标识唯一的服务实例活动 （例如，管道/业务流程发送/接收具有相同 ID 的消息）。     |
|     服务实例 ID      |                              全局唯一标识符 (GUID) 标识正在运行的服务实例。                               |
|     消息实例 ID      |                                   全局唯一标识符 (GUID) 标识消息实例。                                   |
|          服务 ID          |                                       全局唯一标识符 (GUID) 标识服务。                                        |
|        服务类         |                                                类 （管道或业务流程） 的类型。                                                 |
|       服务类别 ID       |                            用于标识服务 （例如，业务流程） 的独立于服务的 GUID。                             |
|             图标             |                                                          结果行的图标。                                                          |
|           适配器            |                                                      在操作中使用的适配器。                                                       |

