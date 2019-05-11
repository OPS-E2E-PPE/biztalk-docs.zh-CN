---
title: 生成 WCF 客户端或 WCF 服务协定为 Siebel 解决方案项目 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- how to, generate a client class by using svcutil.exe
- creating a proxy
- how to, create a proxy
- WCF service model, creating a proxy
- how to, generate a client class by using the Add Adapter Service Reference Plug-in
- how to, generate a client class
ms.assetid: 52c32c86-6403-4bb4-9d43-1319d19a6b49
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b380496d0186789d3ff8109903d88e8f01b39c46
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65371602"
---
# <a name="generate-a-wcf-client-or-a-wcf-service-contract-for-siebel-solution-artifacts"></a>生成 WCF 客户端或 WCF 服务协定为 Siebel 解决方案项目
可以使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]针对所选操作对 Siebel 项目生成 WCF 客户端类。 此外可以使用 ServiceModel Metadata Utility Tool (svcutil.exe) 来生成 WCF 客户端类;但是，[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]公开 ServiceModel Metadata Utility Tool 通过标准的 Microsoft Windows 界面的功能。 它还提供浏览和搜索功能，使用 svcutil.exe 工具中，未提供，并生成一个基于连接到 Siebel 系统时选择的绑定属性的配置文件。  
  
## <a name="generating-a-wcf-client-class-by-using-the-add-adapter-service-reference-plug-in"></a>使用生成 WCF 客户端类添加适配器服务引用插件  
 执行以下步骤以使用生成 WCF 客户端类[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。  
  
#### <a name="to-generate-a-wcf-client-class"></a>若要生成 WCF 客户端类  
  
1. 在中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]解决方案资源管理器，右键单击项目，然后依次**添加适配器服务引用**。  
  
2. 之后**添加适配器服务引用**对话框打开，请按照中的步骤[检索 Visual Studio 中的 Siebel 操作的元数据](../../adapters-and-accelerators/adapter-siebel/get-metadata-for-siebel-operations-in-visual-studio.md)连接到 Siebel 系统和浏览和搜索操作。 若要创建你选择的操作的 WCF 客户端类，务必**客户端 （出站操作）** 从所选**选择协定类型**下拉列表 （这是默认值）。  
  
3. 选择所有你想要为目标，请单击操作后**确定**生成 WCF 客户端类。  
  
   [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]将两个文件添加到你的项目：  
  
- WCF 客户端代码文件。 此文件包含生成的 WCF 客户端类和帮助程序的代码所选的操作。 首次运行[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]它将生成此文件，其默认名称**SiebelBindingClient.cs** 。 如果再次运行，将调用的下一个文件，它将生成**SiebelBindingClient1.cs**。  数字后缀将增加 1 为您生成每个新文件。  您还可以更改默认前缀**SiebelBinding**通过输入中的不同前缀**文件名前缀**字段[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]选择前**确定**到生成的文件。  
  
- **App.config**。此文件包含的绑定配置和客户端终结点配置的基于配置的连接时所做的选择[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。 App.config 文件的内容的详细信息，请参阅[为 Siebel 系统配置 WCF 客户端](../../adapters-and-accelerators/adapter-siebel/configure-a-wcf-client-for-a-siebel-system.md)。  
  
  > [!IMPORTANT]
  >  同时使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]，如果未指定字符串类型的绑定属性的值，并且其默认值为 null，然后，绑定属性将不可用的 app.config 文件中。 您必须手动添加的绑定属性和其值在 app.config 文件中，如果所需。  
  
## <a name="generating-a-wcf-client-class-by-using-svcutilexe"></a>使用 svcutil.exe 生成 WCF 客户端类  
 可以使用 svcutil.exe 为你的应用程序生成 WCF 客户端类。 必须配置 svcutil.exe 与其一起使用[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]。 有关详细信息，有关配置和使用与 svcutil.exe [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]，请参阅[用于 Siebel eBusiness 应用程序的 BizTalk 适配器使用 ServiceModel Metadata Utility Tool](../../adapters-and-accelerators/adapter-siebel/use-the-servicemodel-metadata-utility-with-the-siebel-adapter.md)。  
  
 Svcutil.exe 包含 output.cs 的默认文件名称的输出文件中生成 WCF 客户端类。 您必须手动将此文件加入你[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]项目。  
  
## <a name="see-also"></a>请参阅  
 [开发 Siebel 应用程序使用 WCF 服务模型](../../adapters-and-accelerators/adapter-siebel/develop-siebel-applications-using-the-wcf-service-model.md)