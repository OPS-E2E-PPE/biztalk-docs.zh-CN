---
title: 单一登录：事件 11047 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: aa4eb1ae-45a6-4e0c-9af6-6bf1ed63acfb
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 97d70d94ffad94b4a81d09c821469c4adbfbe775
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400959"
---
# <a name="single-sign-on-event-11047"></a>单一登录：事件 11047
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                         |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                企业单一登录                                                                |
| 产品版本 |                                               [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                |
|    事件 ID     |                                                                          11047                                                                          |
|  事件源   |                                                                         ENTSSO                                                                          |
|    组件    |                                                                           不可用                                                                           |
|  符号名称  |                                                                 SSO_ERROR_SSOSQL_FAILED                                                                 |
|  消息正文   | 无法创建 SSOSQL。 若要解决此问题，请重新安装 SSO 或尝试 Visual Studio 命令 prompt.%r regasm SSOSQL.dll<br /><br /> 错误代码： %1 |
  
## <a name="explanation"></a>解释  
 这可能是由于安装错误所致。  
  
## <a name="user-action"></a>用户操作  
 若要解决此问题，请重新安装 SSO 或尝试从 Visual Studio 命令提示符下的 regasm SSOSQL.dll。