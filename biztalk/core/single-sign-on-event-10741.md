---
title: 单一登录： 事件 10741 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 58b6b093-d136-498f-a3b5-c413150da956
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1901ad4c58f3056b74f50fead72637bc9bb8b62e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37006830"
---
# <a name="single-sign-on-event-10741"></a>单一登录： 事件 10741
## <a name="details"></a>详细信息  

|                 |                                                                                           |
|-----------------|-------------------------------------------------------------------------------------------|
|  产品名称   |                                 企业单一登录                                 |
| 产品版本 |                [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                 |
|    事件 ID     |                                           10741                                           |
|  事件源   |                                          ENTSSO                                           |
|    组件    |                                            N\A                                            |
|  符号名称  |                                SSO_WARN_SAVING_REPLAY_FILE                                |
|  消息正文   | 正在保存重播文件或进度文件。%r<br /><br /> 保存的文件: %1 %r<br /><br /> 错误代码： %2 |

## <a name="explanation"></a>解释  
 此警告事件表明 SSO 正在保存重播文件或进度文件。  

 ENTSSO 服务器无法与 SSO 数据库取得联系时，密码同步使用重播文件。 进度文件指示，距离通过 SSO 无法重播文件中用例联系人与 SSO 数据库会再次读取。  

## <a name="user-action"></a>用户操作  

- 不需要用户进行任何操作。  

  有关详细信息，请参阅下列资源：  

- [密码同步](../core/password-synchronization2.md)
