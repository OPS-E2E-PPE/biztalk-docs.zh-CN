---
title: "使用 WCF LOB 适配器 SDK 时选择的 URI 方案和寻址格式 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3bb4feee-3d39-43ca-82ac-aba38c13bc69
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9990facf6a23f4abea37ee9ce9758a7333eaca61
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="select-a-uri-scheme-and-addressing-format-when-using-the-wcf-lob-adapter-sdk"></a>使用 WCF LOB 适配器 SDK 时选择的 URI 方案和寻址的格式
统一资源标识符 (URI) 唯一标识资源与 Web 服务类似，或者如果使用的开发适配器[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]，要连接到系统，以及要执行的操作。 本部分提供有关如何构造用于唯一地描述了终结点地址和适配器的操作的 URI 的建议。  
  
## <a name="anatomy-of-a-uri"></a>一个 URI 的剖析  
 一个 URI 由以下三个组件构成：  
  
-   **方案名称**是 URI 字符串的前导部分，而是命名的结构中; 第一个级别示例包括 http、 urn 和 contoso。  
  
-   **层次结构部分**包含通常分层，并可以包含可选机构、 主机名和端口信息的信息。 示例包括 www.microsoft.com 和用户名 =User@microsoft.com:4099。  
  
-   **查询**包含用问号 （？） 标记和通常分组为用连字符分隔的键/值对的可选信息 (&)。 例如，contoso://microsoft.com/functions?name=Find。  
  
-   **片段**用于存储可能需要的适配器的额外标识信息。 片段分隔由一个哈希 （#）;例如，contoso://microsoft.com/functions?name=Find#public。  
  
 你可能不会使用所有的 URI 语法所提供的功能。  
  
## <a name="designing-the-uri"></a>设计 URI  
 作为适配器开发人员，你将需要设计为目标的业务系统的相应 URI。 在设计时你的 URI，很重要，使其唯一且有意义。  
  
 一个唯一的 URI 是指不与现有 Uri 在组织内和跨其他业务领域和 Internet 冲突。 例如，选择方案名称，例如"http"或"afs"可能当前识别或已在广泛使用可能导致连接或操作问题因为可能会将请求路由到不同系统，而不适用于你的适配器。  
  
 URI 设计的另一个重要方面它有意义对进行的开发人员受众使用你的适配器。 例如，如果你正在编写一个适配器，有关医疗声明处理系统，您可以设计包含您公司的名称，处理系统名称和系统版本的目标声明的 URI 方案： northwind.contoso.cps.v1.0://。  
  
## <a name="connecting-to-the-target-system"></a>连接到目标系统  
 连接字符串具有以下语法：  
  
 **\<方案\>: //[userinfo"@"]\<LOB 连接字符串\>**  
  
 例如，你无法连接到 contoso 目录排序系统 （示例业务线应用程序） 使用以下：  
  
 **northwind.contoso.v1.0://\<servername\>？目录 = Contoso 集成的安全性 = True**  
  
 你还可以提供可选的颁发机构信息中包括用户名和密码以及其他重要的凭据的 URI。 但是，这可以存在安全风险。  
  
> [!CAUTION]
>  不要在 URI 中传递用户凭据和其他敏感信息。 此信息可能被截获和未经授权的用户查看。  
  
## <a name="see-also"></a>另请参阅  
 [规划和设计使用 WCF LOB 适配器 SDK 的适配器](../../adapters-and-accelerators/wcf-lob-adapter-sdk/plan-and-design-an-adapter-using-the-wcf-lob-adapter-sdk.md)