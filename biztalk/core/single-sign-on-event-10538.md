---
title: 单一登录： 事件 10538 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1211ac33-9149-4dd3-85a2-d46eb24d1060
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9f4b7fba63d26fde664e14470eb95b41a1580ae7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975774"
---
# <a name="single-sign-on-event-10538"></a>单一登录： 事件 10538
## <a name="details"></a>详细信息  

|                 |                                                                           |
|-----------------|---------------------------------------------------------------------------|
|  产品名称   |                         企业单一登录                         |
| 产品版本 |        [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]         |
|    事件 ID     |                                   10538                                   |
|  事件源   |                                  ENTSSO                                   |
|    组件    |                                    CO                                     |
|  符号名称  |                           SSO_WARN_APP_DISABLED                           |
|  消息正文   | 目前禁用了此应用程序。%r<br /><br /> 应用程序名称： %1 |

## <a name="explanation"></a>解释  
 此警告事件表示应用程序管理员已禁用了 SSO 关联应用程序。  

## <a name="user-action"></a>用户操作  
 若要解决此警告问题，请执行以下一项或多项操作：  

- 联系应用程序管理员以启用 SSO 关联应用程序。 可使用 SSO 管理工具（GUI 或命令行）完成此操作。  

  有关详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：  

- [如何启用关联应用程序](../core/how-to-enable-an-affiliate-application.md)  

- [如何禁用关联应用程序](../core/how-to-disable-an-affiliate-application.md)
