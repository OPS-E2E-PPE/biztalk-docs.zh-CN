---
title: "生成 WCF 客户端或 SAP 解决方案项目关联的 WCF 服务协定 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ff01e2b0-6480-427a-bc6d-6169e7d6e256
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 035f1263922a0c455662139ca112794e920e3848
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts"></a>生成 WCF 客户端或 SAP 解决方案项目关联的 WCF 服务协定
你可以使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]生成 WCF 客户端类或所选操作上的 SAP 项目所面向的 WCF 服务协定 （接口）。 你还可以使用 ServiceModel 元数据实用工具 (svcutil.exe) 生成 WCF 客户端类或 WCF 服务协定;但是，[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]公开通过标准的 Microsoft Windows 界面 ServiceModel 元数据实用工具的功能。 它还提供浏览和搜索功能，使用 svcutil.exe 工具中，未提供，并生成一个基于连接到 SAP 系统时选择的绑定属性的配置文件。  
  
## <a name="generating-a-client-class-by-using-the-add-adapter-service-reference-plug-in"></a>通过使用生成的客户端类添加插件的适配器服务引用  
 执行以下步骤以使用生成 WCF 客户端类[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。  
  
#### <a name="to-generate-a-wcf-client-class"></a>若要生成 WCF 客户端类  
  
1.  在[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]解决方案资源管理器，右键单击你的项目，并依次**添加适配器服务引用**。  
  
2.  后**添加适配器服务引用**对话框随即打开，请按照中的步骤[获取 Visual Studio 中的 SAP 操作的元数据](../../adapters-and-accelerators/adapter-sap/get-metadata-for-sap-operations-in-visual-studio.md)连接到 SAP 系统和浏览和搜索操作。 若要创建的操作，你选择一个 WCF 客户端类，请确保**客户端 （出站操作）**从选择**选择协定类型**（这是默认值） 的下拉列表。  
  
3.  选择所有你想要为目标，请单击操作后**确定**生成 WCF 客户端类。  
  
 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]将两个文件添加到你的项目：  
  
-   **SAPBindingClient.cs**。 此文件包含生成的 WCF 客户端类和帮助程序的代码所选的操作。  
  
-   **App.config**。此文件包含的绑定配置和客户端终结点配置。 设置基于配置的绑定和连接时所做的选择[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。  
  
    > [!IMPORTANT]
    >  在使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]，如果未指定的字符串类型的绑定属性的值，并且其默认值为 null，然后，绑定属性将不可用的 app.config 文件中。 你必须手动添加绑定属性，并且其值在 app.config 文件中，如果需要。  
  
## <a name="generating-a-wcf-service-contract-by-using-the-add-adapter-service-reference-plug-in"></a>通过使用生成的 WCF 服务协定添加插件的适配器服务引用  
 当你使用[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]若要接收到的 Idoc、 Rfc 和 tRFCs 从 SAP 系统，你的代码充当到适配器服务。 即适配器收到来自 SAP 系统的相应项目，并调用你的代码以将项目传递到你的应用程序执行 （入站） 的操作。  
  
 因此，必须实现的 WCF 服务，可以从适配器接收此入站的操作。 若要执行此操作，请使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]生成表示该操作的适配器显示的服务协定的.NET 接口。 此.NET 接口也被称为 WCF 服务协定。 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]还会生成一个包含 WCF 服务的存根的实现类。 然后，则实现此接口可创建可用于接收操作的 WCF 服务。  
  
 执行以下步骤以使用生成的 WCF 服务协定[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。  
  
#### <a name="to-generate-a-wcf-service-contract"></a>若要生成的 WCF 服务协定  
  
1.  在[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]解决方案资源管理器，右键单击你的项目，并依次**添加适配器服务引用**。  
  
2.  后**添加适配器服务引用**对话框随即打开，请按照中的步骤[获取 Visual Studio 中的 SAP 操作的元数据](../../adapters-and-accelerators/adapter-sap/get-metadata-for-sap-operations-in-visual-studio.md)连接到 SAP 系统和浏览和搜索操作。 若要创建 WCF 服务协定的操作，你选择，请确保**服务 （入站操作）**从选择**选择协定类型**下拉列表。  
  
3.  选择所有你想要为目标，请单击操作后**确定**来生成 WCF 服务协定。  
  
 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]将三个文件添加到你的项目：  
  
-   **SAPBindingInterface.cs**。 此文件包含生成的 WCF 服务协定 （接口），并为所选的操作的帮助器代码。  
  
-   **SAPBindingService.cs**。 此文件包含实现 SAPBindingInterface.cs 中定义的接口的存根处理的 WCF 服务类。 你可以实现直接在此类的方法中处理 RFC、 tRFC 或 IDOC 的业务逻辑。  
  
-   **App.config**。此文件包含的绑定配置、 终结点行为和基于你所做的选择时配置的绑定和连接的服务终结点配置[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。  
  
    > [!IMPORTANT]
    >  在使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]，如果未指定的字符串类型的绑定属性的值，并且其默认值为 null，然后，绑定属性将不可用的 app.config 文件中。 你必须手动添加绑定属性，并且其值在 app.config 文件中，如果需要。  
  
> [!NOTE]
>  无需在配置连接 URI 时指定的 RFC 服务器参数为[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]来生成 WCF 服务协定。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]从通过客户端连接 SAP 系统中检索元数据。  
  
## <a name="generate-a-wcf-client-class-or-a-wcf-service-contract-by-using-svcutilexe"></a>通过使用 svcutil.exe 生成 WCF 客户端类或 WCF 服务协定  
 你可以使用 svcutil.exe 为你的应用程序生成 WCF 客户端类或 WCF 服务协定。 你必须配置 svcutil.exe 以将它与[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。 有关详细信息，有关配置和使用与 svcutil.exe [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]，请参阅[用于 mySAP Business Suite ServiceModel 元数据实用工具使用 BizTalk 适配器](../../adapters-and-accelerators/adapter-sap/use-the-servicemodel-metadata-utility-with-the-sap-adapter-in-biztalk.md)。  
  
 Svcutil.exe 生成输出文件中的 WCF 客户端类或 WCF 服务协定。 默认文件名称为 output.cs。 你必须手动将此文件加入你[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]项目。  
  
## <a name="see-also"></a>另请参阅  
[开发 SAP 应用程序使用 WCF 通道模型](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-channel-model.md)