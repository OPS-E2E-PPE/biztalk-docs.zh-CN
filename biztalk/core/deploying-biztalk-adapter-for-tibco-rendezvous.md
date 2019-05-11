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
ms.openlocfilehash: 13f68268cc23255bb18128757b7ee879376572e9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390025"
---
# <a name="deploy-tibco-rendezvous-ports-and-assemblies"></a>部署 TIBCO Rendezvous 端口和程序集
  
## <a name="overview"></a>概述
使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，可以复制端口和目标计算机上的程序集。 向导导出的发送端口/接收位置配置为 XML 文件。  
  
 BizTalk Server 用于执行以下任务：  
  
- 部署或 BizTalk 配置数据库中删除 BizTalk Server 程序集。  
  
- 安装或卸载的程序集在全局程序集缓存 (GAC) 中。  
  
- 导入或导出 BizTalk Server 程序集绑定信息与绑定文件。  
  
  有关如何使用信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]若要部署端口和程序集，请参阅[如何导出 BizTalk 应用程序的绑定](../core/how-to-export-bindings-for-a-biztalk-application.md)。  
  
> [!NOTE]
>  用于 TIBCO Rendezvous 的 Microsoft BizTalk 适配器只要求在源 （开发） 计算机上安装 Visual Studio。 Visual Studio 不需要在生产计算机上。  

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