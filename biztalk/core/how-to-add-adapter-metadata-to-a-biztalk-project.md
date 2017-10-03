---
title: "如何将适配器元数据添加到 BizTalk 项目 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e439e5bf-94b3-4582-bacc-b058e6eb8e17
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b343ff085cee7049ea916a38fe1216e097200fbf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-add-adapter-metadata-to-a-biztalk-project"></a>如何将适配器元数据添加到 BizTalk 项目
使用“添加适配器元数据”向导可向 BizTalk 项目添加适配器元数据。 此数据包括与业务流程中的适配器通信所需的架构、消息类型和端口类型。 对应用程序适配器（例如 FTP）使用“添加适配器元数据”向导，将对应于这些应用程序适配器的架构拖入系统。 请注意，传输适配器（如 HTTP）通常不使用架构。  
  
 以下过程可引导您完成添加适配器元数据的一般步骤。  
  
### <a name="to-add-adapter-metadata-to-a-biztalk-project"></a>向 BizTalk 项目添加适配器元数据  
  
1.  在你[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]BizTalk 项目，请在解决方案资源管理器，右键单击你的项目，单击**添加**，然后单击**添加生成的项**。  
  
2.  在**添加生成的项的\<** *项目名称* **>** 对话框中，在**模板**部分中，选择**添加适配器**，然后单击**打开**。  
  
3.  在添加适配器元数据向导中，在**选择适配器**页上，执行以下操作。  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |适配器列表框|选择要添加到项目的已注册的适配器。|  
    |SQL Server|输入 BizTalk 数据库服务器名称。|  
    |数据库|显示用于所选服务器的 BizTalk 管理数据库的列表。|  
    |端口|可选。 显示在 BizTalk 管理数据库中创建和存储的端口的列表。 只显示配置为使用所选适配器的端口。|  
  
     单击 **“下一步”**。  
  
    > [!NOTE]
    >  尝试添加包含的生成的架构字符数**System.XML.XMLConvert**类不支持在编译错误的结果。  
  
4.  如果你使用的静态的适配器，在**选择服务添加到导入**页上，从树视图中，选择可用服务的一组，然后单击**完成**。  
  
     - 或者 -  
  
     如果使用的是动态适配器，请遵照自定义用户界面中的步骤完成向导。  
  
 完成向导之后，[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 将在“解决方案资源管理器”中列出 .odx 和 .xsd 文件。