---
title: 项目位置不为空 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: db353050-3662-4ab6-8898-4e4d3bd78ac1
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6fd44cc0d9bfefb67b96558808e6b98a46c8afc2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394090"
---
# <a name="the-project-location-is-not-empty"></a>项目位置不为空
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                                                                                                                    |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                                 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                                                 |
| 产品版本 |                                                                                             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                                                                                             |
|    事件 ID     |                                                                                                                         0                                                                                                                          |
|  事件源   |                                                                                                                         0                                                                                                                          |
|    组件    |                                                                                                                         0                                                                                                                          |
|  符号名称  |                                                                                                                         0                                                                                                                          |
|  消息正文   | 项目位置"{0}"不为空。 需要以下项之一：1. 选择新的项目中，2 的不同位置。 指定覆盖以重用现有位置或 3。 手动删除项目位置的内容。 |
  
## <a name="explanation"></a>解释  
 此错误表示虚拟服务正在尝试发布的目录不为空。  
  
## <a name="user-action"></a>用户操作  
 选择覆盖位置以重复使用相同的位置。 或指定新位置。  在 WCF 服务发布向导中，选择**覆盖现有位置**然后单击**下一步**。 此步骤将覆盖该位置。