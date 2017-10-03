---
title: "管理 （BizTalk Server 示例） |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SSO, examples
- utilities, SSOMANAGE
- examples, SSO
- SSOMANAGE command line utility
ms.assetid: f738e344-4d81-4557-b399-68b59c413245
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b15a94bf916550d9a2eada9b8f354432b4c154ff
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="manage-biztalk-server-sample"></a>管理 （BizTalk Server 示例）
管理单一登录 (SSO) 示例演示如何构造能用于 ssomanage.exe 命令行实用工具的 .xml 文件以执行以下类型的管理操作：  
  
-   在 SSO 系统级别更新全局信息  
  
-   创建关联应用程序  
  
-   创建用户映射  
  
 有关企业单一登录的概念信息，请参阅[使用 SSO](../core/using-sso.md)。  
  
 有关演示如何以编程方式配置 SSO，，如创建关联应用程序和用户映射的示例，请参阅[HTTPSSO （BizTalk Server 示例）](../core/httpsso-biztalk-server-sample.md)。  
  
## <a name="what-this-sample-does"></a>本示例的用途  
 本示例为上述操作类型中的每一种类型都提供了一对 XSD 和示例 .xml 文件。 示例 .xml 文件中的值是无效的。 必须更改这些值，使其与您的特定需求相适应。  
  
## <a name="where-to-find-this-sample"></a>本示例所在的位置  
 *\<示例路径 >*\SSO\Manage\  
  
 下表显示了本示例中的文件及其用途说明：  
  
|文件|Description|  
|---------------|-----------------|  
|AffiliateApplication.xml、GlobalInfo.xml、UserMapping.xml|示例 .xml 文件，在进行修改之后，可以将它们作为参数传递给命令行实用工具 ssomanage.exe。|  
|AffiliateApplication.xsd、GlobalInfo.xsd、UserMapping.xsd|与 .xml 文件对应的架构文件，全面描述了架构可能包含的元素和属性。 可使用这些文件验证从其他来源收到的对应 .xml 文件。|  
  
## <a name="building-and-initializing-this-sample"></a>生成并初始化此示例  
 由于本示例仅包括 XML 架构定义语言 (XSD) 和 .xml 文件，您可以修改后者并将其传递给命令行实用工具 ssomanage.exe，本示例中无需生成任何内容。  
  
## <a name="running-this-sample"></a>运行本示例  
 本示例包含了示例 .xml 文件，可用于在以下三种不同模式下运行命令行实用工具 ssomanage.exe：  
  
-   **更新全局 SSO 系统级别的信息。** 若要执行此种类型的操作，请执行以下步骤：  
  
    1.  根据您的特定配置的需要，编辑 GlobalInfo.xml 文件。  
  
    2.  使用适当的参数运行命令行实用工具 ssomanage.exe，如下所示：  
  
        ```  
        ssomanage –updatedb GlobalInfo.xml  
        ```  
  
     确保根据您的环境对 GlobalInfo.xml 文件中的值进行了编辑。 例如，SSO 管理员帐户必须是一个有效的 Windows 帐户。 SSO 管理员帐户和 SSO 关联管理员帐户都必须是 Windows 的全局域组帐户。  
  
-   **创建关联应用程序。** 若要执行此种类型的操作，请执行以下步骤：  
  
-   根据您的特定配置的需要，编辑 AffiliateApplication.xml 文件。  
  
    -   运行命令行实用工具 ssomanage.exe 使用适当的参数，如下所示：  
  
        ```  
        ssomanage –createapps AffiliateApplication.xml  
        ```  
  
     可以同时创建多个关联应用程序。  
  
-   **创建用户映射。** 若要执行此种类型的操作，请执行以下步骤：  
  
    1.  根据您的特定配置的需要，编辑 UserMapping.xml 文件。  
  
    2.  运行命令行实用工具 ssomanage.exe 使用适当的参数，如下所示：  
  
        ```  
        ssomanage –createmappings UserMapping.xml  
        ```  
  
     可以同时为一个或多个关联应用程序创建多个映射。  
  
## <a name="comments"></a>注释  
 在修改了本示例提供的示例 .xml 文件之后，特别是在此类更改涉及到在这些文件中添加敏感信息的情况下，请确保这些文件在文件系统中能得到很好的保护。 例如，应确保没有将这些文件误放到某个共享文件夹中。  
  
## <a name="see-also"></a>另请参阅  
 [SSO （BizTalk Server 示例文件夹中）](../core/sso-biztalk-server-samples-folder.md)