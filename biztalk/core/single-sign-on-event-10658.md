---
title: 单一登录：Event 10658 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c5bee12d-502b-4fee-bc84-25807eb0e48e
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b8ac64b60ba9a4d92452b3299f0e1f30cef192d6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397615"
---
# <a name="single-sign-on-event-10658"></a>单一登录：事件 10658
## <a name="details"></a>详细信息  

|                 |                                                                                   |
|-----------------|-----------------------------------------------------------------------------------|
|  产品名称   |                             企业单一登录                             |
| 产品版本 |            [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]             |
|    事件 ID     |                                       10658                                       |
|  事件源   |                                      ENTSSO                                       |
|    组件    |                                        N\A                                        |
|  符号名称  |                   SSO_ERROR_PASSWORD_SYNC_ADAPTERS_START_FAILED                   |
|  消息正文   | 外部适配器的密码同步无法 start.%r<br /><br /> 错误代码： %1 |

## <a name="explanation"></a>解释  
 此错误事件表示无法启动的外部适配器的密码同步。  

## <a name="user-action"></a>用户操作  
 若要解决此错误，请执行下列一项或多项操作:  

-   检查应用程序和系统事件日志中的关联事件。  

-   验证适配器配置属性。  

## <a name="more-info"></a>详细信息  

- [如何管理密码同步](../core/how-to-administer-password-synchronization.md)  

- **企业单一登录的用户界面帮助** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
