---
title: "无效的地址方案 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0b059289-654e-40d6-a092-2a685e6e10f7
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 385f3aca555f18599887897f6b60144070f252a2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="invalid-address-scheme"></a>地址方案无效
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|事件 ID|000|  
|事件源|0|  
|组件|0|  
|符号名称|0|  
|消息正文|无效的地址方案;应为"{0}"方案。|  
  
## <a name="explanation"></a>解释  
 您提供的协议纲要与传输绑定定义的类型不匹配。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请执行以下操作：  
  
1.  单击**启动**，单击**所有程序**，单击**Microsoft [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]** ，然后单击**BizTalk Server 管理**。  
  
2.  在控制台根目录中，展开**BizTalk Server 管理**，展开**BizTalk 组**，然后展开**应用程序**。  
  
3.  找到应用程序，然后找到您的传输。  
  
4.  右键单击传输名称。  
  
5.  单击 **“属性”**。  
  
6.  在端口**类型**列表中，选择正确的端口。  
  
7.  单击**配置**。  
  
8.  在**WCF [***传输类型***] 传输属性**对话框中，单击**常规**选项卡。  
  
9. 在**地址 (URI)**文本中，确保地址值匹配的 WCF 适配器正在使用的类型。  
  
 此外，如果你与系统提供的绑定类型一起使用的 WCF 自定义适配器，检查的值**绑定类型**列表上**绑定**选项卡。如果**绑定类型**配置为**customBinding**，地址应与匹配传输绑定元素中列出**绑定类型**上列表**绑定**选项卡。