---
title: 单一登录：Event 10503 | Microsoft Docs
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
ms.openlocfilehash: 72b82421d4c70833f085b8e95c75c60cb1944545
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65243481"
---
# <a name="single-sign-on-event-10503"></a>单一登录：事件 10503
## <a name="details"></a>详细信息  

|                 |                                                               |
|-----------------|---------------------------------------------------------------|
|  产品名称   |                   企业单一登录                   |
| 产品版本 |  [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]   |
|    事件 ID     |                             10503                             |
|  事件源   |                            ENTSSO                             |
|    组件    |                              N\A                              |
|  符号名称  |                SSO_ERROR_SERVICE_START_FAILED                 |
|  消息正文   | SSO 服务无法 start.%r<br /><br /> 错误代码： %1 |

## <a name="explanation"></a>解释  
 此错误事件表示 ENTSSO 服务无法启动由于出现异常。  

## <a name="user-action"></a>用户操作  
 若要解决此错误，请执行以下操作：  

- 检查应用程序和系统事件日志中的 ENTSSO 或其他服务的相关错误。  

  有关详细信息，请参阅中的以下资源[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助：  

- [使用 SSO](../core/using-sso.md)
