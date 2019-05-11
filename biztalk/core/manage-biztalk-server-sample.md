---
title: 管理 （BizTalk Server 示例） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SSO, examples
- utilities, SSOMANAGE
- examples, SSO
- SSOMANAGE command line utility
ms.assetid: f738e344-4d81-4557-b399-68b59c413245
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 32fb8d27057f1fca3b75f20aab715649fb95b8cb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65329069"
---
# <a name="manage-biztalk-server-sample"></a>管理 （BizTalk Server 示例）
管理单一登录 (SSO) 示例演示了如何构造.xml 文件，它们可以使用 ssomanage.exe 命令行实用程序来执行以下类型的管理操作：  
  
- 在 SSO 系统级别更新全局信息  
  
- 创建关联应用程序  
  
- 创建用户映射  
  
  有关企业单一登录的概念信息，请参阅[使用 SSO](../core/using-sso.md)。  
  
  有关演示如何以编程方式配置 SSO，例如创建关联应用程序和用户映射的示例，请参阅[HTTPSSO （BizTalk Server 示例）](../core/httpsso-biztalk-server-sample.md)。  
  
## <a name="what-this-sample-does"></a>本示例的用途  
 此示例包含一对 XSD 和示例.xml 文件，为每个这些类型的操作。 示例.xml 文件中的值不是有效的。 您必须对适用于你的特定要求的值进行更改。  
  
## <a name="where-to-find-this-sample"></a>本示例所在的位置  
 *\<示例路径\>* \SSO\Manage\  
  
 下表显示了本示例中的文件及其用途说明：  
  
|文件|Description|  
|---------------|-----------------|  
|AffiliateApplication.xml、 GlobalInfo.xml、 UserMapping.xml|示例.xml 文件，你可以修改后，作为参数传递给命令行实用工具 ssomanage.exe。|  
|AffiliateApplication.xsd、 GlobalInfo.xsd、 UserMapping.xsd|提供对其使用的元素和属性的完整说明相应的.xml 文件的架构文件。 这些文件可用于验证从其他来源收到的对应.xml 文件。|  
  
## <a name="building-and-initializing-this-sample"></a>生成并初始化此示例  
 本示例包含仅 XML 架构定义语言 (XSD) 和.xml 文件，后者的其中您可以修改，然后将其传递给命令行实用工具 ssomanage.exe，因为没有要在此示例中生成。  
  
## <a name="running-this-sample"></a>运行本示例  
 此示例包括用于在以下三种不同模式下运行命令行实用工具 ssomanage.exe 示例.xml 文件：  
  
- **更新在 SSO 系统级别的全局信息。** 若要执行此类操作，请执行以下步骤：  
  
  1. 编辑 GlobalInfo.xml 文件所需的特定配置。  
  
  2. 使用适当的参数，运行 ssomanage.exe 命令行实用程序，如下所示：  
  
     ```  
     ssomanage –updatedb GlobalInfo.xml  
     ```  
  
     请确保编辑文件 GlobalInfo.xml 以匹配你的环境中的值。 例如，SSO 管理员帐户必须是有效的 Windows 帐户。 SSO 管理员帐户和 SSO 关联管理员帐户必须是 Windows 的全局域组帐户。  
  
- **创建关联应用程序。** 若要执行此类操作，请执行以下步骤：  
  
- 编辑 AffiliateApplication.xml 文件所需的特定配置。  
  
  - 使用适当的参数，运行命令行实用工具 ssomanage.exe，如下所示：  
  
    ```  
    ssomanage –createapps AffiliateApplication.xml  
    ```  
  
    可以在同一时间创建多个关联应用程序。  
  
- **创建用户映射。** 若要执行此类操作，请执行以下步骤：  
  
  1. 编辑 Usermapping.xml 所需的特定配置文件。  
  
  2. 使用适当的参数，运行命令行实用工具 ssomanage.exe，如下所示：  
  
     ```  
     ssomanage –createmappings UserMapping.xml  
     ```  
  
     可以创建多个映射一个或多个关联应用程序在同一时间。  
  
## <a name="comments"></a>注释  
 提供与此示例中，尤其是，此类更改涉及的文件中包括敏感信息的示例.xml 文件进行更改后请确保这些文件受到良好保护文件系统中。 例如，确保它们不会无意中放共享的文件夹中。  
  
## <a name="see-also"></a>请参阅  
 [SSO（BizTalk Server 示例文件夹）](../core/sso-biztalk-server-samples-folder.md)