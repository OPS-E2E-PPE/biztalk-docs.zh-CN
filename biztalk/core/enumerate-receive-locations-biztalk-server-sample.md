---
title: 枚举接收位置 （BizTalk Server 示例） |Microsoft Docs
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
ms.openlocfilehash: 7941cffb7e796c02b84c2dbd686fa20edbe9c8df
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530766"
---
# <a name="enumerate-receive-locations-biztalk-server-sample"></a>枚举接收位置 （BizTalk Server 示例）
枚举接收位置示例演示如何检索有关一个详细信息或多个接收位置。  
  
> [!WARNING]
>  如果不需要应在部署后删除的部署脚本。 管理脚本和其他必须保持的脚本应受 ACL 并加以密切监视。  
  
## <a name="what-this-sample-does"></a>本示例的用途  
 此示例包含用于访问 Windows WMI 对象模型中，Visual Basic Scripting Edition (VBScript) 版本和用于访问的 Visual C# 版本**System.Management**由.NET Framework 提供的对象。 这两个版本最终会访问 BizTalk Server WMI 提供程序，执行以下操作：  
  
-   查询的一套配置接收位置或某一特定接收位置，在给定其名称。  
  
-   检索和显示详细信息，有关每个接收位置所需。  
  
-   处理任何错误，以便向用户返回有意义的信息。  
  
## <a name="where-to-find-this-sample"></a>本示例所在的位置  
 这些示例位于以下 SDK 位置：  
  
- VBScript 版本：\<*示例路径*\>\Admin\WMI\Enumerate Receive Locations\VBScript\  
  
- VisualC#版本：\<*示例路径*\>\Admin\WMI\Enumerate Receive Locations\CSharp\  
  
  下表显示了本示例中的文件及其用途说明：  
  
|文件|Description|  
|---------------|-----------------|  
|\VBScript 文件夹的位置：<br /><br /> EnumRecLocs.vbs|检索有关所有已配置的详细信息的 VBScript 文件接收位置。|  
|\CSharp 文件夹的位置：<br /><br /> App.ico、 AssemblyInfo.cs、 BTSampleEnumerateRLs.csproj、 BTSampleEnumerateRLs.sln 和 EnumRLs.cs|项目、 解决方案和源文件构建的 Visual C# 命令行应用程序检索有关所有已配置的详细信息的接收位置，或有关特定接收位置。|  
  
## <a name="building-and-initializing-this-sample"></a>生成并初始化此示例  
 枚举接收位置示例的 VBScript 版本包括不需要生成或初始化的单一 Visual Basic 脚本文件。  
  
#### <a name="to-build-the-visual-c-version-of-the-enumerate-receive-locations-sample"></a>若要生成的枚举接收位置示例的 Visual C# 版本  
  
1. 在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，打开 BTSampleEnumerateRLs.sln 解决方案文件。  
  
2. 在中**构建**菜单上，单击**生成解决方案**。  
  
## <a name="running-this-sample"></a>运行本示例  
  
#### <a name="to-run-the-enumerate-receive-locations-sample"></a>若要运行枚举接收位置示例  
  
1.  在命令窗口中，导航到以下文件夹中，具体取决于是否要运行的 VBScript 版本还是 Visual C# 版本的此示例中，分别之一：  
  
     \<*示例路径*\>\Admin\WMI\Enumerate Receive Locations\VBScript\  
  
     \<*示例路径*\>\Admin\WMI\Enumerate Receive Locations\CSharp\bin\Debug\  
  
2.  运行文件使用 cscript 程序的哪一个，或运行文件 EnumRl.exe，具体取决于是否要运行的 VBScript 版本还是 Visual C# 版本的此示例中，分别。 对于 Visual C# 版本中，传递下列两个命令行参数之一：  
  
    -   **\<ReceiveLocationName\>。** 将显示其详细信息的接收位置的名称。 如果接收位置名称包含空格，将名称括起来。  
  
    -   **/?.** 显示帮助。  
  
         对于示例 (VBScript):  
  
        ```  
        cscript EnumRecLocs.vbs  
        ```  
  
         -或者-(Visual C#):  
  
        ```  
        EnumRl "My Receive Location #3"  
        ```  
  
         -或者-(Visual C#):  
  
        ```  
        EnumRl /?  
        ```  
  
    > [!NOTE]
    >  此示例的 VBScript 版本不接受任何命令行参数，因此仅检索和显示详细信息，有关配置的所有接收位置。  
  
## <a name="comments"></a>注释  
 可以在中执行的所有任务[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]通过使用访问 Windows WMI 对象模型的脚本，并通过使用 Visual C# 访问，也可以执行管理控制台**System.Management**提供对象由.NET Framework 中。  
  
 哪一个的脚本文件和 Visual C# 源代码文件 EnumRLs.cs 包含详细的注释了进一步说明他们执行的操作。 有关详细信息，请参阅在 Windows Management Instrumentation [ http://go.microsoft.com/fwlink/?LinkId=21102 ](http://go.microsoft.com/fwlink/?LinkId=21102)。  
  
## <a name="see-also"></a>请参阅  
 [Admin-WMI（BizTalk Server 示例文件夹）](../core/admin-wmi-biztalk-server-samples-folder.md)