---
title: 命名空间中找不到类型 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 66387fa6-3ba3-499f-99d6-bb0033c68adc
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 70011a83e5264344a5ef4f30c4525529aa403dce
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393775"
---
# <a name="type-cannot-be-found-in-namespace"></a>命名空间中找不到类型
## <a name="details"></a>详细信息  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  产品名称   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| 产品版本 |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    事件 ID     |                                         0                                          |
|  事件源   |                                         0                                          |
|    组件    |                                         0                                          |
|  符号名称  |                                         0                                          |
|  消息正文   |                错误：类型"{0}"不能在命名空间中找到"{1}"                |
  
## <a name="explanation"></a>解释  
 此错误表示创建的项目所引用类型不能在指定的命名空间中找到。  
  
## <a name="user-action"></a>用户操作  
 添加包含未找到，则类型的引用，并再次运行该向导 （如果您拥有要尝试使用的 WCF 服务）。 否则，请与服务提供商联系。