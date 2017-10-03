---
title: "元数据错误 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ccb60c91-5905-4852-813b-586b82de4825
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4dce5fc9eb944eccbeed57073c2546f81825ec6f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="metadata-errors"></a>元数据错误
用于诊断和解决 WCF 元数据错误的信息。  
  
## <a name="error-consuming-wcf-service-metadata"></a>使用 WCF 服务元数据时出错

||错误详细信息|  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|事件 ID|0|  
|事件源|0|  
|组件|0|  
|符号名称|0|  
|消息正文|使用 WCF 服务元数据时出错|  
  
### <a name="explanation"></a>解释  
 此错误表示元数据，有关该服务不提供或无效。  
  
### <a name="user-action"></a>用户操作  
 如果您拥有要尝试使用的 WCF 服务，则更正服务元数据，然后尝试使用该服务。 转到服务配置编辑器 (**svcConfigEditor.exe**) 以及对配置文件进行更改。  否则，请联系服务提供商

## <a name="failed-to-get-metadata"></a>无法获取元数据

||错误详细信息|  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|事件 ID|0|  
|事件源|0|  
|组件|0|  
|符号名称|0|  
|消息正文|无法从“{0}”获取元数据|  
  
## <a name="explanation"></a>解释  
 此错误表明该服务的元数据不可用。  
  
## <a name="user-action"></a>用户操作  
 启用服务的元数据并再次运行使用向导（如果您具有要尝试使用的 WCF 服务）。 否则，请与服务提供商联系。