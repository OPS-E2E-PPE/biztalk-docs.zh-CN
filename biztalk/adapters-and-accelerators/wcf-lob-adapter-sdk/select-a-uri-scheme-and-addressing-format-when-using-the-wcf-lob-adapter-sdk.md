---
title: 使用 WCF LOB 适配器 SDK 时选择的 URI 方案和寻址的格式 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3bb4feee-3d39-43ca-82ac-aba38c13bc69
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b8a9e9ffd78e0740dd366f4f09d3a832e74cda94
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005766"
---
# <a name="select-a-uri-scheme-and-addressing-format-when-using-the-wcf-lob-adapter-sdk"></a>使用 WCF LOB 适配器 SDK 时选择的 URI 方案和寻址的格式
统一资源标识符 (URI) 唯一标识资源类似于 Web 服务，或在开发适配器的情况下[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]，若要连接到的系统，以及要执行的操作。 本部分提供有关如何构造一个 URI 来唯一地描述终结点地址和您的适配器的操作的建议。  
  
## <a name="anatomy-of-a-uri"></a>一个 URI 的剖析  
 URI 由以下三个组件组成：  
  
- **方案名称**是潜在客户部分的 URI 字符串，而是第一个级别的命名结构; 示例包括 http、 urn 和 contoso。  
  
- **层次结构部分**包含，通常具有层次结构可以包含可选的颁发机构、 主机名和端口信息的信息。 示例包括 www.microsoft.com 和 UserName =User@microsoft.com:4099。  
  
- **查询**包含可选信息用问号 （？） 标记，并且通常分组为键/值对分隔与号 (&)。 例如，contoso://microsoft.com/functions?name=Find。  
  
- **片段**用来存储可能需要的适配器的额外标识信息。 片段分隔哈希 (）;例如，contoso://microsoft.com/functions?name=Find#public。  
  
  您可能不会使用所有的 URI 语法所提供的功能。  
  
## <a name="designing-the-uri"></a>设计 URI  
 作为适配器开发人员，您需要设计您的目标业务线系统的相应 URI。 在设计你的 URI 时，务必使其唯一且有意义。  
  
 一个唯一的 URI 是指不与现有组织内以及跨其他业务领域的 Uri 和 Internet 冲突。 例如，选择一个方案名称，如"http"或"afs"可能当前识别或已在广泛的使用可能会导致连接或操作问题由于可能会将请求路由到不同的系统，而不适用于您的适配器。  
  
 URI 设计的另一个重要方面，使有意义向开发人员受众将使用您的适配器。 例如，如果你正在编写一个适配器的医疗索赔处理系统，您可以设计包含公司名称、 处理系统名称和系统版本的目标声明的 URI 方案： northwind.contoso.cps.v1.0://。  
  
## <a name="connecting-to-the-target-system"></a>连接到目标系统  
 连接字符串有以下语法：  
  
 **\<方案\>: //[userinfo"\@"]\<LOB 连接字符串\>**  
  
 例如，你可以连接到 contoso 目录订购系统 （业务线应用程序的示例行） 使用以下：  
  
 **northwind.contoso.v1.0://\<servername\>？目录 Contoso 和集成的安全性 = = True**  
  
 您还可以提供可选的颁发机构信息中包括用户名和密码以及其他重要的凭据的 URI。 但是，这可能会造成安全风险。  
  
> [!CAUTION]
>  不要在 URI 中传递用户凭据和其他敏感信息。 可以截获和未经授权的用户查看此信息。  
  
## <a name="see-also"></a>请参阅  
 [规划和设计适配器使用 WCF LOB 适配器 SDK](../../adapters-and-accelerators/wcf-lob-adapter-sdk/plan-and-design-an-adapter-using-the-wcf-lob-adapter-sdk.md)