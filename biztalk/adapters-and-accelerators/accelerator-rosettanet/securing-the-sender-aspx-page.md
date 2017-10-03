---
title: "保护发件人 ASPX 页 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ASPX pages, protocol rules
- security, ASPX pages
- RNIFSend.aspx
- ASPX pages, security
- protocol rules [ASPX pages]
ms.assetid: 8214e3f5-a8e9-4d71-957d-ed0852035030
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a0c5d5ec97d4d4aed862ffc1dbc0d75d0c0430d7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="securing-the-sender-aspx-page"></a>保护发件人 ASPX 页
本主题介绍如何防止未经授权的使用 RNIFSend.aspx 页。 有两个过程，你可以使用：  
  
-   在 Internet 信息服务 (IIS) 管理器中，安全 RNIFSend.aspx 以确保任何未经授权的服务器将使用 RNIFSend.aspx 页将未经授权的消息从你的网络传输。  
  
-   使用 Microsoft Internet Security and Acceleration (ISA) Server 创建的传出 HTTP 请求的协议规则。  
  
### <a name="to-secure-rnifsendaspx"></a>若要保护 RNIFSend.aspx  
  
1.  在 Web 服务器上用于 RNIF 消息传输，单击**启动**，指向**所有程序**，指向**管理工具**，然后单击**Internet Information Services (IIS) 管理器**。  
  
2.  在 IIS 管理器中，展开本地计算机节点，展开**网站**，然后展开**Default Web Site**。  
  
3.  单击**BTARNApp**，然后在右窗格中，右键单击**RNIFSend.aspx**。  
  
4.  单击 **“属性”**。 上**文件安全性**选项卡上，在**IP 地址和域名限制**部分中，单击**编辑**。  
  
5.  在 IP 地址和域名限制对话框中，单击**拒绝访问**，然后单击**添加**。  
  
6.  在**授予访问权限**对话框中，添加所有 BizTalk 服务器执行发送操作。 添加一台服务器，请单击**单台计算机**。 在**IP 地址**框中，键入计算机的 IP 地址，然后单击**确定**。  
  
7.  添加一组服务器，请单击**计算机组**，然后执行以下：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**网络 ID**|键入你想要使用的网络。|  
    |**子网掩码**|键入你想要使用的子网掩码。|  
  
8.  单击 **“确定”**。  
  
    > [!NOTE]
    >  如果你具有分隔到另一个实例上运行的单独主机的所有发送操作，你只需添加此计算机。 你可以拒绝所有其他用户的访问。  
  
9. 单击**确定**，然后单击**确定**试。  
  
### <a name="to-create-a-protocol-rule-of-outgoing-http-requests"></a>若要创建的传出 HTTP 请求的协议规则  
  
1.  在 ISA 管理中，单击**访问策略**，然后单击**协议规则**。  
  
2.  创建一个名为的新协议规则**HTTP**使用 TCP 协议。  
  
3.  在属性页的新 HTTP 协议规则，在**适用于**选项卡上，选择**适用于以下指定的客户端地址集**。 输入仅这些客户端想要访问页的 Ip。  
  
## <a name="see-also"></a>另请参阅  
 [管理配置、 证书、 数据库和安全](manage-configuration-certificates-databases-security.md)