---
title: 在 BizTalk 中使用 WCF 自定义适配器和 Siebel 适配器配置端口 |Microsoft Docs
description: 创建 WCF 自定义发送和接收端口为 Siebel eBusiness 应用程序适配器使用 BizTalk Server 中
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 53c5ee07-36ae-474b-9241-8b53c9066ca1
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: df6d9e9cea34a9bfd95765ad4d37f51fcf55f4ff
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37017986"
---
# <a name="configure-a-port-using-the-wcf-custom-adapter-and-siebel-adapter"></a>使用 WCF 自定义适配器和 Siebel 适配器配置端口
本主题提供了说明如何配置 Wcf-custom 发送端口执行 Siebel 系统使用的出站操作[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。  
  
## <a name="prerequisites"></a>必要條件  
是的成员的帐户登录[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]Administrators 组或 BizTalk Operators 组。 详细了解权限的详细信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)，并[最低安全权限](https://social.technet.microsoft.com/wiki/contents/articles/24590.minimum-security-rights-for-biztalk-server-2006-to-2016.aspx)。
  
## <a name="deploying-adapters-for-sending-messages-to-a-siebel-system"></a>部署用于将消息发送到 Siebel 系统的适配器  
 执行以下步骤来配置 Wcf-custom 发送端口将消息发送到 Siebel 系统使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
 
1. 启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
2. 在控制台树中，展开**BizTalk 组**，然后展开**应用程序**。  
  
3. 展开你想要部署的应用程序[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。  
  
4. 右键单击**发送端口**，依次指向**新建**，并指向你想要根据 BizTalk Server 和 Siebel 系统之间的通信的模式配置的端口的类型。  
  
5. 在中**发送端口属性**对话框中，在**常规**选项卡上，键入发送端口的名称。  
  
6. 从**类型**下拉列表中，选择**WCF 自定义**然后单击**配置**。  
  
7. 在中**Wcf-custom 传输属性**对话框框中，执行以下操作：  
  
   1. 单击**常规**选项卡并在**地址 (URI)** 字段指定连接 URI 连接到 Siebel 系统。 有关连接 URI 的详细信息，请参阅[创建 Siebel 系统连接 URI](../../adapters-and-accelerators/adapter-siebel/create-the-siebel-system-connection-uri.md)。  
  
   2. 上**常规**选项卡上，在**操作**文字框中，键入操作的操作。 请参阅[消息和消息架构](messages-and-message-schemas-for-siebel-adapter-in-biztalk.md)有关每个操作的操作的列表。 例如，要调用帐户业务组件上的插入操作的操作是：  
  
      ```  
      http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Insert  
      ```  
  
   3. 单击**绑定**选项卡和从**绑定类型**下拉列表中，选择**siebelBinding**。 此外可以指定不同的绑定属性公开的[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。 有关详细信息，请参阅[了解关于 BizTalk Adapter for Siebel 绑定属性](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md)。  
  
   4. 单击**凭据**选项卡上，执行下列操作之一：  
  
      - 选择**不使用单一登录**选项，然后指定用户名和密码以连接到 Siebel 系统。  
  
      - 选择**使用单一登录**选项，并指定关联 ESSO 应用程序。  
  
        有关与 BizTalk Server 相关的安全性的详细信息，请参阅[Siebel 适配器与 BizTalk Server 安全性](../../adapters-and-accelerators/adapter-siebel/security-with-siebel-adapter-and-biztalk-server.md)。  
  
   5. 若要返回到**发送端口属性**对话框中，单击**确定**。  
  
8. 从**发送处理程序**下拉列表中，选择**BizTalkServerApplication**。  
  
9. 如果在步骤 4 中选择静态单向发送端口，指定发送管道。 从**发送管道**下拉列表中，选择对应于 XMLTransmit 管道。  
  
10. 如果你在步骤 4 中选择静态要求响应端口，指定发送和接收管道。  
  
    1.  从**发送管道**下拉列表中，选择对应于 XMLTransmit 管道。  
  
    2.  从**接收管道**下拉列表中，选择对应于 XMLReceive 管道。  
  
11. 单击“确定” 。  
  
## <a name="see-also"></a>请参阅  
[手动配置到 Siebel 适配器的物理端口绑定](../../adapters-and-accelerators/adapter-siebel/manually-configure-a-physical-port-binding-to-the-siebel-adapter.md)