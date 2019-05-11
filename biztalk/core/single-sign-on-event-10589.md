---
title: 单一登录：Event 10589 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0fe962bb-e9bb-4107-a5fb-21c180d54e21
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 160635fe7446a2fbac21edad332b4c87cd86e1b0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400170"
---
# <a name="single-sign-on-event-10589"></a>单一登录：事件 10589
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                                                                                                                                   |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                                                                     企业单一登录                                                                                                                     |
| 产品版本 |                                                                                                    [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                     |
|    事件 ID     |                                                                                                                               10589                                                                                                                               |
|  事件源   |                                                                                                                              ENTSSO                                                                                                                               |
|    组件    |                                                                                                                                不可用                                                                                                                                |
|  符号名称  |                                                                                                                 SSO_ERROR_BACKUP_SECRET_REQUIRED                                                                                                                  |
|  消息正文   | 主密钥尚未备份。 如果丢失主密钥存储在 SSO 系统中的所有信息将都永久丢失，并且您的系统可能无法正常工作。 请使用 SSO 管理工具来备份主密钥。 |
  
## <a name="explanation"></a>解释  
 主密钥尚未备份。 如果丢失主密钥存储在 SSO 系统中的所有信息将都永久丢失，并且您的系统可能无法正常工作。  
  
## <a name="user-action"></a>用户操作  
 有关备份主密钥的信息，请参阅[管理主密钥](../core/managing-the-master-secret.md)。