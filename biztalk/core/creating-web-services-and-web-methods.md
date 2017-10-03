---
title: "创建 Web 服务和 Web 方法 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- schemas, publishing
- Web services, schemas
- orchestrations, naming conventions
- Web services, naming conventions
- schemas, Web services
ms.assetid: a7c47000-501c-47b1-bafa-82370585c1db
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 74065489e427ae0612897f1f333e3c8e154a535f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="creating-web-services-and-web-methods"></a>创建 Web 服务和 Web 方法
在将架构发布为 Web Services 时，您可在 BizTalk Web Services 发布向导中控制 Web Services 和 Web 方法的创建。 您可以重命名 Web Services 页上树视图中的 Web Services 说明、Web Services 和 Web 方法。 可以添加和删除 Web Services 和 Web 方法。 该向导使用选定请求架构的根元素名称作为输入参数名称。 Web 方法返回值会返回响应架构。  
  
> [!NOTE]
>  ASP.NET Web 客户端可以通过合并相同类型的 in 参数和 out 参数更改 Web 方法签名。 例如，ASP.NET Web 客户端可能会更改从某一 BizTalk Web 方法**字符串 myService （字符串一部分）**到**void myService （ref 字符串一部分）**。  
  
> [!NOTE]
>  如果你收到定义端口，则为单向，Web 方法的响应类型是**void**和 Web 客户端返回任何信息。 SOAP 适配器和业务流程不会将引发的异常返回到 Web 客户端。  
  
## <a name="web-services-naming-conventions-for-published-orchestrations"></a>已发布业务流程的 Web Services 命名约定  
 BizTalk Web Services 发布向导基于在 Web Services 页中定义的 Web Services 说明生成 Web Services (.asmx) 文件名。 下表显示了 Web Services 文件名的默认值。  
  
|生成的 Web Services|文件名|  
|---------------------------|---------------|  
|BizTalkWebService|Visual Studio Web Services 项目名称|  
|WebService1|Web Services (.asmx) 文件名|  
|WebMethod1|Web 方法名|  
  
 生成的 Web Services 不反映其余节点的名称。  
  
## <a name="see-also"></a>另请参阅  
 [发布架构作为 Web 服务](../core/publishing-schemas-as-a-web-service.md)   
 [如何使用发布向导的 BizTalk Web 服务以将架构作为 Web 服务发布](../core/publish-schemas-as-web-services-with-biztalk-web-services-publishing-wizard.md)