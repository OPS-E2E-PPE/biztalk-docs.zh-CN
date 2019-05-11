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
ms.openlocfilehash: e27379b1d7f3132009db4837a8a5911206e9064a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65350487"
---
# <a name="dynamic-design-time-adapter-configuration"></a>动态设计时适配器配置
有些情况下不具有足够的灵活性，以显示适配器的 BizTalk 项目导入服务静态设计时适配器配置和标准默认 UI 中添加适配器元数据向导。 或者，您可以使用动态设计时配置，其中为向导可以显示并选择您的适配器服务提供自定义的 UI。 BizTalk 适配器框架提供了一系列你可以使用导入适配器所需的架构并显示自定义 UI 的 Api。  
  
 本部分介绍如何实现自定义适配器的动态设计时配置功能。 决定进行的更改将基于与应用程序的需求适配器通信和适配器需要实现的逻辑。 指向章节的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]可用时提供帮助描述这些步骤的更多详细信息或提供其他背景信息。 此外它还指出提供相关示例的示例文件适配器文档中的位置。  
  
## <a name="guidelines-for-the-dynamic-development-process"></a>有关动态开发过程的准则  
 以下列表提供了有助于在适配器中构建动态设计时功能的建议。 在开发过程中可能不需要执行所有这些步骤操作，也不严格依照顺序执行它们。  
  
1. 创建适配器配置要求和所需设置的配置参数的列表。 如果全局使用的参数进行所有接收位置和发送端口，在处理程序架构配置文件中进行指定。 如果它们是端口或特定位置，配置在发送端口和接收位置配置文件。  
  
2. 修改适配器属性页的任何新的配置参数。 有关此步骤的信息，请参阅[适配器配置架构](../core/adapter-configuration-schemas.md)。  
  
3. 创建自定义用户界面 (UI) 添加适配器元数据向导来选择要添加到项目的架构。 此处列出的所有建议的仅在于这是动态与静态适配器。 有关此步骤的详细信息，请参阅[动态适配器 DisplayUI 方法](../core/dynamic-adapter-displayui-method.md)和类[Microsoft.BizTalk.Adapter.Framework.IDynamicAdapterConfig.DisplayUI](http://msdn.microsoft.com/library/microsoft.biztalk.adapter.framework.idynamicadapterconfig.displayui.aspx)。  
  
4. 修改示例代码，以返回作为 Web 服务描述语言 (WSDL) 文件的架构。 有关此步骤的详细信息，请参阅[静态适配器 IStaticAdapterConfig 接口](../core/static-adapter-istaticadapterconfig-interface.md)。  
  
5. 修改现有的 WSDL 文件或创建新的 WSDL 文件。 有关此步骤的详细信息，请参阅[适配器 WSDL 文件](../core/adapter-wsdl-files.md)。  
  
6. 修改要返回的附加 XSD 文件所需的适配器不包括在 WSDL 文件中的示例代码。 有关此步骤的详细信息，请参阅[适配器 GetSchema 方法](../core/adapter-getschema-method.md)。  
  
7. 修改适配器注册表项并运行适配器注册表文件。 有关此步骤的详细信息，请参阅[适配器注册文件](../core/adapter-registration-file.md)。  
  
8. 静态适配器安装到[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 有关此步骤的详细信息，请参阅[适配器安装到 BizTalk Server](../core/install-the-adapter-into-biztalk-server.md)。  
  
9. 测试对适配器属性页所做的更改。 重新生成适配器，以测试将显示在 UI 中添加适配器元数据向导。 有关此步骤的详细信息，请参阅[生成和测试适配器项目](../core/build-and-test-the-adapter-project.md)  
  
## <a name="in-this-section"></a>本节内容  
  
-   [动态适配器 DisplayUI 方法](../core/dynamic-adapter-displayui-method.md)