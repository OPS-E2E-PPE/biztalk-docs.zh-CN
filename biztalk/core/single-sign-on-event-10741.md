---
title: 单一登录：事件 10741 |Microsoft Docs
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
ms.openlocfilehash: 2150f33b90137d5f5e1258a829901426a45d7856
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65291737"
---
# <a name="single-sign-on-event-10741"></a>单一登录：事件 10741
## <a name="details"></a>详细信息  

|                 |                                                                                           |
|-----------------|-------------------------------------------------------------------------------------------|
|  产品名称   |                                 企业单一登录                                 |
| 产品版本 |                [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                 |
|    事件 ID     |                                           10741                                           |
|  事件源   |                                          ENTSSO                                           |
|    组件    |                                            N\A                                            |
|  符号名称  |                                SSO_WARN_SAVING_REPLAY_FILE                                |
|  消息正文   | 正在保存重播或进度 file.%r<br /><br /> 保存的文件: %1 %r<br /><br /> 错误代码： %2 |

## <a name="explanation"></a>解释  
 此警告事件表明 SSO 正在保存重播或进度文件。  

 ENTSSO 服务器无法与 SSO 数据库取得联系时，密码同步使用重播文件。 进度文件指示，距离通过 SSO 无法重播文件中用例联系人与 SSO 数据库会再次读取。  

## <a name="user-action"></a>用户操作  

- 不不需要任何用户操作。  

  有关详细信息，请参阅下列资源：  

- [密码同步](../core/password-synchronization2.md)
