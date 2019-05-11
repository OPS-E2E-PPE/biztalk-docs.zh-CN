---
title: 配置接收器 MDN 设置 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: eae6431d-a2b9-4889-a29c-720e801a644e
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 62c4362ad8acb40bd34f9e0f89751a456ff0fa84
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390833"
---
# <a name="configuring-receiver-mdn-settings"></a>配置接收器 MDN 设置
作为接收方 MDN 设置的一部分，可以指定控制 MDN 生成基于 AS2 消息标头的属性。  
  
> [!IMPORTANT]
>  没有属性上将禁用**参与方 A-> 参与方 B**单向协议选项卡，如果您清除**本地 BizTalk 处理参与方或支持来自此参与方发送消息的接收的消息**复选框为参与方 a。但是，禁用中相同页面上的所有属性**参与方 B-> 参与方 A**选项卡上，如果您创建参与方 A.时选中复选框  
  
## <a name="prerequisites"></a>先决条件  
 必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理员或[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]B2B Operators 组。  
  
### <a name="to-configure-receiver-mdn-settings"></a>若要配置接收方 MDN 设置  
  
1.  创建 AS2 协议中所述[配置常规设置 (AS2)](../core/configuring-general-settings-as2.md)。 若要更新现有 AS2 协议，请右键单击中的协议**参与方和业务配置文件**页，然后单击**属性**。  
  
2.  在单向协议选项卡下**本地主机设置**部分中，单击**接收器 MDN 设置**。  
  
3.  如果未选中**使用的验证和 MDN 的协议设置而非消息标头**属性中的**验证**页上，你可以选择允许发送 MDN 的参与方签名 MDN，如果通过启用 MDN 生成**处置-到通知**AS2 标头，但**处置通知选项**标头不会启用签名。 发生这种情况**处置通知选项**未设置或设置为可选。 就可以通过单击**请求的 MDN 签名不预设处置通知选项标头是否已签名回执协议标头设置为可选**。  
  
4.  可以输入中文**MDN 文本**字段使参与方发送 MDN 将其添加到 MDN 消息 （位于下的内容说明字段中）。 此设置的而不考虑是否根据 AS2 标头或协议属性生成 MDN。  
  
5.  单击**Apply**以接受更改，然后才能继续进行配置，或单击**确定**以验证所做的更改，然后关闭对话框。  
  
## <a name="see-also"></a>请参阅  
 [配置本地主机设置 (AS2)](../core/configuring-local-host-settings-as2.md)