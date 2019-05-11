---
title: 登记业务流程 （BizTalk Server 示例） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, examples
- orchestrations, enlisting
- examples, orchestrations
ms.assetid: d8d53e59-2313-40dd-a278-0a29d8eb4ce8
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c70276a30004c1a21f95a3e2ff43a28209deea87
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389069"
---
# <a name="enlist-orchestration-biztalk-server-sample"></a>登记业务流程 （BizTalk Server 示例）
登记业务流程示例演示如何登记到主机的 BizTalk Server 业务流程。  
  
> [!WARNING]
>  如果不需要应在部署后删除的部署脚本。 管理脚本和其他必须保持的脚本应受 ACL 并加以密切监视。  
  
## <a name="what-this-sample-does"></a>本示例的用途  
 此示例包含用于访问 Windows Management Instrumentation (WMI) 对象模型中，Visual Basic Scripting Edition (VBScript) 版本和用于访问的 Visual C# 版本**System.Management**由提供的对象.NET Framework 中。 这两个版本最终会访问 BizTalk Server WMI 提供程序，执行以下操作：  
  
-   给定的业务流程名称和程序集名称，查询的特定部署 BizTalk Server 业务流程。  
  
-   该业务流程登记到默认主机。  
  
-   处理任何错误，以便向用户返回有意义的信息。  
  
## <a name="where-to-find-this-sample"></a>本示例所在的位置  
 这些示例位于以下 SDK 位置：  
  
- VBScript 版本：\<*Samples Path*\>\Admin\WMI\Enlist Orchestration\VBScript\  
  
- VisusalC#版本：\<*示例路径*\>\Admin\WMI\Enlist Orchestration\CSharp\  
  
  下表显示了本示例中的文件及其用途说明：  
  
|文件|Description|  
|---------------|-----------------|  
|\VBScript 文件夹的位置：<br /><br /> EnlistOrch.vbs|采用参数指定的业务流程登记到主机的 VBScript 文件。|  
|\CSharp 文件夹的位置：<br /><br /> App.ico、 AssemblyInfo.cs、 BTSampleEnlistOrc.csproj、 BTSampleEnlistOrc.sln 和 EnlistOrc.cs|项目、 解决方案和源代码文件生成视觉对象C#命令行应用程序，采用参数指定的业务流程登记到主机。|  
  
## <a name="building-and-initializing-this-sample"></a>生成并初始化此示例  
 登记业务流程示例的 VBScript 版本包括不需要生成或初始化的单一 Visual Basic 脚本文件。  
  
#### <a name="to-build-the-visual-c-version-of-the-enlist-orchestration-sample"></a>若要生成视觉对象C#版本的登记业务流程示例  
  
1. 在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，打开 BTSampleEnlistOrc.sln 解决方案文件。  
  
2. 在中**构建**菜单上，单击**生成解决方案**。  
  
#### <a name="to-run-the-enlist-orchestration-sample"></a>若要运行登记业务流程示例。  
  
1.  在命令窗口中，导航到以下文件夹中，具体取决于是否想要运行的 VBScript 版本还是视觉对象之一C#版本的此示例，分别：  
  
     \<*Samples Path*\>\Admin\WMI\Enlist Orchestration\VBScript\  
  
     \<*示例路径*\>AdminWMIEnlist OrchestrationCSharpbinDebug  
  
2.  运行文件 EnlistOrch.vbs 使用 cscript 程序或运行文件 EnlistOrc.exe，具体取决于是否想要运行的 VBScript 版本还是 VisualC#版本的此示例，分别。 在任何情况下，传递下列命令行参数：  
  
    -   **\<** ***OrchestrationName* \>.** 要登记业务流程的名称。  
  
    -   **\<** ***AssemblyName* \>.** 在其中部署该业务流程的程序集的名称。 如果程序集名称包含空格，将名称括起来。  
  
         例如：(VBScript):  
  
        ```  
        cscript EnlistOrch.vbs MyBusinessOrchestration "My Business Assembly"  
        ```  
  
         -或者-(Visual C#):  
  
        ```  
        EnlistOrc MyBusinessOrchestration "My Business Assembly"  
        ```  
  
## <a name="comments"></a>注释  
 可以在中执行的所有任务[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]通过使用访问 Windows WMI 对象模型的脚本，并通过使用 Visual C# 访问，也可以执行管理控制台**System.Management**提供对象由.NET Framework 中。  
  
 EnlistOrch.vbs 脚本文件和视觉对象C#源文件 EnlistOrc.cs 包含详细的注释了进一步说明他们执行的操作。 有关详细信息，请参阅在 Windows Management Instrumentation [ http://go.microsoft.com/fwlink/?LinkId=21102 ](http://go.microsoft.com/fwlink/?LinkId=21102)。  
  
## <a name="see-also"></a>请参阅  
 [Admin-WMI（BizTalk Server 示例文件夹）](../core/admin-wmi-biztalk-server-samples-folder.md)