---
title: 为博士 Edwards OneWorld 导入的 BizTalk Adapter |Microsoft 文档
description: 导入应用程序绑定文件，并查看博士 Edwards OneWorld 适配器在 BizTalk 任何限制
ms.custom: ''
ms.date: 10/18/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f308d2fe-39dd-4008-94ed-292c4c26fe06
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d4a452d61b3bdb5f5d0fee9e0916811645938d70
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="import-the-jd-edwards-enterpriseone-application"></a>导入博士 Edwards EnterpriseOne 应用程序
  
## <a name="overview"></a>概述
使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，可在目标计算机上复制端口和程序集。 BizTalk Server 将发送端口/接收位置配置导出到一个 XML 文件中。  
  
 BizTalk Server 可用于执行以下任务︰  
  
-   将 BizTalk Server 程序集部署到 BizTalk 配置数据库或从其删除  
  
-   将程序集安装在全局程序集缓存 (GAC) 中或从其卸载  
  
-   将 BizTalk Server 程序集绑定信息导入到绑定文件或从其导出  

若要使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]若要部署的端口和程序集，请参阅[如何导出 BizTalk 应用程序的绑定](../core/how-to-export-bindings-for-a-biztalk-application.md)。  
  
> [!NOTE]
>  JD Edwards OneWorld 的 Microsoft BizTalk 适配器只要求在源（开发）计算机上具有 Visual Studio。 在生产计算机上不要求使用 Visual Studio。  

## <a name="confirm-your-setup"></a>确认你的设置
BizTalk Server 用于导入绑定文件之前，请验证以下各项︰  
  
-   CLASSPATH 指向 JD Edwards 特定文件的特定位置。 验证在新计算机上这些文件的位置是否相同，否则编辑绑定文件。  
  
-   用于响应的文件夹存在，并且在新计算机上相同，否则编辑绑定文件。  
  
-   如果在配置中存在 JD Edwards 系统密码，则在绑定文件中另存为 *****。 请参阅**限制**本主题中。

  
> [!NOTE]
>  部署将覆盖接收位置配置。 如果在目标计算机上部署绑定文件（和程序集），则发送端口和接收位置将替换为所导入的 XML 绑定文件中的发送端口和接收位置。  
  
  
## <a name="clean-the-target-computer"></a>清除目标计算机中的
部署将覆盖接收位置配置。 当你部署的目标计算机上，发送端口的绑定文件 （和程序集） 和接收位置已替换为 XML 绑定文件中导入时。  
  
在导入之前，删除发送端口和接收位置绑定到业务流程。  
  
如果你没有在目标计算机上安装的 Microsoft Visual Studio，你可以通过运行这些脚本中删除的端口︰  
  
-   [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\Admin\WMI\Remove Send Port\VBScript\RemoveSendPort.vbs  
  
-   [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\Admin\WMI\Remove Receive Port\VBScript\RemoveReceivePort.vbs  
  
例如，在命令提示符下运行：  
  
```
cscript RemoveSendPort.vbs \<Send port name\>
```
  
## <a name="limitations"></a>限制
传输适配器密码存储为星号 (\*\*\*\*\*\*) 中的绑定文件，由 BizTalk 部署向导，导出并传递给相同的格式中的管理组件。 在导入之前编辑绑定文件，将星号替换为随机的字母数字值（即，不替换为正确密码）。 然后输入正确的密码使用 **传输属性** 后导入绑定文件页。  
  
 在导出绑定信息时，得到的绑定文件不包含传输适配器曾经在接收位置/发送端口中使用过的任何密码。 這可防止密碼資訊以純文字方式出現。 下次您使用檔案匯入繫結資訊時，必須使用傳輸屬性頁使用者介面輸入密碼。 或者，您可以在匯入前先暫時修改繫結檔案，方法是將密碼輸入繫結檔案。 在这种情况下，必须从绑定文件删除密码，导入操作成功完成后。  
  
> [!NOTE]
>  将 .msi 文件导入包含任何企业适配器的绑定信息的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 应用程序时，您可能会收到一条导入错误消息。 受支持的修补程序是可从 Microsoft 处的错误的完整说明以及[ http://support.microsoft.com/kb/923733/en-us ](http://support.microsoft.com/kb/923733/en-us)。  
  
### <a name="work-around-the-password-limitation"></a>要解决的密码限制  

**选项 1**  

- 在导入之前，请通过将替换为纯文本的星号更新绑定文件。  
  
    > [!CAUTION]
    >  出于安全考虑，这不被建议。  
  
- 在导入之前，请通过将星号替换某个垃圾值 （即，不正确的密码） 来更新绑定文件。 你导入后，请输入正确的密码使用**传输属性**。  
  
    > [!NOTE]
    >  只有当目标计算机上安装了 Microsoft Visual Studio 或者开发一个自定义工具，才能使用这种解决方法。  
  
**选项 2**  
  
1.  不使用密碼，改為使用「企業單一登入」。 使用 SSO 選項只需要先匯入繫結檔案，不需要額外操作。  
  
2.  驗證邏輯系統以及「傳輸」和「接收」服務。  

## <a name="next-steps"></a>后续步骤
[使用 BizTalk Server 中的异常处理您的业务流程](../core/using-biztalk-server-exception-handling1.md)