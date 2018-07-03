---
title: 用于 TIBCO EMS 将绑定导入 |Microsoft Docs
description: 部署用于 TIBCO Enterprise Message Service 应用程序在 BizTalk Server 中使用导入绑定功能在 BizTalk 适配器
ms.custom: ''
ms.date: 10/23/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 69dae448-4ec6-4a56-a628-bb447bc21b62
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e90d083833e7961770c6ecd535e9ed3e5143be30
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981358"
---
# <a name="deploy-tibco-ems-ports-and-assemblies"></a>部署 TIBCO EMS 端口和程序集

## <a name="overview"></a>概述
使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，可以复制端口和目标计算机上的程序集。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 导出到 XML 文件发送端口/接收位置配置。  
  
 使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 可以执行以下任务：  
  
- 将 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 程序集部署到 BizTalk 配置数据库中或从其中删除。  
  
- 将程序集安装在全局程序集缓存 (GAC) 中或从其卸载。  
  
- 将 BizTalk 程序集绑定信息导入到绑定文件或从中导出。  
  
  有关如何使用信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]若要部署端口和程序集，请参阅[如何导出 BizTalk 应用程序的绑定](../core/how-to-export-bindings-for-a-biztalk-application.md)。  
  
> [!NOTE]
>  用于 TIBCO Enterprise Message Service 的 Microsoft BizTalk 适配器只要求在源（开发）计算机上装有 Visual Studio。 在生产计算机上不要求使用 Visual Studio。  

## <a name="confirm-your-setup"></a>确认您的安装程序
在使用 BizTalk Server 导入绑定文件之前，请验证以下各项：  
  
-   用于响应的文件夹必须存在，并且在新计算机上必须相同；否则编辑绑定文件。  
  
-   如果在配置中存在 TIBCO Enterprise Message Service 系统密码，则必须在绑定文件中另存为 *****。 请参阅**限制**本主题中。


## <a name="clean-the-target-computer"></a>清理目标计算机
部署会覆盖接收位置配置。 当将绑定文件 （和程序集） 部署的目标计算机上，发送端口和接收位置将替换 XML 绑定文件中所导入。  

在导入之前，删除任何发送端口和接收位置绑定到业务流程。  
  
如果没有在目标计算机上安装 Microsoft Visual Studio，则可以通过运行这些脚本删除端口：  
  
`\<Microsoft BizTalk Server\>\SDK\Samples\Admin\WMI\Remove Send Port\VBScript\RemoveSendPort.vbs`  
  
`\<Microsoft BizTalk Server\>\SDK\Samples\Admin\WMI\Remove Receive Port\VBScript\RemoveReceivePort.vbs`
  

例如，在命令提示符下运行：  
  
```
cscript RemoveSendPort.vbs \<Send port name\>
```

## <a name="limitations"></a>限制
传输适配器密码存储为星号 (\*\*\*\*\*\*) 在绑定文件中的已导出的 BizTalk Server 中，并且传递至中相同的管理组件格式。 在导入之前编辑绑定文件，将星号替换为某些无效的值（即，不替换为正确密码）。 输入正确的密码使用**传输属性**导入绑定文件后在 BizTalk Server 管理控制台中的页。  
  
 这是一项已知的缺限。 在导出绑定信息时，得到的绑定文件不包含传输适配器曾经在接收位置/发送端口中使用过的任何密码。 这样可防止以明文形式显示密码信息。 下一次使用该文件导入绑定信息时，必须使用传输属性页用户界面输入密码。 或者，可以在导入前临时修改绑定文件，将密码输入到文件中。 在这种情况下，必须在成功完成导入操作后从绑定文件中删除密码。  
  
 
### <a name="password-limitation-workaround"></a>密码限制的解决方法  
 若要解决此密码限制问题，可使用以下方法之一：  
  
-   在导入之前编辑绑定文件，将星号替换为明文密码。  
  
    > [!CAUTION]
    >  出于安全原因，这不被建议。  
  
-   在导入之前编辑绑定文件，将星号替换为某些无效的值（即，不替换为正确密码）。 输入正确的密码使用**传输属性**导入绑定文件后在 BizTalk Server 管理控制台中的页。  
  
    > [!NOTE]
    >  只有当目标计算机上安装了 Visual Studio 或者您开发了一个自定义工具时，才能使用这种解决方法。  
  
-   验证逻辑系统以及传输和接收服务。  

## <a name="next-steps"></a>后续步骤
[在您的业务流程中使用 BizTalk Server 异常处理](../core/using-biztalk-server-exception-handling5.md)