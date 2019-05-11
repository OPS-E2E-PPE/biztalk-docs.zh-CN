---
title: 单一登录：Event 10809 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7331d12b-1000-4a60-83b3-f092968e0e51
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3dc0f1b98ed1b9b3e414888b01f2693a9f1786f4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65293005"
---
# <a name="single-sign-on-event-10809"></a>单一登录：事件 10809
## <a name="details"></a>详细信息  
  
|                 |                                                                   |
|-----------------|-------------------------------------------------------------------|
|  产品名称   |                     企业单一登录                     |
| 产品版本 |    [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]     |
|    事件 ID     |                               10809                               |
|  事件源   |                              ENTSSO                               |
|    组件    |                                不可用                                |
|  符号名称  |                  ENTSSO_E_HISSO_APP_NOT_ENABLED                   |
|  消息正文   | 该应用不支持为主机启动的单一登录。 |
  
## <a name="explanation"></a>解释  
 该应用不支持为主机启动的单一登录。  
  
## <a name="user-action"></a>用户操作  
 使用管理工具来配置主机启动的单一登录。 这会设置  
  
 SSO_FLAG_SSO_EXTERNAL_TO_WINDOWS 标记应用程序。