---
title: 导入绑定 TIBCO EMS |Microsoft 文档
description: 部署你的 BizTalk Adapter TIBCO 企业消息服务应用程序在 BizTalk Server 中使用导入绑定功能
ms.custom: ''
ms.date: 10/23/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 69dae448-4ec6-4a56-a628-bb447bc21b62
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 79f7f3ec0478746b8c2c6762fe212229f9c7b11d
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-tibco-ems-ports-and-assemblies"></a>部署 TIBCO EMS 端口和程序集

## <a name="overview"></a>概述
与[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，你可以复制端口和目标计算机上的程序集。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 导出到 XML 文件发送/接收端口的位置配置。  
  
 使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 可以执行以下任务：  
  
-   将 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 程序集部署到 BizTalk 配置数据库中或从其中删除。  
  
-   将程序集安装在全局程序集缓存 (GAC) 中或从其卸载。  
  
-   将 BizTalk 程序集绑定信息导入到绑定文件或从中导出。  
  
 有关如何使用信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]若要部署的端口和程序集，请参阅[如何导出 BizTalk 应用程序的绑定](../core/how-to-export-bindings-for-a-biztalk-application.md)。  
  
> [!NOTE]
>  用于 TIBCO Enterprise Message Service 的 Microsoft BizTalk 适配器只要求在源（开发）计算机上装有 Visual Studio。 在生产计算机上不要求使用 Visual Studio。  

## <a name="confirm-your-setup"></a>确认你的设置
在使用 BizTalk Server 导入绑定文件之前，请验证以下各项：  
  
-   用于响应的文件夹必须存在，并且在新计算机上必须相同；否则编辑绑定文件。  
  
-   如果在配置中存在 TIBCO Enterprise Message Service 系统密码，则必须在绑定文件中另存为 *****。 请参阅**限制**本主题中。


## <a name="clean-the-target-computer"></a>清除目标计算机中的
部署将覆盖接收位置配置。 当你部署的目标计算机上，发送端口的绑定文件 （和程序集） 和接收位置已替换为 XML 绑定文件中导入时。  

在导入之前，删除任何发送端口和接收位置绑定到业务流程。  
  
如果你没有在目标计算机上安装的 Microsoft Visual Studio，你可以通过运行这些脚本中删除的端口︰  
  
`\<Microsoft BizTalk Server\>\SDK\Samples\Admin\WMI\Remove Send Port\VBScript\RemoveSendPort.vbs`  
  
`\<Microsoft BizTalk Server\>\SDK\Samples\Admin\WMI\Remove Receive Port\VBScript\RemoveReceivePort.vbs`
  

例如，在命令提示符下运行：  
  
```
cscript RemoveSendPort.vbs \<Send port name\>
```

## <a name="limitations"></a>限制
传输适配器密码存储为星号 (\*\*\*\*\*\*) 在绑定文件中，将导出由 BizTalk Server 中，并将其传递到相同的格式中的管理组件。 在导入之前编辑绑定文件，将星号替换为某些无效的值（即，不替换为正确密码）。 输入正确的密码使用 **传输属性** 在 BizTalk Server 管理控制台中导入的绑定文件后的页。  
  
 这是一项已知的缺限。 在导出绑定信息时，得到的绑定文件不包含传输适配器曾经在接收位置/发送端口中使用过的任何密码。 这样可防止以明文形式显示密码信息。 下一次使用该文件导入绑定信息时，必须使用传输属性页用户界面输入密码。 或者，可以在导入前临时修改绑定文件，将密码输入到文件中。 在这种情况下，必须在成功完成导入操作后从绑定文件中删除密码。  
  
 
### <a name="password-limitation-workaround"></a>密碼限制解決方法  
 若要解决此密码限制问题，可使用以下方法之一：  
  
-   在导入之前编辑绑定文件，将星号替换为明文密码。  
  
    > [!CAUTION]
    >  出于安全考虑，这不被建议。  
  
-   在导入之前编辑绑定文件，将星号替换为某些无效的值（即，不替换为正确密码）。 输入正确的密码使用 **传输属性** 在 BizTalk Server 管理控制台中导入的绑定文件后的页。  
  
    > [!NOTE]
    >  只有当目标计算机上安装了 Visual Studio 或者您开发了一个自定义工具时，才能使用这种解决方法。  
  
-   驗證邏輯系統以及「傳輸」和「接收」服務。  

## <a name="next-steps"></a>后续步骤
[使用 BizTalk Server 中的异常处理您的业务流程](../core/using-biztalk-server-exception-handling5.md)