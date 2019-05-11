---
title: 静态设计时适配器配置 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 332723a4-e39d-43f5-af4d-bf9f56496535
caps.latest.revision: 28
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 081a7ed6fb6892eb08214d1844d98e7d87b503ee
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392936"
---
# <a name="static-design-time-adapter-configuration"></a>静态设计时适配器配置
适配器的设计时部分负责定义所有可用的属性并用于验证用户输入。 在静态设计时配置该适配器用于显示和编辑其属性使用默认用户界面 (UI)。  
  
 本部分介绍如何实现自定义适配器的静态设计时配置功能。 决定进行的更改将基于与应用程序的需求适配器通信和适配器需要实现的逻辑。 指向章节的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]可用时提供帮助描述这些步骤的更多详细信息或提供其他背景信息。 此外它还指出提供相关示例的示例文件适配器文档中的位置。  
  
## <a name="guidelines-for-the-static-development-process"></a>有关静态开发过程的准则  
 以下列表提供了有助于在适配器中构建静态设计时功能的建议。 在开发过程中可能不需要进行上述所有步骤，也不严格依照顺序执行它们。  
  
1. 创建适配器配置要求和所需设置的配置参数的列表。 如果全局使用的参数进行所有接收位置和发送端口，在处理程序架构配置文件中进行指定。 如果它们是端口或特定位置，配置在发送端口和接收位置配置文件。  
  
2. 修改适配器属性页的任何新的配置参数。 有关此步骤的信息，请参阅[适配器配置架构](../core/adapter-configuration-schemas.md)。  
  
3. 通过使用添加适配器元数据向导修改架构类别的树视图。 有关此步骤的详细信息，请参阅[添加适配器元数据向导中的架构类别](../core/schema-categories-in-the-add-adapter-metadata-wizard.md)  
  
4. 修改示例代码，以返回作为 Web 服务描述语言 (WSDL) 文件的架构。 有关此步骤的详细信息，请参阅[静态适配器 IStaticAdapterConfig 接口](../core/static-adapter-istaticadapterconfig-interface.md)。  
  
5. 修改现有的 WSDL 文件或创建新的 WSDL 文件。 有关此步骤的详细信息，请参阅[适配器 WSDL 文件](../core/adapter-wsdl-files.md)。  
  
6. 修改要返回的附加 XSD 文件所需的适配器不包括在 WSDL 文件中的示例代码。 有关此步骤的详细信息，请参阅[适配器 GetSchema 方法](../core/adapter-getschema-method.md)。  
  
7. 修改适配器注册表项并运行适配器注册表文件。 有关此步骤的详细信息，请参阅[适配器注册文件](../core/adapter-registration-file.md)。  
  
8. 静态适配器安装到[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 有关此步骤的详细信息，请参阅[适配器安装到 BizTalk Server](../core/install-the-adapter-into-biztalk-server.md)。  
  
9. 测试对适配器属性页所做的更改。 重新生成适配器，以测试将显示在 UI 中添加适配器元数据向导。 有关此步骤的详细信息，请参阅[生成和测试适配器项目](../core/build-and-test-the-adapter-project.md)  
  
## <a name="in-this-section"></a>本节内容  
  
-   [静态适配器 IStaticAdapterConfig 接口](../core/static-adapter-istaticadapterconfig-interface.md)  
  
-   [“添加适配器元数据”向导中的架构类别](../core/schema-categories-in-the-add-adapter-metadata-wizard.md)