---
title: 单一登录： 事件 10759 |Microsoft Docs
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
ms.openlocfilehash: 177b5d1383a583ddc33a67a7290bff98b1d13364
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967582"
---
# <a name="single-sign-on-event-10759"></a>单一登录： 事件 10759
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                   |
|-----------------|-------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                             企业单一登录                                             |
| 产品版本 |                            [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                             |
|    事件 ID     |                                                       10759                                                       |
|  事件源   |                                                      ENTSSO                                                       |
|    组件    |                                                        N/A                                                        |
|  符号名称  |                                       ENTSSO_E_BACKUP_RESTORE_FAILED_MEDIA                                        |
|  消息正文   | 指定用于备份或还原主密钥的文件必须位于 NTFS 文件系统或可移动介质上。 |
  
## <a name="explanation"></a>解释  
 只有 NTFS 文件系统或可移动介质能够受到保护。  
  
## <a name="user-action"></a>用户操作  
 切换到 NTFS 文件系统或可移动介质以备份主密钥。