---
title: 单一登录：事件 11048 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: abceb5ca-f772-4cc8-8e20-2cda8765575e
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9b21787ab368df4ddf7bad7c9ca93d541cc796c7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400946"
---
# <a name="single-sign-on-event-11048"></a>单一登录：事件 11048
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                                                    |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                             企业单一登录                                                                              |
| 产品版本 |                                                             [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                             |
|    事件 ID     |                                                                                       11048                                                                                        |
|  事件源   |                                                                                       ENTSSO                                                                                       |
|    组件    |                                                                                        不可用                                                                                         |
|  符号名称  |                                                                              SSO_ERROR_SSOCSTX_FAILED                                                                              |
|  消息正文   | 无法创建 SSOCSTX。 若要解决此问题，请重新安装 SSO 或将 SSOCSTX.dll 安装到 COM + 库 application.%r<br /><br /> 其他数据: %1 %r<br /><br /> 错误代码： %2 |
  
## <a name="explanation"></a>解释  
 这可能是由于安装错误所致。  
  
## <a name="user-action"></a>用户操作  
 若要解决此问题，请重新安装 SSO 或将 SSOCSTX.dll 安装到 COM + 库应用程序。