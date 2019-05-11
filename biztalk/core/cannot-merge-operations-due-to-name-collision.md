---
title: 由于名称冲突无法合并操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 81ddb8b7-6f7e-420c-b7c3-921c0e305326
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a8ab241fe80b63f833c9eb373627d445dc7fd08d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357628"
---
# <a name="cannot-merge-operations-due-to-name-collision"></a>由于名称冲突，无法合并操作
## <a name="details"></a>详细信息  
  
|                 |                                                                                                             |
|-----------------|-------------------------------------------------------------------------------------------------------------|
|  产品名称   |             [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]              |
| 产品版本 |                         [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                          |
|    事件 ID     |                                                      0                                                      |
|  事件源   |                                                      0                                                      |
|    组件    |                                                      0                                                      |
|  符号名称  |                                                      0                                                      |
|  消息正文   | 无法合并操作"{0}"由于名称冲突。 Web Services 中的所有操作都必须具有唯一的名称。 |
  
## <a name="explanation"></a>解释  
 此错误表示端口名称或合并的两个不同端口的操作名称具有相同的名称。  
  
## <a name="user-action"></a>用户操作  
 使用端口配置向导，确保合并的所有端口都具有不同的端口名称和操作。  
  
 有关端口配置的其他信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：  
  
-   [如何运行端口配置向导](../core/how-to-run-the-port-configuration-wizard.md)