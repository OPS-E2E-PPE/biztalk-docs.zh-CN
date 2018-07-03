---
title: 如何编辑属性的接收位置 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [receive locations], properties
- managing [receive locations], editing
- receive locations, properties
- receive locations, editing
- editing, receive locations
- editing, properties
ms.assetid: 2b622050-a875-4896-bed6-65ca39a26dd3
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2bace802ee40c98cd6ffee956c967d01fcdb7994
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36985926"
---
# <a name="how-to-edit-the-properties-of-a-receive-location"></a>如何编辑接收位置的属性
本主题将介绍如何使用 BizTalk Server 管理控制台编辑现有接收位置的属性。 有关创建接收位置的说明，请参阅[如何创建接收位置](../core/how-to-create-a-receive-location.md)。  
  
## <a name="prerequisites"></a>必要條件  
 若要执行本主题中的过程，必须是 BizTalk Server Administrators 组的成员的帐户登录。 有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
### <a name="to-edit-the-properties-of-a-receive-location"></a>编辑接收位置的属性  
  
1. 单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2. 在控制台树中，展开 BizTalk 组和 BizTalk 应用程序想要编辑的接收位置属性，然后单击**接收位置**。  
  
3. 在右窗格中，右键单击该接收位置，然后依次**属性**。  
  
4. 在中**接收位置属性**窗口中，编辑一个或多个以下属性，然后单击**确定**:  
  
   |使用此选项|执行的操作|  
   |--------------|----------------|  
   |**名称**|键入接收位置的名称。|  
   |**类型**|从下拉列表中，选择传输类型或传输协议。 如果更改传输类型，则必须按下文所述配置传输属性。|  
   |**配置**|选择传输类型后，单击**配置**以显示**传输属性**对话框框，并配置接收位置适配器属性。 有关说明，请单击**帮助**对话框框中。 有关配置适配器，每种类型的详细信息，请参阅下的相应主题[使用适配器](../core/using-adapters.md)。|  
   |**接收处理程序**|从下拉列表中，选择将运行接收位置的 BizTalk Server 主机实例。 接收处理程序必须在此主机上运行。|  
   |**接收管道**|从下拉列表中，选择用于在此接收位置接收消息的接收管道。|  
   |**发送管道**|从下拉列表中，选择用于从此接收位置发送响应的发送管道。 此列表仅对与请求响应端口关联的接收位置可用。|  
   |**将此主位置**|如果接收端口有多个接收位置，并且在需要将该接收端口传递到另一实体（例如需要向组织发送消息的业务合作伙伴）时要让此接收位置代表该接收端口，请选中此复选框。 创建的第一个接收位置自动选择为主接收位置。 在将其他接收位置指定为主接收位置之前，此属性将一直处于选中状态和不可用状态。|  
  
> [!NOTE]
>  在更改或修改接收位置，重新启动独立主机工作进程相对应的已修改的情况下接收位置。  
  
## <a name="see-also"></a>请参阅  
 [管理接收位置](../core/managing-receive-locations.md)