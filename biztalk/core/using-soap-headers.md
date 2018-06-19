---
title: 使用 SOAP 标头 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SOAP headers
- SOAP headers, about SOAP headers
- Web services, SOAP headers
ms.assetid: 816618ff-ecd8-4f12-b9a9-dbe4203411d8
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0671dabe7547d3f55b937a1de58241a35cb70b39
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22287117"
---
# <a name="using-soap-headers"></a>使用 SOAP 标头
Microsoft BizTalk Server 支持已定义的和未知的 SOAP 标头。 已定义的 SOAP 标头是 Web Services 中以 Web 服务描述语言 (WSDL) 显式声明的标头。 未知的 SOAP 标头是 Web Services 中未以 WSDL 显式声明的标头。 有关使用 SOAP 标头的详细信息，请参阅"使用 SOAP 标头"Microsoft.NET Framework 文档中在[http://go.microsoft.com/fwlink/?LinkId=25363](http://go.microsoft.com/fwlink/?LinkId=25363)。  
  
 BizTalk Server 为 Web Services 中的每个已定义的 SOAP 标头创建一个上下文属性。  
  
> [!NOTE]
>  使用的 Web Services 仅支持已定义的 SOAP 标头。你不能在使用 Web Services 时设置未知标头。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [与使用的 Web 服务的 SOAP 标头](../core/soap-headers-with-consumed-web-services.md)  
  
-   [与发布的 Web 服务的 SOAP 标头](../core/soap-headers-with-published-web-services.md)