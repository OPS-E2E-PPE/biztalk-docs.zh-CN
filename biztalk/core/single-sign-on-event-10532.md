---
title: 单一登录：事件 10532 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ae2112bc-b53c-4d99-9dc1-a2f55dda4665
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3ea52d8e64f5a59a633a6e22eef7220f44b36f77
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65262344"
---
# <a name="single-sign-on-event-10532"></a>单一登录：事件 10532
## <a name="details"></a>详细信息  

|                 |                                                                                                                                                                                     |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                              企业单一登录                                                                              |
| 产品版本 |                                                             [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                              |
|    事件 ID     |                                                                                        10532                                                                                        |
|  事件源   |                                                                                       ENTSSO                                                                                        |
|    组件    |                                                                                         CO                                                                                          |
|  符号名称  |                                                                             SSO_WARN_LOST_SECRET_SERVER                                                                             |
|  消息正文   | 检索主密钥失败。 验证主密钥服务器名称正确，以及它是 available.%r<br /><br /> 密钥服务器名称: %1 %r<br /><br /> 错误代码： %2 |

## <a name="explanation"></a>解释  
 此警告事件表示获取主密钥的请求已失败。 这可能是因为未在服务器上运行企业单一登录服务。  

## <a name="user-action"></a>用户操作  
 若要解决此警告，请执行一个或多个以下操作：  

- 检查应用程序事件日志关联的事件或错误。  

- 验证主密钥服务器名称正确。  

- 验证主密钥服务器处于联机状态并且正在运行企业单一登录服务。  

  有关详细信息，请参阅中的以下资源[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助：  

- [如何生成主密钥](../core/how-to-generate-the-master-secret.md)  

- [管理主密钥](../core/managing-the-master-secret.md)
