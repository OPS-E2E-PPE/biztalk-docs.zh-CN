---
title: 创建 TIBCO Rendezvous 适配器发送项目 |Microsoft Docs
description: 创建发送端口，配置将从 BizTalk 消息发送到 TIBCO Rendezvous 传输属性
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ad996c4f-e6ed-4582-a768-0cb1ad25b1d8
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6a267b9deac31d729d580cde79c62be96a612b4c
ms.sourcegitcommit: be6273d612669adfbb9dc9208aaae0a8437d4017
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2018
ms.locfileid: "24014348"
---
# <a name="create-tibco-rendezvous-send-handlers"></a>创建 TIBCO Rendezvous 发送处理程序
本部分介绍如何创建架构以在 BizTalk Server 业务流程中使用 TIBCO Rendezvous。  
  
## <a name="create-a-send-port"></a>创建发送端口
  
1.  在中**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，然后展开你的应用程序。  
  
2.  右键单击**发送端口**，依次指向**新建**，然后单击**静态要求响应发送端口**。  
  
3.  在中**发送端口属性**对话框框中，执行以下操作：  
  
    1.  例如，键入发送端口的名称`SendToTIBCORV`。  
  
    2.  从**类型**下拉列表中，选择**TIBCO Rendezvous**。  
  
    3.  从**发送处理程序**下拉列表中，选择 URI。  
  
    4.  从发送管道下拉列表，选择**Microsoft.BizTalk.DefaultPipelines.XMLTransmit**。  从**接收管道**下拉列表中，选择**Microsoft.BizTalk.DefaultPiplelines.XMLReceive**。  

        > [!NOTE]
        > 用于 TIBCO Rendezvous 的 Microsoft BizTalk 适配器要求您选择 XMLTransmit 管道的发送和接收的 XMLReceive 管道。
        
    6.  单击**配置**可配置的发送端口。  
  
4.  在中**TIBCO Rendezvous 传输属性**对话框框中，执行以下操作：  
  
    1.  输入的属性。  
  
         您不必设置登录信息。  
  
    2.  在列表中，选择为表示 TIBCO Rendezvous 系统所创建的 SSO 关联应用程序。  
  
    3.  有关**使用 SSO**，选择**是**。  
  
    4.  单击“确定” 。  
  
5.  单击“确定” 。  

## <a name="set-the-transport-properties"></a>设置传输属性
TIBCO Rendezvous 传输属性用于运行时。 在中**传输属性**，设置标识你想要发布生成的消息的 TIBCO Rendezvous 域的连接参数。  
  
 
1.  上**TIBCO Rendezvous 传输属性**屏幕上，展开**已认证发送方属性**并输入以下信息。  
  
     ![](../core/media/sadp-tibcoren-transs.gif "SAdp_TibcoRen_Transs")  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**分类帐名称**|默认值为空。 用于持久性认证消息传递的分类帐文件名。 仅限使用本地驱动器。|  
    |**可重复使用名称**|默认值为空。 用于已验证消息传递的可重用的通信名称。 在网络上所有已验证消息通信名称中，该名称必须是唯一的。|  
  
2.  展开**凭据**并输入以下信息以连接到服务器。  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**密码**|默认值为空。 登录到 Tibco Rendezvous 守护程序的密码。|  
    |**用户名**|默认值为空。 Tibco Rendezvous 守护程序的用户名称。|  
  
3.  展开**常规设置**并输入以下信息以连接到 TIBCO Rendezvous 服务器。  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**代码页编号**|默认值是 65001（UTF-8 编码代码页）。 这是 TIBCO Rendezvous SDK 用于字符串编码的代码页。|  
    |**默认使用者名称**|默认值为空。 使用者名称在业务流程中设置。 如果一个端口用于一种消息类型，您可以提供一个默认使用者名称，并通过删除设置使用者名称属性需求来简化业务流程。|  
    |**启用时间批处理**|默认值为 False。 启用/禁用 TIBCO Rendezvous 时间批处理功能。|  
    |**将不受支持的类型映射到字符串**|默认值为 True。 如果为 True，在可能的情况将不受支持的类型映射到字符串。 如果为 False，则生成运行时错误。|  
    |**二进制文件，如 TIBCO Rendezvous 程序集路径**|如果此信息已不在该路径环境变量中，则提供此信息。|  
    |**保留订单**|默认值为 True。 启用逻辑以按从 BizTalk Server 接收消息的相同顺序发送消息到 TIBCO Rendezvous。 此参数强制按相同顺序发布；但不表示订阅者按相同的顺序接收。|  
    |**发送端口标识符**|此标识符出现在与此端口关联的日志消息中。 它作为方便提供。|  
  
4.  展开**Rendezvous 传输**并输入到 TIBCO Rendezvous 服务器的连接的信息，请单击**应用**，然后单击**确定**。  
  
     您必须为用于 TIBCO Rendezvous 的 Microsoft BizTalk 适配器设置连接参数以访问 TIBCO Rendezvous。  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**守护程序**|默认值为空。<br /><br /> Rendezvous 传输后台程序参数。|  
    |**Network**|默认值为空。<br /><br /> Rendezvous 传输网络参数。|  
    |**服务**|默认值为空。<br /><br /> Rendezvous 传输服务参数。|  
  
5.  使用单一登录 (SSO) 提供凭据。  
  
     有两种方法可用于访问 TIBCO Rendezvous 系统。 您可以使用凭据（用户名和密码参数）或单一登录。  
  
    1.  选择**是**中**使用 SSO**若要使用单一登录。  
  
        > [!NOTE]
        >  请参阅[安全](../core/security-in-biztalk-adapter-for-tibco-rendezvous.md)了解如何设置 SSO。  
  
    2.  从列表中选择一个关联应用程序。  
  
         一个由企业单一登录工具创建的关联应用程序表示一个应用程序（如 TIBCO Rendezvous）。 用于 TIBCO Rendezvous 的 Microsoft BizTalk 适配器使用应用程序用户的凭据。 这些凭据是从服务器系统的 SSO 数据库中为指定关联应用程序检索的。  
  
        > [!NOTE]
        >  有关如何创建关联应用程序的信息，请参阅[创建关联应用程序](../core/creating-affiliate-applications1.md)。  
  
6.  单击**Apply**，然后单击**确定**提供接受连接信息所需的所有信息后。  
  
     必须设置为用于 TIBCO Rendezvous 以访问 TIBCO Rendezvous 的 BizTalk 适配器的连接参数。  


## <a name="next-steps"></a>后续步骤
  
-   [从 BizTalk Server 中使用 TIBCO Rendezvous 发送端口](../core/using-tibco-rendezvous-send-ports-from-biztalk-server.md)  
  
-   [TIBCO Rendezvous 中用于发送处理程序的数据类型映射](../core/data-type-mapping-for-send-handlers-in-tibco-rendezvous.md)  
  
-   [BizTalk Server 消息上下文属性（发送处理程序）](../core/biztalk-server-message-context-properties-send-handlers.md)