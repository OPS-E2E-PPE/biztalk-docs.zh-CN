---
title: 配置 AS2 管道属性 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.edir2.AS2.pipeline.properties
ms.assetid: 7faf6b05-710a-4d00-8c77-590ce9d9f962
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7b8168af5ba8d9fbb242833011bfb0d9a51bdd96
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65391354"
---
# <a name="configuring-as2-pipeline-properties"></a>配置 AS2 管道属性
将使用管道属性处理传入或传出 AS2 消息时[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]无法确定解析为发送或接收交换的协议。  
  
## <a name="prerequisites"></a>先决条件  
 必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理员或[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]B2B Operators 组。  
  
## <a name="as2-pipeline-properties"></a>AS2 管道属性  
 可以在 AS2 管道中设置以下属性：  
  
|属性|改用|值|管道/阶段|  
|--------------|---------|------------|---------------------|  
|ContentTransferEncoding|指示将使用哪种方法表示 ASCII 文本格式的二进制数据。|8 位 （默认值）<br /><br /> 7bit<br /><br /> 8bit|AS2EdiSend/编码<br /><br /> AS2Send/编码|  
  
### <a name="to-set-a-pipeline-property"></a>若要设置管道属性  
  
1. 在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击接收位置或发送端口使用你想要设置的属性的管道。 单击 **“属性”**。  
  
2. 单击你想要设置的属性的管道旁的省略号按钮 （...）。  
  
3. 为属性输入值，然后单击**确定**。  
  
## <a name="see-also"></a>请参阅  
 [开发和配置 BizTalk Server AS2 解决方案](../core/developing-and-configuring-biztalk-server-as2-solutions.md)