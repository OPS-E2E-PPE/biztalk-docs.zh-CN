---
title: 单一登录： 事件 10564 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e523c97a-608e-4bf4-8747-cfa0cce10acf
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8be4ea87757a1fa0cb5d8ebd2e344ce521dbf740
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36997142"
---
# <a name="single-sign-on-event-10564"></a>单一登录： 事件 10564
## <a name="details"></a>详细信息  
  
|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  产品名称   |                 企业单一登录                  |
| 产品版本 | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    事件 ID     |                           10564                            |
|  事件源   |                           ENTSSO                           |
|    组件    |                            N/A                             |
|  符号名称  |           SSO_ERROR_BACKUP_FILE_INCORRECT_FORMAT           |
|  消息正文   |     备份文件格式不正确。      |
  
## <a name="explanation"></a>解释  
 备份文件格式不正确。  
  
## <a name="user-action"></a>用户操作  
 检查您是否具有正确的文件和位置。 还应确认在该文件夹中不存在具有 .BAK 扩展名的其他文件，因为 ENTSSO 系统可能会将这些文件与实际的备份文件相混淆。