---
title: 适配器设计时配置 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f5e7b63c-6e17-4c54-9bbf-6964668a2420
caps.latest.revision: 27
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 815690aee7178db52936e8f1aca5641d1be945b6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987366"
---
# <a name="adapter-design-time-configuration"></a>适配器设计时配置
适配器包含一个运行时组件和一个设计时组件。 运行时组件对于用户是不可见的。 它是以透明方式负责的传输、 回执和处理[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]消息。  
  
 适配器的设计时组件可通过管理用户界面看到。 它负责显示可用属性、接受管理输入以及验证输入以配置适配器。 设计时组件允许对适配器的属性进行适当配置以使运行时功能能够正确交换消息，这一点是非常重要的。  
  
 本部分仅讨论适配器的设计时组件。 因此，我们将主要关注如何显示和设置适配器的配置。 有两种方法来配置适配器：  
  
- **属性浏览器。** 适配器属性的发送或接收端口或发送或接收处理程序，通过其属性菜单将通过使用配置[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。 在这些项目的配置过程中，可以选择适配器（传输）并使用属性浏览器来配置其属性。 适用的属性通过一个带有集名称的架构来显示。 例如，对于一个发送（传输）处理程序，属性将位于 TransmitHandler.xsd 文件中；对于一个接收位置，属性将位于 ReceiveLocation.xsd 文件中。  此适配器应实现**IAdapterConfig**接口来定位和加载适当架构，以便公开属性浏览器中的特定属性。 **IAdapterConfigValidation**接口可用来验证这些条目并保存配置数据之前进行最后的修改的值。  
  
- **添加适配器元数据向导。** 对于应用程序和数据库适配器，您可能需要导入描述适配器需要在 BizTalk 项目中的消息类型和端口类型的支持架构[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。 或者，有时需要使用适配器提供的服务。 使用“添加适配器元数据向导”可以查看适配器支持的服务并将相关消息类型和端口类型导入到您的项目中。 此过程称为“元数据搜集”。 作为适配器开发人员创建 XML 文件描述这些服务并在设计时通过将其公开给向导**IStaticAdapterConfig**或**IDynamicAdapterConfig**接口，使用以下结果：  
  
  -   **静态适配器。** 向导提供一个标准默认分层树结构，用于显示适配器的服务。 静态适配器定义为使用向导提供的标准树用户界面 (UI) 的适配器。 使用**IStaticAdapterConfig.GetServiceOrganization**并**GetServiceDescription**方法以允许所选的服务添加到 BizTalk 项目中。 这是适配器开发人员的最简单的配置选择，但其不利的一面是对显示格式要求严格。  
  
  -   **动态适配器。** 如果向导提供的基本服务选择 UI 不够灵活，无法满足您的 UI 需要，则可以创建可由向导动态显示的自定义 UI。 使用**IDynamicAdapterConfig.DisplayUI**方法以显示自定义用户界面中，以允许所选服务添加到 BizTalk 项目中。  
  
  本部分提供了以静态或动态方式处理设计时配置的两套方案的指南。  
  
  Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]软件开发工具包 (SDK) 包含可以使用一个示例文件适配器用作模板来创建和自定义您自己的适配器设计时配置解决方案。 每个设计时配置主题中都提供了有关该示例文件适配器的注释和参考，以帮助您修改自己的自定义适配器配置要求。 为更好地理解这些指南，您可能需要安装、生成和运行 SDK 中提供的示例文件适配器。 请参阅[文件适配器 （BizTalk Server 示例）](../core/file-adapter-biztalk-server-sample.md)有关详细信息。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [静态设计时适配器配置](../core/static-design-time-adapter-configuration.md)  
  
-   [动态设计时适配器配置](../core/dynamic-design-time-adapter-configuration.md)  
  
-   [适配器配置架构](../core/adapter-configuration-schemas.md)  
  
-   [适配器 WSDL 文件](../core/adapter-wsdl-files.md)  
  
-   [适配器 GetSchema 方法](../core/adapter-getschema-method.md)  
  
-   [适配器注册文件](../core/adapter-registration-file.md)  
  
-   [将适配器安装到 BizTalk Server 中](../core/install-the-adapter-into-biztalk-server.md)  
  
-   [生成和测试适配器项目](../core/build-and-test-the-adapter-project.md)