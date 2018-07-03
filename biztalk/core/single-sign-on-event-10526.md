---
title: 单一登录： 事件 10526 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0f72d466-8b63-453c-b608-f9d64f635f65
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 433190146391c494ff3b890c8332cc15fb947753
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37024451"
---
# <a name="single-sign-on-event-10526"></a>单一登录： 事件 10526
## <a name="details"></a>详细信息  

|                 |                                                                                                                                                                   |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                     企业单一登录                                                                     |
| 产品版本 |                                                    [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                     |
|    事件 ID     |                                                                               10526                                                                               |
|  事件源   |                                                                              ENTSSO                                                                               |
|    组件    |                                                                                N\A                                                                                |
|  符号名称  |                                                                 SSO_ERROR_GENERATE_SECRET_FAILED                                                                  |
|  消息正文   | 生成新的主密钥失败。%r<br /><br /> 客户端用户: %1 %r<br /><br /> 客户端计算机：%2%r<br /><br /> 跟踪 ID: %3 %r<br /><br /> 错误代码： %4 |

## <a name="explanation"></a>解释  
 此错误事件表示用户尝试生成新的主密钥失败。 这可能是由于权限问题 （您必须是 SSO 管理员才能生成主密钥） 或可能没有主密钥写入备份文件的问题。 在这些情况下应该有相关的邮件应用程序事件日志中。  

## <a name="user-action"></a>用户操作  
 若要解决此错误，请执行下列一项或多项操作:  

- 检查应用程序事件日志关联的事件或错误。  

- 检查您是否具有相应的 SSO 管理员权限。  

  有关详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：  

- [如何生成主密钥](../core/how-to-generate-the-master-secret.md)  

- [管理主密钥](../core/managing-the-master-secret.md)
