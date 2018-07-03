---
title: 使用 IntelliSense 创建侦听器配置文件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 349ea1bf-a5d1-4464-bf4b-d8746c622377
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1d6df002c51bbcc51a3cb714e389a0f453a0693c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011350"
---
# <a name="using-intellisense-to-create-an-interceptor-configuration-file"></a>使用 IntelliSense 创建侦听器配置文件
可以使用 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 中的 IntelliSense 和架构验证来帮助您构造从架构上来说有效的侦听器配置文件。 BAM 管理实用工具根据基本侦听器配置架构验证您的侦听器配置文件，如果此文件无效，则不部署该架构。 如果文件通过了根据基本侦听器配置架构进行的验证，则在运行时会根据特定于技术的架构（如 [!INCLUDE[firstref_btsWinWorkflowFoundation](../includes/firstref-btswinworkflowfoundation-md.md)] 架构或 [!INCLUDE[firstref_btsWinCommFoundation](../includes/firstref-btswincommfoundation-md.md)] 架构）对其进行验证，如果出错，则不进行侦听。 构造侦听器配置文件时，可以通过使用 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 中的架构验证来避免这些错误。  
  
> [!NOTE]
>  示例 BAM 侦听器配置 XSD 文件与 SDK 文件一起安装。 它们位于 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\BAM\InterceptorXSDs：  
> 
> - CommonInterceptorConfiguration.xsd  
>   -   WcfInterceptorConfiguration.xsd  
>   -   WorkflowInterceptorConfiguration.xsd  
  
### <a name="to-obtain-a-copy-of-the-interceptor-schemas"></a>获取侦听器架构的副本  
  
1. 打开记事本或其他文本编辑器。  
  
2. 导航到[侦听器配置架构](../core/interceptor-configuration-schema.md)主题。  
  
3. 将内容粘贴到新文档中打开的文本编辑器，然后将该文件保存为文本文件使用名称**CommonInterceptorConfiguration.xsd** （或您自己选择的一个） 到您的硬盘。  
  
4. 重复这些步骤[!INCLUDE[firstref_btsWinWorkflowFoundation](../includes/firstref-btswinworkflowfoundation-md.md)]架构和[!INCLUDE[firstref_btsWinCommFoundation](../includes/firstref-btswincommfoundation-md.md)]架构主题使用的文件名**WorkflowInterceptorConfiguration.xsd**并**WcfInterceptorConfiguration.xsd**或名称你自己的选择。  
  
### <a name="to-use-intellisense-with-your-interceptor-configuration-file"></a>将 IntelliSense 用于侦听器配置文件  
  
1. 打开 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。  
  
2. 单击**文件**，单击**新建**，然后单击**文件**。  
  
3. 在中**新的文件**对话框中，选择**XML 文件**，然后单击**打开**。  
  
4. 查看通过右键单击编辑窗格中，然后单击属性窗格**属性**。  
  
5. 在属性窗格中单击**架构**，然后单击省略号 (**...**).  
  
6. 在中**XML 架构**对话框中，单击**添加**，然后导航到的位置的该架构，然后选择**CommonInterceptorConfiguration.xsd**和**WcfInterceptorConfiguration.xsd**如果你正在使用[!INCLUDE[firstref_btsWinCommFoundation](../includes/firstref-btswincommfoundation-md.md)]侦听器配置文件，或**WorkflowInterceptorConfiguration.xsd**如果你正在使用[!INCLUDE[firstref_btsWinWorkflowFoundation](../includes/firstref-btswinworkflowfoundation-md.md)]侦听器配置文件。  
  
   > [!NOTE]
   >  如果使用其他名称保存这些文件，请改为选择那些文件。  
  
7. 现在，打开侦听器配置文件时，[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 将对其进行验证，并在您创建和修改该文件时提供 IntelliSense 帮助。  
  
## <a name="see-also"></a>请参阅  
 [Windows Workflow Foundation 架构](../core/windows-workflow-foundation-schema.md)   
 [Windows Communication Foundation 架构](../core/windows-communication-foundation-schema.md)