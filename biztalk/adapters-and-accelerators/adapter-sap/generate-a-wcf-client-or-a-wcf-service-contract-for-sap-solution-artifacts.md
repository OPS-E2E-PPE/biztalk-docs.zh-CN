---
title: 生成 WCF 客户端或 WCF 服务约定的 SAP 解决方案项目 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ff01e2b0-6480-427a-bc6d-6169e7d6e256
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d84258ab9c1d2716f74e5bab2b4f82fd7caf11e3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65373414"
---
# <a name="generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts"></a>生成 WCF 客户端或 WCF 服务约定的 SAP 解决方案项目
可以使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]生成 WCF 客户端类或针对 SAP 项目上的所选操作的 WCF 服务协定 （接口）。 您还可以使用 ServiceModel Metadata Utility Tool (svcutil.exe) 来生成 WCF 客户端类或 WCF 服务协定;但是，[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]公开 ServiceModel Metadata Utility Tool 通过标准的 Microsoft Windows 界面的功能。 它还提供浏览和搜索功能，使用 svcutil.exe 工具中，未提供，并生成一个基于连接到 SAP 系统时选择的绑定属性的配置文件。  
  
## <a name="generating-a-client-class-by-using-the-add-adapter-service-reference-plug-in"></a>使用生成的客户端类添加适配器服务引用插件  
 执行以下步骤以使用生成 WCF 客户端类[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。  
  
#### <a name="to-generate-a-wcf-client-class"></a>若要生成 WCF 客户端类  
  
1. 在中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]解决方案资源管理器，右键单击项目，然后依次**添加适配器服务引用**。  
  
2. 之后**添加适配器服务引用**对话框打开，请按照中的步骤[获取有关在 Visual Studio 中的 SAP 操作的元数据](../../adapters-and-accelerators/adapter-sap/get-metadata-for-sap-operations-in-visual-studio.md)连接到 SAP 系统和浏览和搜索操作。 若要创建你选择的操作的 WCF 客户端类，务必**客户端 （出站操作）** 从所选**选择协定类型**下拉列表 （这是默认值）。  
  
3. 选择所有你想要为目标，请单击操作后**确定**生成 WCF 客户端类。  
  
   [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]将两个文件添加到你的项目：  
  
- **SAPBindingClient.cs**. 此文件包含生成的 WCF 客户端类和帮助程序的代码所选的操作。  
  
- **App.config**。此文件包含的绑定配置和客户端终结点配置。 设置基于配置的绑定和连接时所做的选择[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。  
  
  > [!IMPORTANT]
  >  同时使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]，如果未指定字符串类型的绑定属性的值，并且其默认值为 null，然后，绑定属性将不可用的 app.config 文件中。 您必须手动添加的绑定属性和其值在 app.config 文件中，如果所需。  
  
## <a name="generating-a-wcf-service-contract-by-using-the-add-adapter-service-reference-plug-in"></a>使用生成的 WCF 服务协定添加适配器服务引用插件  
 当你使用[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]若要从 SAP 系统接收 Idoc 和 Rfc，Trfc，你的代码充当服务到适配器。 即适配器接收来自 SAP 系统的相应项目，并调用代码将传送到你的应用程序的项目 （入站） 操作。  
  
 因此，必须实现 WCF 服务可以从适配器接收此入站的操作。 若要执行此操作，应使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]来生成表示为适配器提供的操作的服务约定的.NET 接口。 此.NET 接口也被称为 WCF 服务约定。 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]还会生成一个类，包含 WCF 服务的存根的实现。 然后实现此接口可创建可用于接收操作的 WCF 服务。  
  
 执行以下步骤以使用生成的 WCF 服务协定[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。  
  
#### <a name="to-generate-a-wcf-service-contract"></a>若要生成的 WCF 服务协定  
  
1. 在中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]解决方案资源管理器，右键单击项目，然后依次**添加适配器服务引用**。  
  
2. 之后**添加适配器服务引用**对话框打开，请按照中的步骤[获取有关在 Visual Studio 中的 SAP 操作的元数据](../../adapters-and-accelerators/adapter-sap/get-metadata-for-sap-operations-in-visual-studio.md)连接到 SAP 系统和浏览和搜索操作。 若要创建你选择的操作的 WCF 服务约定，务必**服务 （入站操作）** 从所选**选择协定类型**下拉列表。  
  
3. 选择所有你想要为目标，请单击操作后**确定**来生成 WCF 服务协定。  
  
   [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]将三个文件添加到你的项目：  
  
- **SAPBindingInterface.cs**。 此文件包含生成的 WCF 服务协定 （接口），并为所选的操作的帮助器代码。  
  
- **SAPBindingService.cs**. 此文件包含存根的 WCF 服务类实现 SAPBindingInterface.cs 中定义的接口。 您可以实现直接在此类方法中处理 RFC、 tRFC 或 IDOC 的业务逻辑。  
  
- **App.config**。此文件包含的绑定配置、 终结点行为，以及基于配置的绑定和连接时所做的选择的服务终结点配置[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。  
  
  > [!IMPORTANT]
  >  同时使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]，如果未指定字符串类型的绑定属性的值，并且其默认值为 null，然后，绑定属性将不可用的 app.config 文件中。 您必须手动添加的绑定属性和其值在 app.config 文件中，如果所需。  
  
> [!NOTE]
>  无需配置的连接 URI 时，指定 RFC 服务器参数为[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]来生成 WCF 服务协定。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]从客户端连接到 SAP 系统中检索元数据。  
  
## <a name="generate-a-wcf-client-class-or-a-wcf-service-contract-by-using-svcutilexe"></a>使用 svcutil.exe 生成 WCF 客户端类或 WCF 服务约定  
 可以使用 svcutil.exe 为你的应用程序生成 WCF 客户端类或 WCF 服务约定。 必须配置 svcutil.exe 与其一起使用[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。 有关详细信息，有关配置和使用与 svcutil.exe [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]，请参阅[用于 mySAP Business Suite 的 BizTalk 适配器使用 ServiceModel Metadata Utility Tool](../../adapters-and-accelerators/adapter-sap/use-the-servicemodel-metadata-utility-with-the-sap-adapter-in-biztalk.md)。  
  
 Svcutil.exe 生成输出文件中的 WCF 客户端类或 WCF 服务协定。 默认文件名称为 output.cs。 您必须手动将此文件加入你[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]项目。  
  
## <a name="see-also"></a>请参阅  
[开发 SAP 应用程序使用 WCF 通道模型](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-channel-model.md)