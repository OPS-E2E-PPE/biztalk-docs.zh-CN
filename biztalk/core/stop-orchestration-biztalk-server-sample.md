---
title: "停止业务流程 （BizTalk Server 示例） |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- orchestrations, examples
- examples, orchestrations
- orchestrations, stopping
ms.assetid: 83be44e9-819d-4ac5-8b75-84c23e6b5ba2
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e8ce53882b20f6615ef280a38eddc8c3e2ef7ea3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="stop-orchestration-biztalk-server-sample"></a>停止业务流程 （BizTalk Server 示例）
停止业务流程示例演示如何停止 BizTalk Server 业务流程和对其取消登记，后者可选。  
  
> [!WARNING]
>  部署后，如果不再需要部署脚本，则应将其删除。 应通过 ACL 确保必须保留的管理脚本和其他脚本的安全并加以密切监视。  
  
## <a name="what-this-sample-does"></a>本示例的用途  
 构成本示例的脚本文件中的 Visual Basic Scripting Edition (VBScript) 脚本演示如何使用 BizTalk Server WMI 提供程序执行下列操作：  
  
-   根据给定的业务流程名称和程序集名称，查询部署的特定 BizTalk Server 业务流程。  
  
-   停止此业务流程。  
  
-   取消登记此业务流程（可选）。  
  
-   处理所有错误，以便向用户返回有意义的信息。  
  
## <a name="where-to-find-this-sample"></a>本示例所在的位置  
 本示例文件位于以下 SDK 位置：  
  
 \<*示例路径*> \Admin\WMI\Stop Orchestration\  
  
 下表显示了本示例中的文件及其用途说明：  
  
|文件|Description|  
|---------------|-----------------|  
|\VBScript 文件夹的内容：<br /><br /> StopOrch.vbs|VBScript 文件，采用参数指定要停止的和选择取消登记的业务流程。|  
  
## <a name="building-and-initializing-this-sample"></a>生成并初始化此示例  
 停止业务流程示例由一个 VBScript 文件组成，您无需生成或初始化此文件。  
  
## <a name="running-this-sample"></a>运行本示例  
  
#### <a name="to-run-this-sample"></a>运行本示例的步骤  
  
1.  在命令窗口中，导航到下面的文件夹：  
  
     \<*示例路径*> \Admin\WMI\Stop Orchestration\VBScript\  
  
2.  使用 cscript 程序运行 StopOrch.vbs 文件，传递下列命令行参数，其中第三个参数是可选的：  
  
    -   **\<**   
         ***OrchestrationName* >。** 要停止的和选择取消登记的 BizTalk Server 业务流程的名称。  
  
    -   **\<**   
         ***AssemblyName* >。** 在其中部署指定业务流程的 BizTalk 程序集的名称。 如果程序集名称包含空格，则将该名称置于引号中。  
  
    -   **取消登记。** 用于指示除停止指定业务流程外还应取消登记该业务流程的可选文本字符串。  
  
         例如：  
  
        ```  
        cscript StopOrch.vbs MyBusinessOrchestration "My Business Assembly"  
        ```  
  
         -或者-  
  
        ```  
        cscript StopOrch.vbs MyBusinessOrchestration MyBusinessAssembly Unenlist  
        ```  
  
## <a name="comments"></a>注释  
 在 BizTalk Server 管理控制台中可执行的所有任务也可通过使用访问 Windows WMI 对象模型的脚本来执行。  
  
 StopOrch.vbs 脚本文件包含详细注释，对其执行的操作进行进一步说明。 有关详细信息，请参阅在 Windows Management Instrumentation [http://go.microsoft.com/fwlink/?LinkId=21102](http://go.microsoft.com/fwlink/?LinkId=21102)。  
  
## <a name="see-also"></a>另请参阅  
 [管理员-WMI （BizTalk Server 示例文件夹中）](../core/admin-wmi-biztalk-server-samples-folder.md)