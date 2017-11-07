---
title: "导入绑定 TIBCO 会合 |Microsoft 文档"
description: "部署你的 BizTalk Adapter TIBCO 会合应用程序在 BizTalk Server 中使用导入绑定功能"
ms.custom: 
ms.date: 10/24/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ec5751a9-0a08-4cf8-a3ef-e51e488a4180
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e880bcbce388bb15924e96739c8bb617c04d0e24
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2017
---
# <a name="deploy-tibco-rendezvous-ports-and-assemblies"></a>部署 TIBCO 会合端口和程序集
  
## <a name="overview"></a>概述
使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，可在目标计算机上复制端口和程序集。 该向导将发送端口/接收位置配置导出到一个 XML 文件中。  
  
 您可以使用 BizTalk Server 来执行以下任务：  
  
-   将 BizTalk Server 程序集部署到 BizTalk 配置数据库中或从其删除。  
  
-   将程序集安装在全局程序集缓存 (GAC) 中或从其卸载。  
  
-   将 BizTalk Server 程序集绑定信息导入到绑定文件或从其导出。  
  
 有关如何使用信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]若要部署的端口和程序集，请参阅[如何导出 BizTalk 应用程序的绑定](../core/how-to-export-bindings-for-a-biztalk-application.md)。  
  
> [!NOTE]
>  TIBCO Rendezvous 的 Microsoft BizTalk 适配器只要求在源（开发）计算机上具有 Visual Studio。 在生产计算机上不要求使用 Visual Studio。  

## <a name="confirm-your-setup"></a>确认你的设置

在使用之前[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]要导入绑定文件，确认是否响应的文件夹存在，以及它们是相同的新计算机上，或你必须编辑绑定文件。  
  
## <a name="clean-the-target-computer"></a>清除目标计算机中的
部署将覆盖接收位置配置。 当你部署的目标计算机上，发送端口的绑定文件 （和程序集） 和接收位置已替换为 XML 绑定文件中导入时。  
  
在导入之前，删除发送端口和接收位置绑定到业务流程。  
  
如果你没有在目标计算机上安装的 Microsoft Visual Studio，你可以通过运行这些脚本中删除的端口：  
  
-   [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\Admin\WMI\Remove Send Port\VBScript\RemoveSendPort.vbs  
  
-   [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\Admin\WMI\Remove Receive Port\VBScript\RemoveReceivePort.vbs  
  
例如，在命令提示符下运行：  
  
```
cscript RemoveSendPort.vbs \<Send port name>
```
  
## <a name="next-steps"></a>后续步骤
[使用 BizTalk Server 中的异常处理您的业务流程](../core/using-biztalk-server-exception-handling4.md)  
[故障排除](../core/troubleshooting-tibco-rendezvous.md)