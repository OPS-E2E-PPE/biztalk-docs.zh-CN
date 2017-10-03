---
title: "静态的设计时适配器配置 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 332723a4-e39d-43f5-af4d-bf9f56496535
caps.latest.revision: "28"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f8337e4f53afe22ccbde0e1d1d2a6437d280011d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="static-design-time-adapter-configuration"></a>静态的设计时适配器配置
适配器的设计时部分负责定义所有可用属性并且验证用户输入。 在静态设计时配置中，适配器使用默认用户界面 (UI) 显示和编辑其属性。  
  
 本部分介绍如何实现您的自定义适配器的静态设计时配置功能。 您决定做出的更改将基于要与适配器通信的应用程序的需要，以及该适配器需要实现的逻辑。 指向章节的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]可用时提供帮助描述了这些步骤中更多详细信息或提供其他背景信息。 此外，本部分还指出了示例文件适配器文档中提供相关示例的位置。  
  
## <a name="guidelines-for-the-static-development-process"></a>有关静态开发过程的准则  
 下面的列表提供了有助于在适配器中构建静态设计时功能的建议。 开发过程中，您不必执行全部步骤，也无需严格依照顺序执行这些步骤。  
  
1.  创建适配器配置需求以及您需要设置的配置参数的列表。 如果要对所有接收位置和发送端口全局性地使用这些参数，请在处理程序架构配置文件中指定这些参数。 如果参数特定于端口或位置，请在发送端口和接收位置配置文件中指定这些参数。  
  
2.  修改各适配器属性页，说明所有新的配置参数。 有关此步骤的信息，请参阅[适配器配置架构](../core/adapter-configuration-schemas.md)。  
  
3.  使用“添加适配器元数据”向导修改架构类别的树视图。 有关此步骤的详细信息，请参阅[添加适配器元数据向导中的架构类别](../core/schema-categories-in-the-add-adapter-metadata-wizard.md)  
  
4.  修改示例代码，将架构作为 Web Services 描述语言 (WSDL) 文件返回。 有关此步骤的详细信息，请参阅[静态适配器 IStaticAdapterConfig 接口](../core/static-adapter-istaticadapterconfig-interface.md)。  
  
5.  修改现有的 WSDL 文件，或者创建新的 WSDL 文件。 有关此步骤的详细信息，请参阅[适配器 WSDL 文件](../core/adapter-wsdl-files.md)。  
  
6.  修改示例代码，以返回适配器所需的但未包含在 WSDL 文件中的附加 XSD 文件。 有关此步骤的详细信息，请参阅[适配器 GetSchema 方法](../core/adapter-getschema-method.md)。  
  
7.  修改适配器注册表项并运行适配器注册表文件。 有关此步骤的详细信息，请参阅[适配器注册文件](../core/adapter-registration-file.md)。  
  
8.  安装适配器放置于静态[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 有关此步骤的详细信息，请参阅[到 BizTalk Server 中安装适配器](../core/install-the-adapter-into-biztalk-server.md)。  
  
9. 测试对适配器属性页所做的更改。 重新生成适配器，以测试在“添加适配器元数据”向导中出现的 UI。 有关此步骤的详细信息，请参阅[生成和测试适配器项目](../core/build-and-test-the-adapter-project.md)  
  
## <a name="in-this-section"></a>本节内容  
  
-   [静态适配器 IStaticAdapterConfig 接口](../core/static-adapter-istaticadapterconfig-interface.md)  
  
-   [架构中的类别添加适配器元数据向导](../core/schema-categories-in-the-add-adapter-metadata-wizard.md)