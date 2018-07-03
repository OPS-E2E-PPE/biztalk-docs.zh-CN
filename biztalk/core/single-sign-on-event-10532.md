---
title: 单一登录： 事件 10532 |Microsoft Docs
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
ms.openlocfilehash: 135060013686ff24e4f2692bda0e8829189e1c4a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974846"
---
# <a name="single-sign-on-event-10532"></a>单一登录： 事件 10532
## <a name="details"></a>详细信息  

|                 |                                                                                                                                                                                     |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                              企业单一登录                                                                              |
| 产品版本 |                                                             [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                              |
|    事件 ID     |                                                                                        10532                                                                                        |
|  事件源   |                                                                                       ENTSSO                                                                                        |
|    组件    |                                                                                         CO                                                                                          |
|  符号名称  |                                                                             SSO_WARN_LOST_SECRET_SERVER                                                                             |
|  消息正文   | 检索主密钥失败。 请确保主密钥服务器名称正确且该服务器可用。%r<br /><br /> 密钥服务器名称: %1 %r<br /><br /> 错误代码： %2 |

## <a name="explanation"></a>解释  
 此警告事件表示，获得主密钥的请求失败。 这可能是因为企业单一登录服务未在服务器上运行。  

## <a name="user-action"></a>用户操作  
 若要解决此警告问题，请执行以下一项或多项操作：  

- 检查应用程序事件日志关联的事件或错误。  

- 验证主密钥服务器名称是否正确。  

- 验证主密钥服务器是否联机，以及企业单一登录服务是否正在运行。  

  有关详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：  

- [如何生成主密钥](../core/how-to-generate-the-master-secret.md)  

- [管理主密钥](../core/managing-the-master-secret.md)
