---
title: 导入 JD Edwards EnterpriseOne 应用程序 |Microsoft Docs
description: 确认设置，导入应用程序绑定文件，并查看 JD Edwards EnterpriseOne 适配器在 BizTalk 中的限制
ms.custom: ''
ms.date: 10/18/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 852f948b-48ba-4ae2-b1eb-7c88c1542a52
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 708e9d3513c9d36e9a4aa28d607332e4c1aac077
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989366"
---
# <a name="import-the-jd-edwards-enterpriseone-application"></a>JD Edwards EnterpriseOne 应用程序导入
  
## <a name="overview"></a>概述
使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，可以复制端口和目标计算机上的程序集。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 导出的发送端口/接收位置配置为 XML 文件。  
  
 使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 可以执行以下任务：  
  
- 将 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 程序集部署到 BizTalk 配置数据库中或从其删除  
  
- 将程序集安装在全局程序集缓存 (GAC) 中或从其卸载  
  
- 将 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 程序集绑定信息导入到绑定文件或从其导出  
  
若要使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]若要部署端口和程序集，请参阅[如何导出 BizTalk 应用程序的绑定](../core/how-to-export-bindings-for-a-biztalk-application.md)。  
  
> [!NOTE]
>  用于 JD Edwards EnterpriseOne 的 Microsoft BizTalk 适配器只要求在源（开发）计算机上具有 Visual Studio。 在生产计算机上不要求使用 Visual Studio。  

## <a name="confirm-your-setup"></a>确认您的安装程序
在使用 BizTalk Server 导入绑定文件之前，必须验证以下各项：  
  
-   CLASSPATH 指向特定于 JD Edwards EnterpriseOne 文件的特定位置。 验证在新计算机上这些文件的位置是否相同，否则编辑绑定文件。  
  
-   用于响应的文件夹存在，并且在新计算机上相同，否则编辑绑定文件。  
  
-   如果在配置中存在 JD Edwards EnterpriseOne 系统密码，则在绑定文件中另存为 *****。 有关详细信息，请参阅**限制**本主题中。

## <a name="clean-the-target-computer"></a>清理目标计算机
当重新绑定文件 （和程序集） 部署的目标计算机上，发送端口和接收位置将替换中的 XML 绑定文件时它们重新导入。  
  
在导入之前，删除发送端口和接收位置绑定到业务流程。 如果未安装目标计算机上安装的 Visual Studio，则可以通过运行脚本删除端口：  
  
- [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\Admin\WMI\Remove Send Port\VBScript\RemoveSendPort.vbs  
  
- [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\Admin\WMI\Remove Receive Port\VBScript\RemoveReceivePort.vbs  

例如，从命令提示符下运行：  
  
```
cscript RemoveSendPort.vbs \<Send port name\>
```
## <a name="limitations"></a>限制
传输适配器密码在导出的绑定文件中存储为星号 （*） [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，并将其传递到相同的格式中的管理组件。 在导入之前编辑绑定文件，将星号替换为某些无效的值（即，不替换为正确密码）。  
  
 在导出绑定信息时，得到的绑定文件不包含传输适配器曾经在接收位置/发送端口中使用过的任何密码。 这样可防止以明文形式显示密码信息。 下次使用该文件导入绑定信息时，你必须使用传输属性页用户界面中输入的密码。  
  
 或者，可以在导入前临时修改绑定文件，将密码输入到文件中。 在这种情况下，你必须删除密码从绑定文件导入操作已成功完成后。  
  
### <a name="work-around-the-password-limitation"></a>解决此密码限制  
  
1.  使用企业单一登录，而不是使用密码。 使用 SSO 选项需要任何额外操作;仅导入绑定文件。  
  
2.  验证逻辑系统以及传输和接收服务。  


## <a name="next-steps"></a>后续步骤
[在您的业务流程中使用 BizTalk Server 异常处理](../core/using-biztalk-server-exception-handling3.md)