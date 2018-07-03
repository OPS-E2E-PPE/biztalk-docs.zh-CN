---
title: 单一登录： 事件 10561 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 770e6fc1-0854-4555-8f2a-5f199e3aaca7
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 053b17fcb940383d58110378710aeb6bc8d3fbe6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992488"
---
# <a name="single-sign-on-event-10561"></a>单一登录： 事件 10561
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                                                                                                 |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                                                    企业单一登录                                                                                                    |
| 产品版本 |                                                                                   [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                    |
|    事件 ID     |                                                                                                              10561                                                                                                              |
|  事件源   |                                                                                                             ENTSSO                                                                                                              |
|    组件    |                                                                                                               N/A                                                                                                               |
|  符号名称  |                                                                                                  SSO_ERROR_BACKUP_FAILED_MEDIA                                                                                                  |
|  消息正文   | 为主密钥备份指定的文件必须位于 NTFS 文件系统或可移动媒体上。%r<br /><br /> 文件名称: %1 %r<br /><br /> 客户端用户: %2 %r<br /><br /> 客户端计算机: %3 %r<br /><br /> 错误代码： %4 |
  
## <a name="explanation"></a>解释  
 尝试备份所使用的媒体（如 FAT 文件）无效。 为主密钥备份指定的文件必须位于 NTFS 文件系统或可移动媒体上。  
  
## <a name="user-action"></a>用户操作  
 检查媒体的格式，确保其为 NTFS 格式或可移动媒体。