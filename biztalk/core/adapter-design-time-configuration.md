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
ms.openlocfilehash: 7f4cad6268e044adef1d9f94c84456d628a41fd4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65361598"
---
# <a name="adapter-design-time-configuration"></a>适配器设计时配置
适配器包含运行时和设计时组件。 运行时组件不是对用户可见的。 它是以透明方式负责的传输、 回执和处理[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]消息。  
  
 适配器的设计时组件是通过管理用户界面中可见。 它负责显示可用的属性、 接受管理输入以及验证输入以配置适配器。 很重要的设计时组件允许的适配器的属性，以使运行时功能能够正确交换消息的正确配置。  
  
 本部分讨论适配器的设计时组件。 因此，我们将主要关注如何显示和设置适配器的配置。 有两种方法来配置适配器：  
  
- **属性浏览器。** 适配器属性的发送或接收端口或发送或接收处理程序，通过其属性菜单将通过使用配置[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。 在这些项目的配置期间选择适配器 （传输），并通过使用属性浏览器配置其属性。 适用的属性将显示通过具有组名称的架构。 例如，对于发送 （传输） 处理程序属性将位于 TransmitHandler.xsd 文件;为接收位置将位于 ReceiveLocation.xsd 文件。  此适配器应实现**IAdapterConfig**接口来定位和加载适当架构，以便公开属性浏览器中的特定属性。 **IAdapterConfigValidation**接口可用来验证这些条目并保存配置数据之前进行最后的修改的值。  
  
- **添加适配器元数据向导。** 对于应用程序和数据库适配器，您可能需要导入描述适配器需要在 BizTalk 项目中的消息类型和端口类型的支持架构[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。 或者，有时需要使用适配器提供的服务。 添加适配器元数据向导，可查看适配器支持的服务和相关的消息类型和端口类型导入到你的项目。 此过程被称为"元数据搜集。 作为适配器开发人员创建 XML 文件描述这些服务并在设计时通过将其公开给向导**IStaticAdapterConfig**或**IDynamicAdapterConfig**接口，使用以下结果：  
  
  -   **静态适配器。** 该向导提供标准默认分层树结构，以显示适配器的服务。 静态适配器定义为使用由向导提供的标准树用户界面 (UI) 的适配器。 使用**IStaticAdapterConfig.GetServiceOrganization**并**GetServiceDescription**方法以允许所选的服务添加到 BizTalk 项目中。 这是适配器开发人员，最简单的配置选项，但其不利的一面是要求严格的显示格式。  
  
  -   **动态适配器。** 如果选择提供向导用户界面的基本服务并不灵活足以满足您可以创建由向导动态显示的自定义 UI 的 UI 需要。 使用**IDynamicAdapterConfig.DisplayUI**方法以显示自定义用户界面中，以允许所选服务添加到 BizTalk 项目中。  
  
  本部分提供用于处理静态或动态方式中的设计时配置的两个集的指导原则。  
  
  Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]软件开发工具包 (SDK) 包含可以使用一个示例文件适配器用作模板来创建和自定义您自己的适配器设计时配置解决方案。 在每个设计时配置主题来帮助你修改你自己的自定义适配器配置要求提供了说明和示例文件适配器有关的引用。 若要更好地了解这些准则，你可能想要安装、 生成和运行 SDK 中提供的示例文件适配器。 请参阅[文件适配器 （BizTalk Server 示例）](../core/file-adapter-biztalk-server-sample.md)有关详细信息。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [静态设计时适配器配置](../core/static-design-time-adapter-configuration.md)  
  
-   [动态设计时适配器配置](../core/dynamic-design-time-adapter-configuration.md)  
  
-   [适配器配置架构](../core/adapter-configuration-schemas.md)  
  
-   [适配器 WSDL 文件](../core/adapter-wsdl-files.md)  
  
-   [适配器 GetSchema 方法](../core/adapter-getschema-method.md)  
  
-   [适配器注册文件](../core/adapter-registration-file.md)  
  
-   [将适配器安装到 BizTalk Server 中](../core/install-the-adapter-into-biztalk-server.md)  
  
-   [生成和测试适配器项目](../core/build-and-test-the-adapter-project.md)