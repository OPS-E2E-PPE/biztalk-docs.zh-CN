---
title: 如何创建接收位置 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.admin.procedure.createreceivelocation
helpviewer_keywords:
- receive locations, creating
- managing [receive locations], creating
- creating, receive locations
ms.assetid: ec0202cf-0e69-4ae2-aba6-8cd2c3c77e82
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e13968abd25f0f7bf85743122688e44a8f2bb25f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37003718"
---
# <a name="how-to-create-a-receive-location"></a>如何创建接收位置
本主题将介绍如何使用 BizTalk Server 管理控制台创建新的接收位置，并指定其所属的接收端口。 接收位置为入站消息到达的地址，以及处理在该地址接收到的消息的消息传送管道。  
  
 在可以创建接收位置之前，此应用程序中必须已存在与希望创建的接收位置类型相同的接收端口，。 有关创建接收端口的说明，请参阅[如何创建接收端口](../core/how-to-create-a-receive-port.md)。  
  
 您可以创建以下类型的接收位置：  
  
-   单向端口 — 用于丢弃消息并且不等待同步回复的应用程序  
  
-   请求-响应 — 用于请求消息响应的应用程序  
  
> [!NOTE]
>  应用程序开发人员可以通过在开发过程中使用本主题中的过程来创建接收位置。  
  
## <a name="prerequisites"></a>必要條件  
 若要执行本主题中的过程，必须是 BizTalk Server Administrators 组的成员的帐户登录。 有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。 此外，还需有 SSO 数据库的相应权限。  
  
### <a name="to-create-a-receive-location"></a>若要创建的接收位置  
  
1. 单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2. 在控制台树中，展开要为其创建接收位置的 BizTalk 组和 BizTalk 应用程序。  
  
3. 右键单击**接收位置**，依次指向**新建**，然后单击**单向接收位置**或**请求响应接收位置**根据接收的类型的创建位置。  
  
4. 在选择接收端口窗口，单击接收端口，将包含此接收位置，然后单击**确定**。  
  
5. 在中**接收位置属性**窗口中，执行以下操作，然后依次**确定**:  
  
   |使用此选项|执行的操作|  
   |--------------|----------------|  
   |**名称**|键入接收位置的名称。|  
   |**类型**|从下拉列表中，选择传输类型或传输协议。 如果更改传输类型，则必须按下文所述配置传输属性。|  
   |**配置**|选择传输类型后，单击**配置**以显示**传输属性**对话框框，并配置接收位置适配器属性。 有关说明，请单击**帮助**对话框框中。 有关配置适配器，每种类型的详细信息，请参阅下的相应主题[使用适配器](../core/using-adapters.md)。|  
   |**接收处理程序**|从下拉列表中，选择将运行接收位置的 BizTalk Server 主机实例。 接收处理程序必须在此主机上运行。|  
   |**接收管道**|从下拉列表中，选择用于在此接收位置接收消息的接收管道。|  
   |**发送管道**|从下拉列表中，选择用于从此接收位置发送响应的发送管道。 此列表仅对与请求响应端口关联的接收位置可用。|  
   |**将此主位置**|如果接收端口有多个接收位置，并且在需要将该接收端口传递到另一实体（例如需要向组织发送消息的业务合作伙伴）时要让此接收位置代表该接收端口，请选中此复选框。 创建的第一个接收位置自动选择为主接收位置。 在将其他接收位置指定为主接收位置之前，此属性将一直处于选中状态和不可用状态。|  
  
## <a name="see-also"></a>请参阅  
 [管理接收位置](../core/managing-receive-locations.md)