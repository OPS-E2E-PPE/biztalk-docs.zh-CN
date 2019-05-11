---
title: 单一登录：Event 10742 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ba62f878-ed12-421f-81ea-9285b2624fe9
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: afe1849acf5ad6cbafb948465a0cbc8f8f06ba84
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400576"
---
# <a name="single-sign-on-event-10742"></a>单一登录：事件 10742
## <a name="details"></a>详细信息  

|                 |                                                                                                                                                                                                                                                                                                            |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                                                                                         企业单一登录                                                                                                                                          |
| 产品版本 |                                                                                                                         [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                         |
|    事件 ID     |                                                                                                                                                   10742                                                                                                                                                    |
|  事件源   |                                                                                                                                                   ENTSSO                                                                                                                                                   |
|    组件    |                                                                                                                                                    N\A                                                                                                                                                     |
|  符号名称  |                                                                                                                                         SSO_WARN_NO_UPDATE_ADAPTER                                                                                                                                         |
|  消息正文   | 客户端用户必须是 SSO 管理员帐户或应用程序管理员帐户的成员才能更新 adapter.%r<br /><br /> 客户端用户: %1 %r<br /><br /> SSO Administrators: %2 %r<br /><br /> 应用程序管理员: %3 %r<br /><br /> 适配器: %4 %r<br /><br /> 错误代码： %5 |

## <a name="explanation"></a>解释  
 此警告事件表示尝试更新指定的适配器已进行，但是无法完成，因为使用的用户帐户不是 SSO 管理员帐户或应用程序管理员帐户的成员。  

## <a name="user-action"></a>用户操作  
 若要解决此警告，请执行一个或多个以下操作：  

- 将用户帐户添加到 SSO Administrators 帐户或应用程序管理员帐户。  

- 重试更新。  

  有关详细信息，请参阅下列资源：  

- [如何管理密码同步](../core/how-to-administer-password-synchronization.md)
