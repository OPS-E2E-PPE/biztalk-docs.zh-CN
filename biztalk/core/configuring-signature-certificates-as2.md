---
title: 配置签名证书 (AS2) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8539e210-1656-4fff-b026-36b81689061f
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aa26611b0937385b74773aa4cd9c78477c7e3378
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65355200"
---
# <a name="configuring-signature-certificates-as2"></a>配置签名证书 (AS2)
作为此页上设置的一部分，可以指定要用于签名的所有传出消息和 MDN 的解析此协议的证书。 此页上的设置替代的 BizTalk 组属性一部分提供的证书设置。 有关如何使用证书的详细信息，请参阅[as2 配置证书](../core/configuring-certificates-for-as2.md)。  
  
> [!IMPORTANT]
>  没有属性禁用此页上，即使您清除**本地 BizTalk 处理参与方或支持来自此参与方发送消息的接收的消息**要为其创建的参与方时的复选框协议。  
  
## <a name="prerequisites"></a>先决条件  
 必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理员或[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]B2B Operators 组。  
  
### <a name="to-configure-agreement-level-signature-certificate"></a>若要配置协议层签名证书  
  
1.  创建 AS2 协议中所述[配置常规设置 (AS2)](../core/configuring-general-settings-as2.md)。 若要更新现有 AS2 协议，请右键单击中的协议**参与方和业务配置文件**页，然后单击**属性**。  
  
2.  在单向协议选项卡上，单击**签名证书**。  
  
3.  选择**覆盖组签名证书**复选框以使用此页中提供的签名传出 AS2 消息和 MDN 的证书。  
  
4.  单击**浏览**以显示**选择证书**对话框中，在其中选择要应用到由此参与方传输的消息的签名证书。  
  
5.  **公用名**文本框显示所选证书的说明。  
  
6.  **指纹**文本框将显示证书的指纹。 证书指纹的格式 HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH，其中 H 为十六进制数字 （从 0 到 9 的数字） 或为从 A 到 F 的字母。  
  
7.  单击**删除证书**若要删除所选的证书。  
  
8.  单击**Apply**以接受更改，然后才能继续进行配置，或单击**确定**以验证所做的更改，然后关闭对话框。  
  
## <a name="see-also"></a>请参阅  
 [配置 AS2 协议属性](../core/configuring-as2-agreement-properties.md)