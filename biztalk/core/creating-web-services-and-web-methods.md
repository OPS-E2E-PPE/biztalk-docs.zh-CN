---
title: 创建 Web 服务和 Web 方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- schemas, publishing
- Web services, schemas
- orchestrations, naming conventions
- Web services, naming conventions
- schemas, Web services
ms.assetid: a7c47000-501c-47b1-bafa-82370585c1db
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 22d93635ce23f4ce8899f3d9f6d95dfca2010ea7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389858"
---
# <a name="creating-web-services-and-web-methods"></a>创建 Web 服务和 Web 方法
时将架构发布为 Web 服务，可以控制创建的 Web 服务和 BizTalk Web Services 发布向导中的 Web 方法。 您可以重命名 Web 服务说明、 Web 服务和树视图中的 Web 服务页上的 Web 方法。 您可以添加和删除 Web services 和 Web 方法。 该向导使用选定的请求架构的根元素名称作为输入的参数名称。 Web 方法返回值会返回响应架构。  
  
> [!NOTE]
>  ASP.NET Web 客户端可能更改的组合 in 和 out 参数相同类型的 Web 方法签名。 例如，ASP.NET Web 客户端可能会更改 BizTalk Web 方法从**myService （字符串一部分） 的字符串**到**void myService （ref 字符串一部分）**。  
  
> [!NOTE]
>  如果在接收端口已定义为单向，则 Web 方法响应类型为**void**和到 Web 客户端返回任何信息。 SOAP 适配器和业务流程不会返回引发的异常到 Web 客户端。  
  
## <a name="web-services-naming-conventions-for-published-orchestrations"></a>Web services 已发布的业务流程的命名的约定  
 BizTalk Web Services 发布向导生成基于 Web 服务页中定义的 Web 服务说明的 Web 服务 (.asmx) 文件名。 下表显示了 Web 服务文件名称的默认值。  
  
|生成的 Web 服务|File name|  
|---------------------------|---------------|  
|BizTalkWebService|Visual Studio Web 服务项目的名称|  
|WebService1|Web 服务 (.asmx) 文件名|  
|WebMethod1|Web 方法名称|  
  
 生成的 Web 服务不反映其余节点的名称。  
  
## <a name="see-also"></a>请参阅  
 [将架构发布为 Web 服务](../core/publishing-schemas-as-a-web-service.md)   
 [如何使用 BizTalk Web Services 发布向导将架构发布为 Web 服务](../core/publish-schemas-as-web-services-with-biztalk-web-services-publishing-wizard.md)