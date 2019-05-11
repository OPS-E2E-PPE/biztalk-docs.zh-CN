---
title: 单一登录：Event 10524 | Microsoft Docs
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
ms.openlocfilehash: d135f8856707527eb3368b579b6f77d541cbb84b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65262558"
---
# <a name="single-sign-on-event-10524"></a>单一登录：事件 10524
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
 此错误事件表示用户尝试从备份文件还原主密钥失败。 这可能是由于权限问题 （您必须是 SSO 管理员才能还原主密钥） 或可能是因为备份文件的文件损坏。 在这些情况下应该有相关的邮件应用程序事件日志中。  

## <a name="user-action"></a>用户操作  
 若要解决此错误，请执行下列一项或多项操作:  

- 检查应用程序事件日志关联的事件或错误。  

- 检查你具有相应的 SSO 管理员权限。  

  有关详细信息，请参阅中的以下资源[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助：  

- [如何还原主密钥](../core/how-to-restore-the-master-secret.md)  

- [如何备份主密钥](../core/how-to-back-up-the-master-secret.md)  

- [如何生成主密钥](../core/how-to-generate-the-master-secret.md)
