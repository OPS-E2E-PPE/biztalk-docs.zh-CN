---
title: 单一登录：Event 10535 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9b570b0b-5c45-4be3-80c9-a2c50601b677
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c4c6fc30ad5b0953ddecaad3266dec787e210429
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65262347"
---
# <a name="single-sign-on-event-10535"></a>单一登录：事件 10535
## <a name="details"></a>详细信息  

|                 |                                                                                                                                                                       |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                       企业单一登录                                                                       |
| 产品版本 |                                                      [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                       |
|    事件 ID     |                                                                                 10535                                                                                 |
|  事件源   |                                                                                ENTSSO                                                                                 |
|    组件    |                                                                                  CO                                                                                   |
|  符号名称  |                                                                          SSO_INFO_API_AUDIT                                                                           |
|  消息正文   | SSO AUDIT %r<br /><br /> 函数: %1 %r<br /><br /> 跟踪 ID: %2 %r<br /><br /> 客户端计算机: %3 %r<br /><br /> 客户端用户: %4 %r<br /><br /> 应用程序名称： %5 |

## <a name="explanation"></a>解释  
 此信息审核事件指示发生满足用户定义的审核级别的事件。 此事件消息包括：  

 **函数：** 正在执行的函数  

 **跟踪 ID:** 当首次调用 SSO API 时，生成的唯一 GUID。  

 **客户端计算机：** 生成函数的客户端计算机。  

 **客户端用户：** 调用该函数的用户帐户的名称。  

 **应用程序名称：** 名称的 SSO 关联应用程序与此函数相关联。  

 此类型的事件用于在开发期间诊断问题、 故障排除，或正在运行的应用程序。 提供的信息可以用于确定正在进行的 SSO API 调用。  

 可以将审核级别设置为 0/1/2/3 – 0 意味着"无"、 1 意味着"低"显示仅限错误、 2 意味着"medium"显示错误和警告，和 3 意味着"高"显示所有审核消息。  

## <a name="user-action"></a>用户操作  

- 检查关联的事件消息的事件日志。  

  有关详细信息，请参阅中的以下资源[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助：  

- [如何审核 SSO](../core/how-to-audit-sso.md)  

- [使用 SSO](../core/using-sso.md)
