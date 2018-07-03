---
title: 单一登录： 事件 10524 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 55e26da3-f67f-4f87-92e5-2f8765b19989
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3f873dab5d4d5f00897e498e2bb88b6ae9a2f040
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37009502"
---
# <a name="single-sign-on-event-10524"></a>单一登录： 事件 10524
## <a name="details"></a>详细信息  

|                 |                                                                                                                                                                                             |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                                  企业单一登录                                                                                  |
| 产品版本 |                                                                 [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                  |
|    事件 ID     |                                                                                            10524                                                                                            |
|  事件源   |                                                                                           ENTSSO                                                                                            |
|    组件    |                                                                                             N\A                                                                                             |
|  符号名称  |                                                                               SSO_ERROR_RESTORE_SECRET_FAILED                                                                               |
|  消息正文   | 无法还原主密钥 secrets.%r<br /><br /> 文件名称: %1 %r<br /><br /> 当前 MSID: %2 %r<br /><br /> 上一个 MSID: %3 %r<br /><br /> 客户端用户: %4 %r<br /><br /> 错误代码： %5 |

## <a name="explanation"></a>解释  
 此错误事件表示用户尝试从备份文件还原主密钥失败。 这可能是由于权限问题（您必须是 SSO 管理员才能还原主密钥）或者可能是备份文件损坏。 在这些情况下应该有相关的邮件应用程序事件日志中。  

## <a name="user-action"></a>用户操作  
 若要解决此错误，请执行下列一项或多项操作:  

- 检查应用程序事件日志关联的事件或错误。  

- 检查您是否具有相应的 SSO 管理员权限。  

  有关详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：  

- [如何还原主密钥](../core/how-to-restore-the-master-secret.md)  

- [如何备份主密钥](../core/how-to-back-up-the-master-secret.md)  

- [如何生成主密钥](../core/how-to-generate-the-master-secret.md)
