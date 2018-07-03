---
title: 无效的地址方案 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0b059289-654e-40d6-a092-2a685e6e10f7
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5c9a0e7a9c200d2efc7d0e6e81158379200d55af
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980998"
---
# <a name="invalid-address-scheme"></a>地址方案无效
## <a name="details"></a>详细信息  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  产品名称   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| 产品版本 |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    事件 ID     |                                        000                                         |
|  事件源   |                                         0                                          |
|    组件    |                                         0                                          |
|  符号名称  |                                         0                                          |
|  消息正文   |                  无效的地址方案;应为"{0}"方案。                   |
  
## <a name="explanation"></a>解释  
 您提供的协议纲要与传输绑定定义的类型不匹配。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请执行以下操作：  
  
1. 单击**启动**，单击**所有程序**，单击**Microsoft [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]** ，然后单击**BizTalk Server 管理**。  
  
2. 在控制台根目录中，展开**BizTalk Server 管理**，展开**BizTalk 组**，然后展开**应用程序**。  
  
3. 找到你的应用程序，然后找到您的传输。  
  
4. 右键单击传输名称。  
  
5. 单击 **“属性”**。  
  
6. 在端口**类型**列表中，选择正确的端口。  
  
7. 单击**配置**。  
  
8. 在中**WCF [**<em>传输类型</em>**] 传输属性**对话框中，单击**常规**选项卡。  
  
9. 在中**地址 (URI)** 文字框中，确保地址值与正在使用的 WCF 适配器的类型相匹配。  
  
   此外，如果使用系统提供的绑定类型使用 Wcf-custom 适配器，检查的值**绑定类型**上列出**绑定**选项卡。如果**绑定类型**配置为**customBinding**，地址应与传输绑定元素中列出匹配**绑定类型**上列表**绑定**选项卡。