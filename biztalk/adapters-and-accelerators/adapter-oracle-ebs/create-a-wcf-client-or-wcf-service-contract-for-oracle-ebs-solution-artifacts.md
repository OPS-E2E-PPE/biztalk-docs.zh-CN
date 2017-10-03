---
title: "生成 WCF 客户端或 Oracle E-business Suite 解决方案项目关联的 WCF 服务协定 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c7ffd857-a177-423a-ae83-685d11b7aec6
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bc7fb7dc0df1c2cbf4c4f8b1118cba07df6c7231
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="generate-a-wcf-client-or-a-wcf-service-contract-for-oracle-e-business-suite-solution-artifacts"></a>生成 WCF 客户端或 Oracle E-business Suite 解决方案项目关联的 WCF 服务协定
你可以使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]生成 WCF 客户端类或 Oracle E-business Suite 项目上的所选操作所针对的 WCF 服务协定 （接口）。 你还可以使用 ServiceModel 元数据实用工具 (svcutil.exe) 生成 WCF 客户端类或 WCF 服务协定;但是，[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]公开通过标准的 Microsoft Windows 界面 ServiceModel 元数据实用工具的功能。 它还提供了使用 svcutil.exe 工具中，未提供的浏览和搜索功能并生成一个基于连接到 Oracle E-business Suite 时选择的绑定属性的配置文件。  
  
## <a name="generating-a-client-class-by-using-the-add-adapter-service-reference-plug-in"></a>通过使用生成的客户端类添加插件的适配器服务引用  
 执行以下步骤以使用生成 WCF 客户端类[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。  
  
#### <a name="to-generate-a-wcf-client-class"></a>若要生成 WCF 客户端类  
  
1.  在[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]解决方案资源管理器，右键单击你的项目，并依次**添加适配器服务引用**。  
  
2.  后**添加适配器服务引用**对话框随即打开，请按照中的步骤[检索用于 Oracle E-business Suite 操作 Visual Studio 中的元数据](../../adapters-and-accelerators/adapter-oracle-ebs/get-metadata-for-oracle-e-business-suite-operations-in-visual-studio.md)以连接到 Oracle E-business Suite 和浏览和搜索操作。 若要创建的操作，你选择一个 WCF 客户端类，请确保**客户端 （出站操作）**从选择**选择协定类型**（这是默认值） 的下拉列表。  
  
3.  选择所有你想要为目标，请单击操作后**确定**生成 WCF 客户端类。  
  
 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]将两个文件添加到你的项目：  
  
-   **OracleEBSBindingClient.cs**。 此文件包含生成的 WCF 客户端类和帮助程序的代码所选的操作。  
  
-   **app.config**。此文件包含的绑定配置和客户端终结点配置。 这些配置基于配置的绑定和连接时所做的选择[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。  
  
    > [!IMPORTANT]
    >  在使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]，如果未指定的字符串类型的绑定属性的值，并且其默认值为 null，然后，绑定属性将不可用的 app.config 文件中。 你必须手动添加绑定属性，并且其值在 app.config 文件中，如果需要。  
  
## <a name="generating-a-wcf-service-contract-by-using-the-add-adapter-service-reference-plug-in"></a>通过使用生成的 WCF 服务协定添加插件的适配器服务引用  
 适配器公开启用 Oracle E-business Suite 将消息发送到适配器客户端的入站的操作。 对于这类操作，则必须生成的 WCF 服务协定。 本部分介绍如何生成公开的适配器的入站操作的服务协定。  
  
 执行以下步骤以使用生成的 WCF 服务协定[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。  
  
#### <a name="to-generate-a-wcf-service-contract-for-inbound-operations"></a>若要生成 WCF 服务协定的入站操作  
  
1.  在[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]解决方案资源管理器，右键单击你的项目，并依次**添加适配器服务引用**。  
  
2.  后**添加适配器服务引用**对话框随即打开，请按照中的步骤[检索用于 Oracle E-business Suite 操作 Visual Studio 中的元数据](../../adapters-and-accelerators/adapter-oracle-ebs/get-metadata-for-oracle-e-business-suite-operations-in-visual-studio.md)以连接到 Oracle E-business Suite。 有几个绑定属性和一个 URI 属性，你可能想要设置连接到 Oracle E-business Suite 时。  
  
3.  你已连接到 Oracle E-business Suite 后，选择**服务 （入站操作）**从**选择协定类型**下拉列表。  
  
4.  在**选择类别**框中，浏览到你想要生成服务协定的入站操作。 例如，对于**通知**操作，单击根节点 (**/**)，选择**通知**从**可用类别和操作**框中，并依次**添加**。 有关如何浏览入站操作的说明，请参阅[浏览、 搜索和检索用于 Oracle E-business Suite 操作的元数据](../../adapters-and-accelerators/adapter-oracle-ebs/browse-search-and-get-metadata-for-oracle-e-business-suite-operations.md)。  
  
5.  若要生成操作的 WCF 服务协定，请单击**确定**。  
  
 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]将三个文件添加到你的项目：  
  
-   **OracleEBSBindingInterface.cs**。 此文件包含生成的 WCF 服务协定 （接口） 和入站操作的帮助器代码。  
  
-   **OracleEBSBindingService.cs**。 此文件包含实现 OracleDBBindingInterface.cs 中定义的接口的类。 你可以实现业务逻辑处理入站操作返回的记录。  
  
-   **app.config**。此文件包含的绑定配置、 终结点行为和基于你所做的选择时配置的绑定和连接的服务终结点配置[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。  
  
    > [!IMPORTANT]
    >  在使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]，如果未指定的字符串类型的绑定属性的值，并且其默认值为 null，然后，绑定属性将不可用的 app.config 文件中。 你必须手动添加绑定属性，并且其值在 app.config 文件中，如果需要。  
  
## <a name="using-svcutilexe-to-generate-a-wcf-client-class-or-a-wcf-service-contract"></a>使用 svcutil.exe 生成 WCF 客户端类或 WCF 服务协定  
 要为你的应用程序生成 WCF 客户端类或 WCF 服务接口，可以使用 svcutil.exe。 你必须配置 svcutil.exe 以将它与[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。  
  
 Svcutil.exe 生成输出文件中的 WCF 客户端类或 WCF 服务协定。 默认文件名称为 output.cs。 你必须手动将此文件加入你[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]项目。 Svcutil.exe 有关的详细信息，请参阅[http://go.microsoft.com/fwlink/?LinkId=139432](http://go.microsoft.com/fwlink/?LinkId=139432)。