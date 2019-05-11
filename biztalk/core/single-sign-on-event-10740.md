---
title: 单一登录：Event 10740 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8e8521e7-32af-4a58-8b1a-66ea1d13f1e1
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: db19b81cb024ff6dfee2196cdefc33f8f977dea9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65291751"
---
# <a name="single-sign-on-event-10740"></a>单一登录：事件 10740
## <a name="details"></a>详细信息  

|                 |                                                                                                                                                            |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                 企业单一登录                                                                  |
| 产品版本 |                                                 [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                 |
|    事件 ID     |                                                                           10740                                                                            |
|  事件源   |                                                                           ENTSSO                                                                           |
|    组件    |                                                                            N\A                                                                             |
|  符号名称  |                                                               SSO_WARN_INVALID_WINDOWS_USER                                                                |
|  消息正文   | Windows 帐户不是有效的应用程序 update.%r<br /><br /> 应用程序名称: %1 %r<br /><br /> Windows 帐户: %2 %r<br /><br /> 错误代码： %3 |

## <a name="explanation"></a>解释  
 此警告事件表示 （事件消息中指定） 的 Windows 帐户对于应用程序更新无效。 更改主机组应用程序的 Windows 帐户时会发生该错误。 主机组应用程序用于实现单一登录从外部系统到 Windows 系统。 它们可以将一组外部用户映射到单个 Windows 帐户。 在应用程序的应用程序用户字段中定义映射到 Windows 帐户。  

## <a name="user-action"></a>用户操作  
 若要解决此警告，请执行以下操作：  

- 检查 Windows 帐户正在使用无效。  

- 重新创建具有正确的 Windows 帐户属性的 Windows 帐户。  

  有关详细信息，请参阅下列资源：  

- [密码同步](../core/password-synchronization2.md)
