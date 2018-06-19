---
title: 枚举接收位置 （BizTalk Server 示例） |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- receive locations, examples
- receive locations, enumerating
- examples, receive locations
ms.assetid: 27ff8ac6-7e8e-4dde-84d1-d21bf417ddd7
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 82fcdc400395d7bbfd6de8f9bc0fca85114a25dc
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25969075"
---
# <a name="enumerate-receive-locations-biztalk-server-sample"></a>枚举接收位置 （BizTalk Server 示例）
“枚举接收位置”示例演示了如何检索有关一个或多个接收位置的详细信息。  
  
> [!WARNING]
>  部署后，如果不再需要部署脚本，则应将其删除。 应通过 ACL 确保必须保留的管理脚本和其他脚本的安全并加以密切监视。  
  
## <a name="what-this-sample-does"></a>本示例的用途  
 此示例包括访问 Windows WMI 对象模型，Visual Basic Scripting Edition (VBScript) 版本和 Visual C# 版本访问**System.Management**由.NET Framework 提供的对象。 上述两个版本最终会访问 BizTalk Server WMI 提供程序，以执行下列操作：  
  
-   在已知名称的情况下，查询配置的接收位置集或某一特定接收位置。  
  
-   检索和显示每个相关接收位置的有关详细信息。  
  
-   处理所有错误，以便向用户返回有意义的信息。  
  
## <a name="where-to-find-this-sample"></a>本示例所在的位置  
 本示例位于以下 SDK 位置：  
  
-   VBScript 版本： \<*示例路径*\>\Admin\WMI\Enumerate Receive Locations\VBScript\  
  
-   Visual C# 版本： \<*示例路径*\>\Admin\WMI\Enumerate Receive Locations\CSharp\  
  
 下表显示了本示例中的文件及其用途说明：  
  
|文件|Description|  
|---------------|-----------------|  
|\VBScript 文件夹的内容：<br /><br /> EnumRecLocs.vbs|用于检索有关配置的所有接收位置的详细信息的 VBScript 文件。|  
|\CSharp 文件夹的内容：<br /><br /> App.ico、AssemblyInfo.cs、BTSampleEnumerateRLs.csproj、BTSampleEnumerateRLs.sln 和 EnumRLs.cs|用于生成 Visual C# 命令行应用程序的项目、解决方案和源文件，该应用程序检索有关配置的所有接收位置或某一特定接收位置的详细信息。|  
  
## <a name="building-and-initializing-this-sample"></a>生成并初始化此示例  
 “枚举接收位置”示例的 VBScript 版本包括一个 Visual Basic 脚本文件，您无需生成或初始化该脚本文件。  
  
#### <a name="to-build-the-visual-c-version-of-the-enumerate-receive-locations-sample"></a>生成“枚举接收位置”示例的 Visual C# 版本  
  
1.  在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，打开解决方案文件 BTSampleEnumerateRLs.sln。  
  
2.  在**生成**菜单上，单击**生成解决方案**。  
  
## <a name="running-this-sample"></a>运行本示例  
  
#### <a name="to-run-the-enumerate-receive-locations-sample"></a>运行“枚举接收位置”示例  
  
1.  在命令窗口中，导航至下列文件夹之一，具体哪一个文件夹取决于您是要运行本示例的 VBScript 版本还是 Visual C# 版本：  
  
     \<*示例路径*\>\Admin\WMI\Enumerate 接收 Locations\VBScript\  
  
     \<*示例路径*\>\Admin\WMI\Enumerate 接收 Locations\CSharp\bin\Debug\  
  
2.  使用 cscript 程序运行 EnumRecLocs.vbs 文件，或者运行 EnumRl.exe 文件，具体要运行哪一个文件取决于您是要运行本示例的 VBScript 版本还是 Visual C# 版本。 对于 Visual C# 版本，请传递下列两个命令行参数之一：  
  
    -   **\<ReceiveLocationName\>。** 将显示其详细信息的接收位置的名称。 如果接收位置名称包含空格，则将该名称置于引号中。  
  
    -   **/?.** 显示帮助。  
  
         例如 (VBScript)：  
  
        ```  
        cscript EnumRecLocs.vbs  
        ```  
  
         - 或者 - (Visual C#)：  
  
        ```  
        EnumRl "My Receive Location #3"  
        ```  
  
         - 或者 - (Visual C#)：  
  
        ```  
        EnumRl /?  
        ```  
  
    > [!NOTE]
    >  此示例的 VBScript 版本不接受任何命令行参数，并因此才能够检索和显示有关所有配置的详细信息接收位置。  
  
## <a name="comments"></a>注释  
 你可以执行中的所有任务[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]使用访问 Windows WMI 对象模型的脚本以及通过使用 Visual C# 访问，还可以执行管理控制台**System.Management**提供的对象.NET framework 中。  
  
 脚本文件 EnumRecLocs.vbs 和 Visual C# 源文件 EnumRLs.cs 包含详细的注释，使用更多有关他们执行的操作的说明。 有关详细信息，请参阅在 Windows Management Instrumentation [http://go.microsoft.com/fwlink/?LinkId=21102](http://go.microsoft.com/fwlink/?LinkId=21102)。  
  
## <a name="see-also"></a>另请参阅  
 [Admin-WMI（BizTalk Server 示例文件夹）](../core/admin-wmi-biztalk-server-samples-folder.md)