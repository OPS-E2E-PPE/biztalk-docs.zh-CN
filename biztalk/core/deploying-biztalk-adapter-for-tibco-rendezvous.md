---
title: 用于 TIBCO Rendezvous 将绑定导入 |Microsoft Docs
description: 部署 TIBCO Rendezvous 应用程序在 BizTalk Server 中使用导入绑定功能的 BizTalk 适配器
ms.custom: ''
ms.date: 10/24/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ec5751a9-0a08-4cf8-a3ef-e51e488a4180
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2bb362afb23b165c31df34adf521be81f93a621f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994006"
---
# <a name="deploy-tibco-rendezvous-ports-and-assemblies"></a>部署 TIBCO Rendezvous 端口和程序集
  
## <a name="overview"></a>概述
使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，可在目标计算机上复制端口和程序集。 该向导将发送端口/接收位置配置导出到一个 XML 文件中。  
  
 您可以使用 BizTalk Server 来执行以下任务：  
  
- 将 BizTalk Server 程序集部署到 BizTalk 配置数据库中或从其删除。  
  
- 将程序集安装在全局程序集缓存 (GAC) 中或从其卸载。  
  
- 将 BizTalk Server 程序集绑定信息导入到绑定文件或从其导出。  
  
  有关如何使用信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]若要部署端口和程序集，请参阅[如何导出 BizTalk 应用程序的绑定](../core/how-to-export-bindings-for-a-biztalk-application.md)。  
  
> [!NOTE]
>  TIBCO Rendezvous 的 Microsoft BizTalk 适配器只要求在源（开发）计算机上具有 Visual Studio。 在生产计算机上不要求使用 Visual Studio。  

## <a name="confirm-your-setup"></a>确认您的安装程序

在使用之前[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]若要导入绑定文件，请确认，用于响应文件夹存在，并且它们是相同的新计算机上，或必须编辑绑定文件。  
  
## <a name="clean-the-target-computer"></a>清理目标计算机
部署会覆盖接收位置配置。 当将绑定文件 （和程序集） 部署的目标计算机上，发送端口和接收位置将替换 XML 绑定文件中所导入。  
  
在导入之前，删除发送端口和接收位置绑定到业务流程。  
  
如果没有在目标计算机上安装 Microsoft Visual Studio，则可以通过运行这些脚本删除端口：  
  
- [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\Admin\WMI\Remove Send Port\VBScript\RemoveSendPort.vbs  
  
- [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\Admin\WMI\Remove Receive Port\VBScript\RemoveReceivePort.vbs  
  
例如，在命令提示符下运行：  
  
```
cscript RemoveSendPort.vbs \<Send port name\>
```
  
## <a name="next-steps"></a>后续步骤
[在您的业务流程中使用 BizTalk Server 异常处理](../core/using-biztalk-server-exception-handling4.md)  
[故障排除](../core/troubleshooting-tibco-rendezvous.md)