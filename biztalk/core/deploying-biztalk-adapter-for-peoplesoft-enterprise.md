---
title: 导入 PeopleSoft 应用程序 |Microsoft Docs
description: 使用 XML 绑定文件导入 BizTalk Server 的 PeopleSoft 适配器应用程序和导入时读取的任何限制
ms.custom: ''
ms.date: 10/19/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2f53d1b4-e1df-41ff-b554-1bb1d20b9111
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d7ca4d0ecbfdb23e35797eb2ba3a704fe19f4cec
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972710"
---
# <a name="deploy-biztalk-adapter-for-peoplesoft-enterprise"></a>部署用于 PeopleSoft Enterprise 的 BizTalk 适配器
本部分提供有关部署 PeopleSoft Enterprise 的 BizTalk 适配器的信息。  

## <a name="overview"></a>概述
使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，可在目标计算机上复制端口和程序集。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 导出的发送端口/接收位置配置为 XML 文件。  
  
 您可使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 执行下列任务：  
  
- 将 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 程序集部署到 BizTalk 配置数据库中或从其中删除。  
  
- 将程序集安装在全局程序集缓存 (GAC) 中或从其卸载。  
  
- 将 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 程序集绑定信息导入到绑定文件或从其中导出。  
  
若要使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]若要部署端口和程序集，请参阅[如何导出 BizTalk 应用程序的绑定](../core/how-to-export-bindings-for-a-biztalk-application.md)。  
  
> [!NOTE]
>  用于 PeopleSoft Enterprise 的 Microsoft BizTalk 适配器只要求在源 （开发） 计算机上具有 Visual Studio。 在生产计算机上不要求使用 Visual Studio。  

## <a name="confirm-your-setup"></a>确认您的安装程序
在使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 导入绑定文件之前，请验证以下各项：  
  
-   CLASSPATH 指向 PeopleSoft 特定文件的特定位置。 验证这些文件的位置，并在新计算机上相同，或编辑绑定文件。  
  
-   用于响应文件夹必须存在并且可在新计算机上完全相同，或编辑绑定文件。  
  
-   如果在配置中存在 PeopleSoft Enterprise 系统密码，则在绑定文件中另存为 *****。 请参阅**限制**本主题中。

> [!NOTE]
>  部署会覆盖接收位置配置。 如果在目标计算机上部署绑定文件和程序集，则发送端口和接收位置将替换为所导入的 XML 绑定文件中的发送端口和接收位置。  
  
 有关导入绑定文件的分步说明，请参阅[如何导入绑定到 BizTalk 组](../core/how-to-import-bindings-into-a-biztalk-group.md)。 
  
## <a name="clean-the-target-computer"></a>清理目标计算机
若要清理目标计算机部署新应用程序、 删除发送端口和接收位置绑定到业务流程。  
  
如果没有在目标计算机上安装 Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，则可通过运行下面的脚本删除端口：  
  
**\<Microsoft BizTalk Server\>\SDK\Samples\Admin\WMI\Remove 发送 Port\VBScript\RemoveSendPort.vbs**  
  
**\<Microsoft BizTalk Server\>\SDK\Samples\Admin\WMI\Remove 接收 Port\VBScript\RemoveReceivePort.vbs**  
  
例如，在命令提示符下运行：  
  
```
cscript RemoveSendPort.vbs \<Send port name\>
```

## <a name="limitations"></a>限制
传输适配器密码为星号 （*） 存储在绑定文件导出的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，并将其传递到相同的格式中的管理组件。  
  
 在导出绑定信息时，得到的绑定文件不包含传输适配器曾经在接收位置/发送端口中使用过的任何密码。 这样可防止以明文形式显示密码信息。 下一次使用该文件导入绑定信息时，必须使用传输属性页用户界面输入密码。 或者，可以在导入前临时修改绑定文件，将密码输入到文件中。 在这种情况下，必须在完成导入操作后从绑定文件中删除密码。  
  

### <a name="work-around-the-password-limitation"></a>解决此密码限制  

**选项 1**   
  
- 在导入之前，请通过将星号替换纯文本更新绑定文件。  
  
  > [!CAUTION]
  >  出于安全考虑，不建议使用此方法。  
  
- 在导入之前，更新绑定 fileby 将星号替换某些无效的值 （即，不正确的密码）。 在导入后，输入在正确的密码**传输属性**BizTalk Server 管理中。  
  
  > [!NOTE]
  >  只有当目标计算机上安装了 Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 或者您开发了一个自定义工具时，才能使用这种解决方法。  
  
**选项 2**  
  
-   使用企业单一登录 (SSO) 而不是使用密码。 使用 SSO 选项时需要导入绑定文件。  
  
- 验证逻辑系统以及传输和接收服务。 
  
## <a name="next-steps"></a>后续步骤
[在您的业务流程中使用 BizTalk Server 异常处理](../core/using-biztalk-server-exception-handling2.md)