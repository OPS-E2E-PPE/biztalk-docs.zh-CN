---
title: "如何设置 TIBCO 会合传输属性 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- setting transport properties
- transport properties, setting
ms.assetid: db8e8a57-a942-44d7-a651-623aa614c6be
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9c9ff40d5319daa0a71d67aa3fd132c3d115923e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-set-tibco-rendezvous-transport-properties"></a>如何设置 TIBCO Rendezvous 传输属性
TIBCO Rendezvous 传输属性用于运行时。 在**传输属性**屏幕上，你设置标识你想要将生成的消息发布 TIBCO 会合域的连接参数。  
  
### <a name="to-specify-tibco-rendezvous-transport-properties"></a>指定 TIBCO Rendezvous 传输属性  
  
1.  上**TIBCO 会合传输属性**屏幕中，展开**认证发件人属性**并输入以下信息。  
  
     ![](../core/media/sadp-tibcoren-transs.gif "SAdp_TibcoRen_Transs")  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**分类帐名称**|默认值为空。 用于持久性认证消息传递的分类帐文件名。 仅限使用本地驱动器。|  
    |**可重用的名称**|默认值为空。 用于已验证消息传递的可重用的通信名称。 在网络上所有已验证消息通信名称中，该名称必须是唯一的。|  
  
2.  展开**凭据**然后输入服务器连接的以下信息。  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**密码**|默认值为空。 登录到 Tibco Rendezvous 守护程序的密码。|  
    |**用户名**|默认值为空。 Tibco Rendezvous 守护程序的用户名称。|  
  
3.  展开**常规设置**然后输入 TIBCO 会合服务器连接的以下信息。  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**代码页编号**|默认值是 65001（UTF-8 编码代码页）。 这是 TIBCO Rendezvous SDK 用于字符串编码的代码页。|  
    |**默认使用者名称**|默认值为空。 使用者名称在业务流程中设置。 如果一个端口用于一种消息类型，您可以提供一个默认使用者名称，并通过删除设置使用者名称属性需求来简化业务流程。|  
    |**启用时间批处理**|默认值为 False。 启用/禁用 TIBCO Rendezvous 时间批处理功能。|  
    |**将不受支持的类型映射到字符串**|默认值为 True。 如果为 True，在可能的情况将不受支持的类型映射到字符串。 如果为 False，则生成运行时错误。|  
    |**对二进制文件，如 TIBCO 会合程序集的路径**|如果此信息已不在该路径环境变量中，则提供此信息。|  
    |**意味着保留顺序**|默认值为 True。 启用逻辑以按从 BizTalk Server 接收消息的相同顺序发送消息到 TIBCO Rendezvous。 此参数强制按相同顺序发布；但不表示订阅者按相同的顺序接收。|  
    |**发送端口标识符**|此标识符出现在与此端口关联的日志消息中。 它作为方便提供。|  
  
4.  展开**会合传输**和输入 TIBCO 会合服务器连接的信息，请单击**应用**，然后单击**确定**。  
  
     您必须为用于 TIBCO Rendezvous 的 Microsoft BizTalk 适配器设置连接参数以访问 TIBCO Rendezvous。  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**后台程序**|默认值为空。<br /><br /> Rendezvous 传输后台程序参数。|  
    |**网络**|默认值为空。<br /><br /> Rendezvous 传输网络参数。|  
    |**服务**|默认值为空。<br /><br /> Rendezvous 传输服务参数。|  
  
5.  使用单一登录 (SSO) 提供凭据。  
  
     有两种方法可用于访问 TIBCO Rendezvous 系统。 您可以使用凭据（用户名和密码参数）或单一登录。  
  
    1.  选择**是**中**使用 SSO**用于单一登录。  
  
        > [!NOTE]
        >  请参阅[使用单一登录](../core/using-single-sign-on5.md)有关如何设置 SSO 信息。  
  
    2.  从列表中选择一个关联应用程序。  
  
         一个由企业单一登录工具创建的关联应用程序表示一个应用程序（如 TIBCO Rendezvous）。 用于 TIBCO Rendezvous 的 Microsoft BizTalk 适配器使用应用程序用户的凭据。 这些凭据是从服务器系统的 SSO 数据库中为指定关联应用程序检索的。  
  
        > [!NOTE]
        >  有关如何创建关联应用程序的信息，请参阅[创建关联应用程序](../core/creating-affiliate-applications1.md)。  
  
6.  单击**应用**，然后单击**确定**后提供所有必要的信息，以接受连接信息。  
  
     你必须设置为 TIBCO 会合访问 TIBCO 会合的 BizTalk 适配器的连接参数。  
  
## <a name="see-also"></a>另请参阅  
 [创建 TIBCO 会合发送处理程序](../core/creating-tibco-rendezvous-send-handlers.md)