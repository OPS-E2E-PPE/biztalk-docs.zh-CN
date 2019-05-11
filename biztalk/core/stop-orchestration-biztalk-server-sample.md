---
title: 停止业务流程 （BizTalk Server 示例） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, examples
- examples, orchestrations
- orchestrations, stopping
ms.assetid: 83be44e9-819d-4ac5-8b75-84c23e6b5ba2
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c5f6294442311f2644f6f0bc7efd2261af7712c1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65244160"
---
# <a name="stop-orchestration-biztalk-server-sample"></a>停止业务流程 （BizTalk Server 示例）
停止业务流程示例演示如何停止 BizTalk Server 业务流程和 （可选） 若要取消登记它。  
  
> [!WARNING]
>  如果不需要应在部署后删除的部署脚本。 管理脚本和其他必须保持的脚本应受 ACL 并加以密切监视。  
  
## <a name="what-this-sample-does"></a>本示例的用途  
 构成本示例的脚本文件中的 Visual Basic Scripting Edition (VBScript) 脚本演示如何执行以下操作，使用 BizTalk Server WMI 提供程序：  
  
-   给定的业务流程名称和程序集名称，查询的特定部署 BizTalk Server 业务流程。  
  
-   停止此业务流程。  
  
-   （可选） 取消登记该业务流程。  
  
-   处理任何错误，以便向用户返回有意义的信息。  
  
## <a name="where-to-find-this-sample"></a>本示例所在的位置  
 示例文件位于以下 SDK 位置：  
  
 \<*Samples Path*\>\Admin\WMI\Stop Orchestration\  
  
 下表显示了本示例中的文件及其用途说明：  
  
|文件|Description|  
|---------------|-----------------|  
|\VBScript 文件夹的位置：<br /><br /> StopOrch.vbs|采用参数指定要停止的和选择取消登记业务流程的 VBScript 文件。|  
  
## <a name="building-and-initializing-this-sample"></a>生成并初始化此示例  
 停止业务流程示例由一个不需要生成或初始化的 VBScript 文件组成。  
  
## <a name="running-this-sample"></a>运行本示例  
  
#### <a name="to-run-this-sample"></a>运行本示例的步骤  
  
1.  在命令窗口中，导航到以下文件夹：  
  
     \<*Samples Path*\>\Admin\WMI\Stop Orchestration\VBScript\  
  
2.  运行 StopOrch.vbs 使用 cscript 程序中，传递下列命令行参数，第三个是可选的文件：  
  
    -   **\<** ***OrchestrationName* \>.** BizTalk Server 业务流程要停止的和选择取消登记的名称。  
  
    -   **\<** ***AssemblyName* \>.** 在其中部署指定业务流程的 BizTalk 程序集的名称。 如果程序集名称包含空格，将名称括起来。  
  
    -   **取消登记。** 用于指示指定的业务流程应在除正在停止已取消登记可选的文本字符串。  
  
         例如：  
  
        ```  
        cscript StopOrch.vbs MyBusinessOrchestration "My Business Assembly"  
        ```  
  
         -或-  
  
        ```  
        cscript StopOrch.vbs MyBusinessOrchestration MyBusinessAssembly Unenlist  
        ```  
  
## <a name="comments"></a>注释  
 可以在 BizTalk Server 管理控制台中执行的所有任务也可以通过使用访问 Windows WMI 对象模型的脚本都执行。  
  
 StopOrch.vbs 脚本文件包含详细的注释了进一步说明，它执行的操作。 有关详细信息，请参阅在 Windows Management Instrumentation [ http://go.microsoft.com/fwlink/?LinkId=21102 ](http://go.microsoft.com/fwlink/?LinkId=21102)。  
  
## <a name="see-also"></a>请参阅  
 [Admin-WMI（BizTalk Server 示例文件夹）](../core/admin-wmi-biztalk-server-samples-folder.md)