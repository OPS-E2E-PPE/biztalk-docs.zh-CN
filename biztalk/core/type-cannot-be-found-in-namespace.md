---
title: 命名空间中找不到类型 |Microsoft 文档
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
ms.openlocfilehash: 515dd9b6b73b43bee22ffc7b67745bb45adcaf6c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22286453"
---
# <a name="type-cannot-be-found-in-namespace"></a>命名空间中找不到类型
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|事件 ID|0|  
|事件源|0|  
|组件|0|  
|符号名称|0|  
|消息正文|错误： 无法在命名空间"{1}"中找到类型"{0}"|  
  
## <a name="explanation"></a>解释  
 此错误表示所创建的项目参考的是无法在指定的命名空间中找到的类型。  
  
## <a name="user-action"></a>用户操作  
 添加包含无法找到的类型的引用，然后再次运行向导（如果您拥有要尝试使用的 WCF 服务）。 否则，请与服务提供商联系。