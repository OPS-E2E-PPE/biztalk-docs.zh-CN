---
title: 单一登录：Event 10759 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5347f3d6-d31a-4c00-a64c-c0b0f680de88
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 966cc847d442e61353ea862e908b12d7d4b4f3d1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65307473"
---
# <a name="single-sign-on-event-10759"></a>单一登录：事件 10759
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                   |
|-----------------|-------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                             企业单一登录                                             |
| 产品版本 |                            [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                             |
|    事件 ID     |                                                       10759                                                       |
|  事件源   |                                                      ENTSSO                                                       |
|    组件    |                                                        不可用                                                        |
|  符号名称  |                                       ENTSSO_E_BACKUP_RESTORE_FAILED_MEDIA                                        |
|  消息正文   | 指定为备份或还原主密钥的文件必须位于 NTFS 文件系统或可移动媒体。 |
  
## <a name="explanation"></a>解释  
 仅 NTFS 文件系统或可移动媒体可以得到保护。  
  
## <a name="user-action"></a>用户操作  
 切换到 NTFS 文件系统或可移动介质以备份主密钥。