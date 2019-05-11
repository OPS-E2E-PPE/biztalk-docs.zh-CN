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
ms.openlocfilehash: 5b43cba0be4bde3c019859b4783bbf1428d366a8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65352083"
---
# <a name="deploy-tibco-ems-ports-and-assemblies"></a>部署 TIBCO EMS 端口和程序集

## <a name="overview"></a>概述
使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，可以复制端口和目标计算机上的程序集。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 导出到 XML 文件发送端口/接收位置配置。  
  
 可以使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]来执行以下任务：  
  
- 部署或删除[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]BizTalk 配置数据库中的程序集。  
  
- 安装或卸载的程序集在全局程序集缓存 (GAC) 中。  
  
- 导入或导出 BizTalk 程序集绑定信息与绑定文件。  
  
  有关如何使用信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]若要部署端口和程序集，请参阅[如何导出 BizTalk 应用程序的绑定](../core/how-to-export-bindings-for-a-biztalk-application.md)。  
  
> [!NOTE]
>  用于 TIBCO Enterprise Message Service 的 Microsoft BizTalk 适配器只要求在源 （开发） 计算机上安装 Visual Studio。 Visual Studio 不需要在生产计算机上。  

## <a name="confirm-your-setup"></a>确认您的安装程序
使用 BizTalk Server 导入绑定文件之前，请验证以下：  
  
-   用于响应文件夹必须存在并在新计算机上完全相同或编辑绑定文件。  
  
-   TIBCO Enterprise Message Service 系统密码，如果存在在配置中，必须将另存为 * * * 绑定文件中。 请参阅**限制**本主题中。


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
传输适配器密码存储为星号 (\*\*\*\*\*\*) 在绑定文件中的已导出的 BizTalk Server 中，并且传递至中相同的管理组件格式。 星号替换为某些无效的值 （即，不正确的密码） 导入之前编辑绑定文件。 输入正确的密码使用**传输属性**导入绑定文件后在 BizTalk Server 管理控制台中的页。  
  
 这是已知的限制。 在导出绑定信息时，得到的绑定文件不包含任何传输所使用的密码中的适配器接收位置/发送端口。 这可以防止以明文形式显示密码信息。 下一次使用该文件导入绑定信息时，您必须使用传输属性页用户界面中输入的密码。 或者，暂时可以通过将密码输入到其导入前修改绑定文件。 在这种情况下，必须从绑定文件删除密码，在导入操作已成功完成后。  
  
 
### <a name="password-limitation-workaround"></a>密码限制的解决方法  
 若要解决此密码限制，可以使用以下方法之一：  
  
-   星号替换为纯文本导入之前编辑绑定文件。  
  
    > [!CAUTION]
    >  出于安全原因，这不被建议。  
  
-   星号替换为某些无效的值 （即，不正确的密码） 导入之前编辑绑定文件。 输入正确的密码使用**传输属性**导入绑定文件后在 BizTalk Server 管理控制台中的页。  
  
    > [!NOTE]
    >  这种解决可仅当目标计算机上安装 Visual Studio 或者您开发一个自定义工具。  
  
-   验证逻辑系统以及传输和接收服务。  

## <a name="next-steps"></a>后续步骤
[在您的业务流程中使用 BizTalk Server 异常处理](../core/using-biztalk-server-exception-handling5.md)