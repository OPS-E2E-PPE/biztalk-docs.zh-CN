---
title: 用于 JD Edwards OneWorld 导入 BizTalk 适配器 |Microsoft Docs
description: 导入应用程序绑定文件，并查看 JD Edwards OneWorld 适配器在 BizTalk 中的任何限制。
ms.custom: ''
ms.date: 10/18/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f308d2fe-39dd-4008-94ed-292c4c26fe06
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9ca65c71e14d488b264d861616fe170220ac249b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999214"
---
# <a name="import-the-jd-edwards-enterpriseone-application"></a>JD Edwards EnterpriseOne 应用程序导入
  
## <a name="overview"></a>概述
使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，可在目标计算机上复制端口和程序集。 BizTalk Server 将发送端口/接收位置配置导出到一个 XML 文件中。  
  
 BizTalk Server 可用于执行以下任务：  
  
-   将 BizTalk Server 程序集部署到 BizTalk 配置数据库或从其删除  
  
-   将程序集安装在全局程序集缓存 (GAC) 中或从其卸载  
  
-   将 BizTalk Server 程序集绑定信息导入到绑定文件或从其导出  

若要使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]若要部署端口和程序集，请参阅[如何导出 BizTalk 应用程序的绑定](../core/how-to-export-bindings-for-a-biztalk-application.md)。  
  
> [!NOTE]
>  JD Edwards OneWorld 的 Microsoft BizTalk 适配器只要求在源（开发）计算机上具有 Visual Studio。 在生产计算机上不要求使用 Visual Studio。  

## <a name="confirm-your-setup"></a>确认您的安装程序
使用 BizTalk Server 导入绑定文件之前，请验证以下：  
  
-   CLASSPATH 指向 JD Edwards 特定文件的特定位置。 验证在新计算机上这些文件的位置是否相同，否则编辑绑定文件。  
  
-   用于响应的文件夹存在，并且在新计算机上相同，否则编辑绑定文件。  
  
-   如果在配置中存在 JD Edwards 系统密码，则在绑定文件中另存为 *****。 请参阅**限制**本主题中。

  
> [!NOTE]
>  部署会覆盖接收位置配置。 如果在目标计算机上部署绑定文件（和程序集），则发送端口和接收位置将替换为所导入的 XML 绑定文件中的发送端口和接收位置。  
  
  
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
  
## <a name="limitations"></a>限制
传输适配器密码存储为星号 (\*\*\*\*\*\*) 中的绑定文件导出的 BizTalk 部署向导，并传递到管理相同的格式中的组件。 在导入之前编辑绑定文件，将星号替换为随机的字母数字值（即，不替换为正确密码）。 然后输入正确的密码使用**传输属性**导入绑定文件后的页。  
  
 在导出绑定信息时，得到的绑定文件不包含传输适配器曾经在接收位置/发送端口中使用过的任何密码。 这样可防止以明文形式显示密码信息。 下次使用该文件导入绑定信息时，你必须使用传输属性页用户界面中输入的密码。 或者，可以在导入前临时修改绑定文件，将密码输入到文件中。 在这种情况下，你必须删除密码从绑定文件导入操作已成功完成后。  
  
> [!NOTE]
>  将 .msi 文件导入包含任何企业适配器的绑定信息的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 应用程序时，您可能会收到一条导入错误消息。 支持的修补程序是 Microsoft 提供的以及在错误的完整说明[ http://support.microsoft.com/kb/923733/en-us ](http://support.microsoft.com/kb/923733/en-us)。  
  
### <a name="work-around-the-password-limitation"></a>解决此密码限制  

**选项 1**  

- 在导入之前，请通过将星号替换纯文本更新绑定文件。  
  
    > [!CAUTION]
    >  出于安全原因，这不被建议。  
  
- 在导入之前，通过将星号替换某些无效的值 （即，不正确的密码） 来更新绑定文件。 导入后，请输入正确的密码使用**传输属性**。  
  
    > [!NOTE]
    >  只有当目标计算机上安装了 Microsoft Visual Studio 或者开发一个自定义工具，才能使用这种解决方法。  
  
**选项 2**  
  
1.  使用企业单一登录，而不是使用密码。 使用 SSO 选项需要任何额外操作;仅导入绑定文件。  
  
2.  验证逻辑系统以及传输和接收服务。  

## <a name="next-steps"></a>后续步骤
[在您的业务流程中使用 BizTalk Server 异常处理](../core/using-biztalk-server-exception-handling1.md)