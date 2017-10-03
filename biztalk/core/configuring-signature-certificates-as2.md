---
title: "配置签名证书 (AS2) |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8539e210-1656-4fff-b026-36b81689061f
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 32a52962976c2db62de902906f53f5c270e2c7c0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-signature-certificates-as2"></a>配置签名证书（AS2）
作为此页上设置的一部分，您可以指定用于签署所有传出消息的证书和用于解析此协议的 MDN。 此页上的设置将覆盖作为 BizTalk 组属性一部分提供的证书设置。 有关证书的使用方式的详细信息，请参阅[Configuring certificates for AS2 证书](../core/configuring-certificates-for-as2.md)。  
  
> [!IMPORTANT]
>  没有属性禁用此页上，即使你清除**本地 BizTalk 处理接收方或支持从该参与方发送消息的消息**时正在创建你为其创建参与方的复选框协议。  
  
## <a name="prerequisites"></a>先决条件  
 必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。  
  
### <a name="to-configure-agreement-level-signature-certificate"></a>配置协议层签名证书  
  
1.  创建 AS2 协议中所述[配置常规设置 (AS2)](../core/configuring-general-settings-as2.md)。 若要更新现有 AS2 协议，右键单击在协议**方和业务配置文件**页，然后单击**属性**。  
  
2.  单向协议选项卡上，单击**签名证书**。  
  
3.  选择**覆盖组签名证书**复选框以使用此页中提供用于对传出的 AS2 消息和 MDN 签名的证书。  
  
4.  单击**浏览**以显示**选择证书**对话框中，你在其中选择要应用于此方传输的消息的签名证书。  
  
5.  **公用名**文本框中显示所选证书的说明。  
  
6.  **指纹**文本框中显示证书的指纹。 证书指纹的格式 HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH，其中 H 是十六进制数字 （介于 0 到 9） 或从 A 到 F 字母。  
  
7.  单击**删除证书**若要删除所选的证书。  
  
8.  单击**应用**接受所做的更改，然后才能继续进行配置，或单击**确定**验证所做的更改，然后关闭对话框。  
  
## <a name="see-also"></a>另请参阅  
 [配置 AS2 协议属性](../core/configuring-as2-agreement-properties.md)