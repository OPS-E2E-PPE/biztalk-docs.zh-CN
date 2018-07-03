---
title: 生成 WCF 客户端或 WCF 服务协定为 Oracle E-business Suite 解决方案项目 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c7ffd857-a177-423a-ae83-685d11b7aec6
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9824e99014431c452f49d4a80e45efe4852c519f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36986894"
---
# <a name="generate-a-wcf-client-or-a-wcf-service-contract-for-oracle-e-business-suite-solution-artifacts"></a>生成 WCF 客户端或 WCF 服务协定为 Oracle E-business Suite 解决方案项目
可以使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]生成 WCF 客户端类或针对 Oracle E-business Suite 项目上的所选操作的 WCF 服务协定 （接口）。 您还可以使用 ServiceModel Metadata Utility Tool (svcutil.exe) 来生成 WCF 客户端类或 WCF 服务协定;但是，[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]公开 ServiceModel Metadata Utility Tool 通过标准的 Microsoft Windows 界面的功能。 它还提供浏览和搜索功能所不具备使用 svcutil.exe 工具中，并生成基于连接到 Oracle E-business Suite 时选择的绑定属性的配置文件。  
  
## <a name="generating-a-client-class-by-using-the-add-adapter-service-reference-plug-in"></a>使用生成的客户端类添加适配器服务引用插件  
 执行以下步骤以使用生成 WCF 客户端类[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。  
  
#### <a name="to-generate-a-wcf-client-class"></a>若要生成 WCF 客户端类  
  
1. 在中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]解决方案资源管理器，右键单击项目，然后依次**添加适配器服务引用**。  
  
2. 之后**添加适配器服务引用**对话框打开，请按照中的步骤[检索用于 Oracle E-business Suite 操作在 Visual Studio 中的元数据](../../adapters-and-accelerators/adapter-oracle-ebs/get-metadata-for-oracle-e-business-suite-operations-in-visual-studio.md)以连接到 Oracle E-business Suite 和浏览和搜索操作。 若要创建你选择的操作的 WCF 客户端类，务必**客户端 （出站操作）** 从所选**选择协定类型**下拉列表 （这是默认值）。  
  
3. 选择所有你想要为目标，请单击操作后**确定**生成 WCF 客户端类。  
  
   [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]将两个文件添加到你的项目：  
  
- **OracleEBSBindingClient.cs**。 此文件包含生成的 WCF 客户端类和帮助程序的代码所选的操作。  
  
- **App.config**。此文件包含的绑定配置和客户端终结点配置。 这些配置根据配置的绑定和连接时所做的选择[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。  
  
  > [!IMPORTANT]
  >  同时使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]，如果未指定字符串类型的绑定属性的值，并且其默认值为 null，然后，绑定属性将不可用的 app.config 文件中。 您必须手动添加的绑定属性和其值在 app.config 文件中，如果所需。  
  
## <a name="generating-a-wcf-service-contract-by-using-the-add-adapter-service-reference-plug-in"></a>使用生成的 WCF 服务协定添加适配器服务引用插件  
 该适配器公开启用 Oracle E-business Suite 将消息发送到适配器客户端的入站的操作。 对于此类操作，则必须生成的 WCF 服务协定。 本部分提供有关如何生成服务协定公开的适配器的入站操作的信息。  
  
 执行以下步骤以使用生成的 WCF 服务协定[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。  
  
#### <a name="to-generate-a-wcf-service-contract-for-inbound-operations"></a>若要生成 WCF 服务协定的入站操作  
  
1. 在中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]解决方案资源管理器，右键单击项目，然后依次**添加适配器服务引用**。  
  
2. 之后**添加适配器服务引用**对话框打开，请按照中的步骤[检索用于 Oracle E-business Suite 操作在 Visual Studio 中的元数据](../../adapters-and-accelerators/adapter-oracle-ebs/get-metadata-for-oracle-e-business-suite-operations-in-visual-studio.md)以连接到 Oracle E-business Suite。 有多个绑定属性，你可能想要连接到 Oracle E-business Suite 时，设置一个 URI 属性。  
  
3. 已连接到 Oracle E-business Suite 后，选择**服务 （入站操作）** 从**选择协定类型**下拉列表。  
  
4. 在中**选择一个类别**框中，浏览到你想要生成服务协定的入站操作。 例如，对于**通知**操作中，单击根节点 (**/**)，选择**通知**从**可用类别和operations**框中，然后依次**添加**。 有关如何浏览的入站操作的说明，请参阅[浏览、 搜索和检索用于 Oracle E-business Suite 操作的元数据](../../adapters-and-accelerators/adapter-oracle-ebs/browse-search-and-get-metadata-for-oracle-e-business-suite-operations.md)。  
  
5. 若要生成操作的 WCF 服务协定，请单击**确定**。  
  
   [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]将三个文件添加到你的项目：  
  
- **OracleEBSBindingInterface.cs**。 此文件包含生成的 WCF 服务协定 （接口） 和入站操作的帮助器代码。  
  
- **OracleEBSBindingService.cs**。 此文件包含实现 OracleDBBindingInterface.cs 中定义的接口的类。 可实现业务逻辑处理入站操作返回的记录。  
  
- **App.config**。此文件包含的绑定配置、 终结点行为，以及基于配置的绑定和连接时所做的选择的服务终结点配置[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。  
  
  > [!IMPORTANT]
  >  同时使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]，如果未指定字符串类型的绑定属性的值，并且其默认值为 null，然后，绑定属性将不可用的 app.config 文件中。 您必须手动添加的绑定属性和其值在 app.config 文件中，如果所需。  
  
## <a name="using-svcutilexe-to-generate-a-wcf-client-class-or-a-wcf-service-contract"></a>使用 svcutil.exe 生成 WCF 客户端类或 WCF 服务约定  
 可以使用 svcutil.exe 为你的应用程序生成 WCF 客户端类或 WCF 服务接口。 必须配置 svcutil.exe 与其一起使用[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。  
  
 Svcutil.exe 生成输出文件中的 WCF 客户端类或 WCF 服务协定。 默认文件名称为 output.cs。 您必须手动将此文件加入你[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]项目。 有关 svcutil.exe 的详细信息，请参阅[ http://go.microsoft.com/fwlink/?LinkId=139432 ](http://go.microsoft.com/fwlink/?LinkId=139432)。