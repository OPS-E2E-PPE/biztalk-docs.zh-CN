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
ms.openlocfilehash: b84730a5f88b36897114fb068b0d2ebbabf3f717
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65352134"
---
# <a name="import-the-jd-edwards-enterpriseone-application"></a>JD Edwards EnterpriseOne 应用程序导入
  
## <a name="overview"></a>概述
使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，可以复制端口和目标计算机上的程序集。 BizTalk Server 发送端口/接收位置将配置导出到 XML 文件。  
  
 BizTalk Server 可用于执行以下任务：  
  
-   部署或 BizTalk 配置数据库中删除 BizTalk Server 程序集  
  
-   安装或卸载的全局程序集缓存 (GAC) 中的程序集  
  
-   导入或导出 BizTalk Server 程序集绑定信息与绑定文件  

若要使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]若要部署端口和程序集，请参阅[如何导出 BizTalk 应用程序的绑定](../core/how-to-export-bindings-for-a-biztalk-application.md)。  
  
> [!NOTE]
>  用于 JD Edwards OneWorld 的 Microsoft BizTalk 适配器只要求在源 （开发） 计算机上具有 Visual Studio。 Visual Studio 不需要在生产计算机上。  

## <a name="confirm-your-setup"></a>确认您的安装程序
使用 BizTalk Server 导入绑定文件之前，请验证以下：  
  
-   CLASSPATH 指向 JD Edwards 特定文件的特定位置。 验证这些文件的位置是相同的新计算机上，或编辑绑定文件。  
  
-   用于响应文件夹存在并在新计算机上完全相同或编辑绑定文件。  
  
-   JD Edwards 系统密码，如果存在在配置中，将保存为 * * * 绑定文件中。 请参阅**限制**本主题中。

  
> [!NOTE]
>  部署会覆盖接收位置配置。 在目标计算机上部署绑定文件 （和程序集），发送端口和接收位置将替换 XML 绑定文件中导入它们。  
  
  
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
传输适配器密码存储为星号 (\*\*\*\*\*\*) 中的绑定文件导出的 BizTalk 部署向导，并传递到管理相同的格式中的组件。 将星号替换随机字母数字值 （即，不正确的密码） 导入之前编辑绑定文件。 然后输入正确的密码使用**传输属性**导入绑定文件后的页。  
  
 在导出绑定信息时，得到的绑定文件不包含任何传输所使用的密码中的适配器接收位置/发送端口。 这可以防止以明文形式显示密码信息。 下次使用该文件导入绑定信息时，你必须使用传输属性页用户界面中输入的密码。 或者，暂时可以通过将密码输入到其导入前修改绑定文件。 在这种情况下，你必须删除密码从绑定文件导入操作已成功完成后。  
  
> [!NOTE]
>  导入到某一.msi 文件时[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]包含针对任何企业适配器的绑定信息的应用程序可能会收到导入错误消息。 支持的修补程序是 Microsoft 提供的以及在错误的完整说明[ http://support.microsoft.com/kb/923733/en-us ](http://support.microsoft.com/kb/923733/en-us)。  
  
### <a name="work-around-the-password-limitation"></a>解决此密码限制  

**选项 1**  

- 在导入之前，请通过将星号替换纯文本更新绑定文件。  
  
    > [!CAUTION]
    >  出于安全原因，这不被建议。  
  
- 在导入之前，通过将星号替换某些无效的值 （即，不正确的密码） 来更新绑定文件。 导入后，请输入正确的密码使用**传输属性**。  
  
    > [!NOTE]
    >  这种解决可仅当目标计算机上或通过开发一个自定义工具来安装 Microsoft Visual Studio。  
  
**选项 2**  
  
1.  使用企业单一登录，而不是使用密码。 使用 SSO 选项需要任何额外操作;仅导入绑定文件。  
  
2.  验证逻辑系统以及传输和接收服务。  

## <a name="next-steps"></a>后续步骤
[在您的业务流程中使用 BizTalk Server 异常处理](../core/using-biztalk-server-exception-handling1.md)