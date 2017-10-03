---
title: "无效的服务证书指纹 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 22e7d74e-40ec-4187-9246-bc8da2a9ce86
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a465d631e72bc27c6b24274deb31e396037aa182
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="invalid-service-certificate-thumbprint"></a>服务证书指纹无效
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|事件 ID|0|  
|事件源|0|  
|组件|0|  
|符号名称|0|  
|消息正文|服务证书指纹无效；应为十六进制的 40 位数字|  
  
## <a name="explanation"></a>解释  
 指定的服务证书指纹无效。  
  
## <a name="user-action"></a>用户操作  
 在用于配置 WCF 端口的代码中，用户界面的服务证书属性应为十六进制的 40 位数字值。 示例： 798A68E7A3E6F2CCC6929FC4AF2A15A9EED66E39  
  
 有关证书的其他信息，请参阅以下资源：  
  
-   [将证书安装适用于这些 WCF 适配器](../core/installing-certificates-for-the-wcf-adapters.md)