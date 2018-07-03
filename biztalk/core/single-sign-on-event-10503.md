---
title: 单一登录： 事件 10503 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 04292ae8-8daf-4f5a-837e-fe5dfcd02b10
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b90af01551359b5caa1a5404facc9e3fece95673
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36990710"
---
# <a name="single-sign-on-event-10503"></a>单一登录： 事件 10503
## <a name="details"></a>详细信息  

|                 |                                                               |
|-----------------|---------------------------------------------------------------|
|  产品名称   |                   企业单一登录                   |
| 产品版本 |  [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]   |
|    事件 ID     |                             10503                             |
|  事件源   |                            ENTSSO                             |
|    组件    |                              N\A                              |
|  符号名称  |                SSO_ERROR_SERVICE_START_FAILED                 |
|  消息正文   | 无法启动 SSO 服务。%r<br /><br /> 错误代码： %1 |

## <a name="explanation"></a>解释  
 此错误事件表示由于出现异常导致无法启动 ENTSSO 服务。  

## <a name="user-action"></a>用户操作  
 若要解决此错误，请执行以下操作：  

- 检查应用程序和系统事件日志，以了解 ENTSSO 或其他服务的相关错误。  

  有关详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：  

- [使用 SSO](../core/using-sso.md)
