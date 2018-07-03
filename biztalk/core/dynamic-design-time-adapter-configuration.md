---
title: 动态设计时适配器配置 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 36127d62-0348-42bb-981f-19fcad26efce
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e54d45c920fa430880e7a51d66ae500bfa9e13af
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988142"
---
# <a name="dynamic-design-time-adapter-configuration"></a>动态设计时适配器配置
静态设计时适配器配置以及“添加适配器元数据”向导中的标准默认 UI 有时不够灵活，不足以显示适配器的服务，以供 BizTalk 项目导入。 此时可以选用动态设计时配置，在其中为向导提供自定义 UI，以显示和选择您的适配器服务。 BizTalk 适配器框架提供了一组 API，可供您导入适配器所需的架构以及显示自定义 UI。  
  
 本部分介绍如何实现您的自定义适配器的动态设计时配置功能。 您决定做出的更改将基于要与适配器通信的应用程序的需要，以及该适配器需要实现的逻辑。 指向章节的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]可用时提供帮助描述这些步骤的更多详细信息或提供其他背景信息。 此外，本部分还指出了示例文件适配器文档中提供相关示例的位置。  
  
## <a name="guidelines-for-the-dynamic-development-process"></a>有关动态开发过程的准则  
 下面的列表提供了有助于在适配器中构建动态设计时功能的建议。 在开发过程中可能不需要执行所有这些步骤操作，也不严格依照顺序执行它们。  
  
1. 创建适配器配置需求以及您需要设置的配置参数的列表。 如果要对所有接收位置和发送端口全局性地使用这些参数，请在处理程序架构配置文件中指定这些参数。 如果参数特定于端口或位置，请在发送端口和接收位置配置文件中指定这些参数。  
  
2. 修改各适配器属性页，说明所有新的配置参数。 有关此步骤的信息，请参阅[适配器配置架构](../core/adapter-configuration-schemas.md)。  
  
3. 为“添加适配器元数据”向导创建自定义用户界面 (UI)，以便选择要添加到项目中的架构。 在此列出的所有建议中，动态适配器与静态适配器只在这一条建议上有所不同。 有关此步骤的详细信息，请参阅[动态适配器 DisplayUI 方法](../core/dynamic-adapter-displayui-method.md)和类[Microsoft.BizTalk.Adapter.Framework.IDynamicAdapterConfig.DisplayUI](http://msdn.microsoft.com/library/microsoft.biztalk.adapter.framework.idynamicadapterconfig.displayui.aspx)。  
  
4. 修改示例代码，将架构作为 Web Services 描述语言 (WSDL) 文件返回。 有关此步骤的详细信息，请参阅[静态适配器 IStaticAdapterConfig 接口](../core/static-adapter-istaticadapterconfig-interface.md)。  
  
5. 修改现有的 WSDL 文件，或者创建新的 WSDL 文件。 有关此步骤的详细信息，请参阅[适配器 WSDL 文件](../core/adapter-wsdl-files.md)。  
  
6. 修改示例代码，以返回适配器所需的但未包含在 WSDL 文件中的附加 XSD 文件。 有关此步骤的详细信息，请参阅[适配器 GetSchema 方法](../core/adapter-getschema-method.md)。  
  
7. 修改适配器注册表项并运行适配器注册表文件。 有关此步骤的详细信息，请参阅[适配器注册文件](../core/adapter-registration-file.md)。  
  
8. 静态适配器安装到[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 有关此步骤的详细信息，请参阅[适配器安装到 BizTalk Server](../core/install-the-adapter-into-biztalk-server.md)。  
  
9. 测试对适配器属性页所做的更改。 重新生成适配器，以测试在“添加适配器元数据”向导中出现的 UI。 有关此步骤的详细信息，请参阅[生成和测试适配器项目](../core/build-and-test-the-adapter-project.md)  
  
## <a name="in-this-section"></a>本节内容  
  
-   [动态适配器 DisplayUI 方法](../core/dynamic-adapter-displayui-method.md)