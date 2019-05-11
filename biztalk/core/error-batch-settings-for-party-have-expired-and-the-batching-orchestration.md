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
ms.openlocfilehash: 896eb6325aa2bac076908643e582d286f2b5febe
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389406"
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
|  消息正文   | 参与方的批处理设置{0}已过期，批处理业务流程被终止。 为此参与方激活批处理之前，将不会生成其他批处理。 |
  
## <a name="explanation"></a>解释  
 此警告表明批处理业务流程实例由于已达到激活范围的末尾已被停用。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请执行以下操作重新启动批处理过程：  
  
1.  打开 BizTalk Server 管理控制台，然后转到交换批处理创建设置页的 EDI 属性对话框。  
  
2.  重置结束条件，并单击，然后重新启动该业务流程**启动**。  
  
3.  在单击时的时间之前开始日期时间是否**启动**，单击**是**以开始日期时间更新为当前日期时间。