---
title: 单一登录：Event 10654 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 49372d5a-8136-4bdd-8004-b5736ddbe058
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 703462b0d4988a60bc0d6fc6b11629fe3dbe0502
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397650"
---
# <a name="single-sign-on-event-10654"></a>单一登录：事件 10654
## <a name="details"></a>详细信息  

|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  产品名称   |                 企业单一登录                  |
| 产品版本 | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    事件 ID     |                           10654                            |
|  事件源   |                           ENTSSO                           |
|    组件    |                            N\A                             |
|  符号名称  |        SSO_ERROR_PS_WINDOWS_CALLBACK_ACCESS_DENIED         |
|  消息正文   |    密码同步服务器 （适用于 Windows) 访问 denied.%r     |

## <a name="explanation"></a>解释  
 此错误事件表示一条消息发送到 [名称] 服务器但回复受到阻止。 原因可能是多种不同原因，例如协议不正确或服务器上没有足够的安全权限。  

## <a name="user-action"></a>用户操作  
 若要解决此错误，请执行以下操作：  

- 请注意此消息中的信息和事件日志中的任何相关信息，请与 Microsoft 产品支持服务联系。  

  有关详细信息，请参阅中的以下资源[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助：  

- [密码同步](../core/password-synchronization2.md)
