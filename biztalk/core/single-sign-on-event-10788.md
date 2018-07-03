---
title: 单一登录： 事件 10788 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: deeb8859-6b2e-452d-a7e5-0cb10de68bd2
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b1bf8d17abd7fd5652821b998cae34915e7777f2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37019657"
---
# <a name="single-sign-on-event-10788"></a>单一登录： 事件 10788
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                          |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                        企业单一登录                                                         |
| 产品版本 |                                        [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                        |
|    事件 ID     |                                                                  10788                                                                   |
|  事件源   |                                                                  ENTSSO                                                                  |
|    组件    |                                                                   N/A                                                                    |
|  符号名称  |                                                       ENTSSO_E_DTC_IMPORT_FAILED1                                                        |
|  消息正文   | 无法导入 DTC 事务。 请检查是否正确配置 MSDTC 以用于远程操作。 有关详细信息，请参阅文档。 |
  
## <a name="explanation"></a>解释  
 无法导入 DTC 事务。  
  
## <a name="user-action"></a>用户操作  
 请检查是否正确配置 MSDTC 以用于远程操作；有关详细信息，请参阅指定计算机上的事件日志。  
  
 有关 MSDTC 问题的帮助，请参阅[MSDTC 疑难解答](../core/troubleshooting-problems-with-msdtc.md)。