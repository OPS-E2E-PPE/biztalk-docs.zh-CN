---
title: 登记业务流程 （BizTalk Server 示例） |Microsoft 文档
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
ms.openlocfilehash: 6e8d85a49b410f0571e8e9cb0be816f1feda139e
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25968859"
---
# <a name="enlist-orchestration-biztalk-server-sample"></a>登记业务流程 （BizTalk Server 示例）
“登记业务流程”示例演示如何将 BizTalk Server 业务流程登记到主机。  
  
> [!WARNING]
>  部署后，如果不再需要部署脚本，则应将其删除。 应通过 ACL 确保必须保留的管理脚本和其他脚本的安全并加以密切监视。  
  
## <a name="what-this-sample-does"></a>本示例的用途  
 此示例包括访问 Windows Management Instrumentation (WMI) 对象模型，Visual Basic Scripting Edition (VBScript) 版本和 Visual C# 版本访问**System.Management**由提供的对象.NET Framework 中。 上述两个版本最终会访问 BizTalk Server WMI 提供程序，以执行下列操作：  
  
-   根据给定的业务流程名称和程序集名称，查询部署的特定 BizTalk Server 业务流程。  
  
-   将此业务流程登记到默认主机。  
  
-   处理所有错误，以便向用户返回有意义的信息。  
  
## <a name="where-to-find-this-sample"></a>本示例所在的位置  
 本示例位于以下 SDK 位置：  
  
-   VBScript 版本： \<*示例路径*\>\Admin\WMI\Enlist Orchestration\VBScript\  
  
-   Visusal C# 版本： \<*示例路径*\>\Admin\WMI\Enlist Orchestration\CSharp\  
  
 下表显示了本示例中的文件及其用途说明：  
  
|文件|Description|  
|---------------|-----------------|  
|\VBScript 文件夹的内容：<br /><br /> EnlistOrch.vbs|采用参数指定要登记到主机的业务流程的 VBScript 文件。|  
|\CSharp 文件夹的内容：<br /><br /> App.ico、AssemblyInfo.cs、BTSampleEnlistOrc.csproj、BTSampleEnlistOrc.sln 和 EnlistOrc.cs|用于生成 Visual C# 命令行应用程序的项目、解决方案和源文件，该应用程序采用参数指定要登记到主机的业务流程。|  
  
## <a name="building-and-initializing-this-sample"></a>生成并初始化此示例  
 “登记业务流程”示例的 VBScript 版本包括一个 Visual Basic 脚本文件，您无需生成或初始化该脚本文件。  
  
#### <a name="to-build-the-visual-c-version-of-the-enlist-orchestration-sample"></a>生成“登记业务流程”示例的 Visual C# 版本  
  
1.  在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，打开解决方案文件 BTSampleEnlistOrc.sln。  
  
2.  在**生成**菜单上，单击**生成解决方案**。  
  
#### <a name="to-run-the-enlist-orchestration-sample"></a>运行登记业务流程示例  
  
1.  在命令窗口中，导航至下列文件夹之一，具体哪一个文件夹取决于您打算运行本示例的 VBScript 版本还是 Visual C# 版本：  
  
     \<*示例路径*\>\Admin\WMI\Enlist Orchestration\VBScript\  
  
     \<*示例路径*\>AdminWMIEnlist OrchestrationCSharpbinDebug  
  
2.  使用 cscript 程序运行 EnlistOrch.vbs 文件，或者运行 EnlistOrc.exe 文件，具体要运行哪一个文件取决于您打算运行本示例的 VBScript 版本还是 Visual C# 版本。 在任何事件中，传递以下命令行参数：  
  
    -   **\<** ***OrchestrationName* \>。** 要登记的业务流程的名称。  
  
    -   **\<** ***AssemblyName* \>。** 在其中部署业务流程的程序集的名称。 如果程序集名称包含空格，则将该名称置于引号中。  
  
         例如: (VBScript):  
  
        ```  
        cscript EnlistOrch.vbs MyBusinessOrchestration "My Business Assembly"  
        ```  
  
         - 或者 - (Visual C#)：  
  
        ```  
        EnlistOrc MyBusinessOrchestration "My Business Assembly"  
        ```  
  
## <a name="comments"></a>注释  
 你可以执行中的所有任务[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]使用访问 Windows WMI 对象模型的脚本以及通过使用 Visual C# 访问，还可以执行管理控制台**System.Management**提供的对象.NET framework 中。  
  
 EnlistOrch.vbs 脚本文件和 Visual C# 源文件 EnlistOrc.cs 包含详细注释，对其执行的操作做了进一步说明。 有关详细信息，请参阅在 Windows Management Instrumentation [http://go.microsoft.com/fwlink/?LinkId=21102](http://go.microsoft.com/fwlink/?LinkId=21102)。  
  
## <a name="see-also"></a>另请参阅  
 [Admin-WMI（BizTalk Server 示例文件夹）](../core/admin-wmi-biztalk-server-samples-folder.md)