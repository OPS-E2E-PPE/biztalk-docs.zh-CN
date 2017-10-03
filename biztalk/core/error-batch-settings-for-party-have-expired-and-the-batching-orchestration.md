---
title: "方的批处理设置已过期，正在终止批处理业务流程 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a2f272b6-4da2-4736-8d61-ce48359f36dd
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5d56e06766a980c1ce293b211d2956a86c093726
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="the-batch-settings-for-party-have-expired-and-the-batching-orchestration-is-being-terminated"></a>参与方的批设置已过期，批处理业务流程被终止
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|事件 ID|-|  
|事件源|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|组件|批处理引擎|  
|符号名称|BatchSettingsExpired|  
|消息正文|参与方 {0} 的批处理设置已过期，批处理业务流程被终止。 在为此参与方激活批处理之前，不会生成其他批处理。|  
  
## <a name="explanation"></a>解释  
 此警告表明批处理业务流程实例已被停用，因为已达到激活范围的结尾。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请通过执行以下操作重新启动批处理过程：  
  
1.  打开 BizTalk Server 管理控制台，移动到“EDI 属性”对话框的“交换批处理创建设置”页。  
  
2.  重置的最终条件，并单击，然后重新启动业务流程**启动**。  
  
3.  开始日期时间是否在单击时的时间之前**启动**，单击**是**更新为当前日期时间的开始日期时间。