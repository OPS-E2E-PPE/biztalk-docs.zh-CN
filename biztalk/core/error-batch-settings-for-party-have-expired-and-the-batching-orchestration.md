---
title: 参与方的批设置已过期，批处理业务流程被终止 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a2f272b6-4da2-4736-8d61-ce48359f36dd
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 471d42035f0c8c279fd25e8bb5ba480f7e0f962a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36990054"
---
# <a name="the-batch-settings-for-party-have-expired-and-the-batching-orchestration-is-being-terminated"></a>参与方的批设置已过期，批处理业务流程被终止
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                                                       |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                   |
| 产品版本 |                                                              [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                               |
|    事件 ID     |                                                                                           -                                                                                           |
|  事件源   |                                                [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI                                                 |
|    组件    |                                                                                    批处理引擎                                                                                    |
|  符号名称  |                                                                                 BatchSettingsExpired                                                                                  |
|  消息正文   | 参与方的批处理设置{0}已过期，批处理业务流程被终止。 在为此参与方激活批处理之前，不会生成其他批处理。 |
  
## <a name="explanation"></a>解释  
 此警告表明批处理业务流程实例已被停用，因为已达到激活范围的结尾。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请通过执行以下操作重新启动批处理过程：  
  
1.  打开 BizTalk Server 管理控制台，移动到“EDI 属性”对话框的“交换批处理创建设置”页。  
  
2.  重置结束条件，并单击，然后重新启动该业务流程**启动**。  
  
3.  在单击时的时间之前开始日期时间是否**启动**，单击**是**以开始日期时间更新为当前日期时间。