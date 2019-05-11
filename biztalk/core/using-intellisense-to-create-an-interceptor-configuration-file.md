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
ms.openlocfilehash: 502b9f1d213a9440bb19820f9998604267045a44
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396853"
---
# <a name="using-intellisense-to-create-an-interceptor-configuration-file"></a>使用 IntelliSense 创建侦听器配置文件
可以使用中的 IntelliSense 和架构验证[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]来帮助您构造从架构上来说有效的侦听器配置文件。 BAM 管理实用程序验证侦听器配置文件根据基本侦听器配置架构，并且如果文件不是有效的不会部署架构。 如果该文件通过了根据基本侦听器配置架构进行验证，它根据等特定于技术的架构验证[!INCLUDE[firstref_btsWinWorkflowFoundation](../includes/firstref-btswinworkflowfoundation-md.md)]架构或[!INCLUDE[firstref_btsWinCommFoundation](../includes/firstref-btswincommfoundation-md.md)]架构在运行时，如果遇到错误，将没有拦截会出现。 可以通过使用中的架构验证来避免这些错误[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]构造侦听器配置文件时。  
  
> [!NOTE]
>  示例 BAM 侦听器配置 XSD 文件已安装的 SDK 文件。 它们可以位于[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\BAM\InterceptorXSDs:  
> 
> - CommonInterceptorConfiguration.xsd  
>   -   WcfInterceptorConfiguration.xsd  
>   -   WorkflowInterceptorConfiguration.xsd  
  
### <a name="to-obtain-a-copy-of-the-interceptor-schemas"></a>若要获取侦听器架构的副本  
  
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
   >  如果保存使用不同的名称的文件，请改为选择这些文件。  
  
7. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 现在打开时验证您的侦听器配置文件，并在创建和修改该文件提供 IntelliSense 帮助。  
  
## <a name="see-also"></a>请参阅  
 [Windows Workflow Foundation 架构](../core/windows-workflow-foundation-schema.md)   
 [Windows Communication Foundation 架构](../core/windows-communication-foundation-schema.md)