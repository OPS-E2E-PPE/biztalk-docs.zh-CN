---
title: "生成 WCF 客户端或 WCF 服务协定的 Siebel 解决方案项目 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- how to, generate a client class by using svcutil.exe
- creating a proxy
- how to, create a proxy
- WCF service model, creating a proxy
- how to, generate a client class by using the Add Adapter Service Reference Plug-in
- how to, generate a client class
ms.assetid: 52c32c86-6403-4bb4-9d43-1319d19a6b49
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c75615f0e6a3f6e4c947a7c13888558b7a666e77
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="generate-a-wcf-client-or-a-wcf-service-contract-for-siebel-solution-artifacts"></a>生成 WCF 客户端或 Siebel 解决方案项目关联的 WCF 服务协定
你可以使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]生成 WCF 客户端类针对 Siebel 项目上的所选操作。 此外可以使用 ServiceModel 元数据实用工具 (svcutil.exe) 生成 WCF 客户端类;但是，[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]公开通过标准的 Microsoft Windows 界面 ServiceModel 元数据实用工具的功能。 它还提供浏览和搜索功能，使用 svcutil.exe 工具中，未提供，并生成一个基于连接到 Siebel 系统时选择的绑定属性的配置文件。  
  
## <a name="generating-a-wcf-client-class-by-using-the-add-adapter-service-reference-plug-in"></a>通过使用生成 WCF 客户端类添加插件的适配器服务引用  
 执行以下步骤以使用生成 WCF 客户端类[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。  
  
#### <a name="to-generate-a-wcf-client-class"></a>若要生成 WCF 客户端类  
  
1.  在[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]解决方案资源管理器，右键单击你的项目，并依次**添加适配器服务引用**。  
  
2.  后**添加适配器服务引用**对话框随即打开，请按照中的步骤[检索用于 Siebel 操作 Visual Studio 中的元数据](../../adapters-and-accelerators/adapter-siebel/get-metadata-for-siebel-operations-in-visual-studio.md)连接到 Siebel 系统和浏览和搜索操作。 若要创建的操作，你选择一个 WCF 客户端类，请确保**客户端 （出站操作）**从选择**选择协定类型**（这是默认值） 的下拉列表。  
  
3.  选择所有你想要为目标，请单击操作后**确定**生成 WCF 客户端类。  
  
 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]将两个文件添加到你的项目：  
  
-   WCF 客户端代码文件。 此文件包含生成的 WCF 客户端类和帮助程序的代码所选的操作。 首次运行[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]它将生成此文件具有默认名称**SiebelBindingClient.cs** 。 如果再次运行，将调用它生成的下一个文件**SiebelBindingClient1.cs**。  数字后缀将增加 1 为你生成每个新文件。  你还可以更改默认的前缀**SiebelBinding**通过输入在不同的前缀**文件名前缀**字段[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]之前选择**确定**到生成文件。  
  
-   **App.config**。此文件包含的绑定配置和客户端终结点配置的基于配置的连接时所做的选择[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。 App.config 文件的内容的详细信息，请参阅[为 Siebel 系统配置 WCF 客户端](../../adapters-and-accelerators/adapter-siebel/configure-a-wcf-client-for-a-siebel-system.md)。  
  
    > [!IMPORTANT]
    >  在使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]，如果未指定的字符串类型的绑定属性的值，并且其默认值为 null，然后，绑定属性将不可用的 app.config 文件中。 你必须手动添加绑定属性，并且其值在 app.config 文件中，如果需要。  
  
## <a name="generating-a-wcf-client-class-by-using-svcutilexe"></a>使用 svcutil.exe 生成 WCF 客户端类  
 要为你的应用程序生成 WCF 客户端类，可以使用 svcutil.exe。 你必须配置 svcutil.exe 以将它与[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]。 有关详细信息，有关配置和使用与 svcutil.exe [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]，请参阅[用于 Siebel eBusiness Applications ServiceModel 元数据实用工具使用 BizTalk 适配器](../../adapters-and-accelerators/adapter-siebel/use-the-servicemodel-metadata-utility-with-the-siebel-adapter.md)。  
  
 Svcutil.exe 在具有 output.cs 的默认文件名的输出文件中生成 WCF 客户端类。 你必须手动将此文件加入你[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]项目。  
  
## <a name="see-also"></a>另请参阅  
 [开发 Siebel 应用程序使用 WCF 服务模型](../../adapters-and-accelerators/adapter-siebel/develop-siebel-applications-using-the-wcf-service-model.md)