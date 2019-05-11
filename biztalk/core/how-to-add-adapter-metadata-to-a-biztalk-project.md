---
title: 如何向 BizTalk 项目添加适配器元数据 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e439e5bf-94b3-4582-bacc-b058e6eb8e17
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0f06b60b1dce1b0b9df785d25552f688f7793858
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387312"
---
# <a name="how-to-add-adapter-metadata-to-a-biztalk-project"></a>如何向 BizTalk 项目添加适配器元数据
添加适配器元数据向导，可向 BizTalk 项目添加适配器元数据。 此数据包括架构、 消息类型和从业务流程的适配器通信所需的端口类型。 对应用程序适配器，例如 FTP，对应于这些应用程序适配器到系统的请求架构中使用添加适配器元数据向导。 请注意，如 HTTP 传输适配器通常不会使用架构。  
  
 以下过程将引导你完成添加适配器元数据的一般步骤。  
  
### <a name="to-add-adapter-metadata-to-a-biztalk-project"></a>若要向 BizTalk 项目添加适配器元数据  
  
1. 在你[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]BizTalk 项目，请在解决方案资源管理器，右键单击你的项目，单击**添加**，然后单击**添加生成的项**。  
  
2. 在中**添加生成的项- \<** <em>项目名称</em>**\>** 对话框中，在**模板**部分中，选择**添加适配器**，然后单击**打开**。  
  
3. 在添加适配器元数据向导中，在**选择适配器**页上，执行以下操作。  
  
   |使用此选项|执行的操作|  
   |--------------|----------------|  
   |适配器列表框|选择要添加到项目的已注册的适配器。|  
   |SQL Server|输入 BizTalk 数据库服务器名称。|  
   |“数据库”|显示所选的服务器的 BizTalk 管理数据库的列表。|  
   |Port|可选。 显示端口创建并存储在 BizTalk 管理数据库的列表。 显示仅配置为使用所选适配器的端口。|  
  
    单击“下一步” 。  
  
   > [!NOTE]
   >  尝试添加的生成的架构包含的字符**System.XML.XMLConvert**类不支持编译错误的结果。  
  
4. 如果在使用静态适配器**选择导入的服务**页上，从树视图中，选择可用的服务的一组，然后单击**完成**。  
  
    （或者）  
  
    如果您使用的是动态适配器，请按照自定义用户界面来完成该向导中的步骤。  
  
   在完成向导后[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]列出了在解决方案资源管理器中的.odx 和.xsd 文件。