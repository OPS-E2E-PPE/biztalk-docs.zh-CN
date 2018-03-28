---
title: 导入博士 Edwards EnterpriseOne 应用程序 |Microsoft 文档
description: 确认安装程序，导入应用程序绑定文件，并查看博士 Edwards EnterpriseOne 适配器在 BizTalk 的限制
ms.custom: ''
ms.date: 10/18/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 852f948b-48ba-4ae2-b1eb-7c88c1542a52
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 55374c87192c993e26cc11cb496d89074d527868
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="import-the-jd-edwards-enterpriseone-application"></a>导入博士 Edwards EnterpriseOne 应用程序
  
## <a name="overview"></a>概述
与[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，你可以复制端口和目标计算机上的程序集。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 发送/接收端口的位置将配置导出到 XML 文件。  
  
 使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 可以执行以下任务：  
  
-   将 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 程序集部署到 BizTalk 配置数据库中或从其删除  
  
-   将程序集安装在全局程序集缓存 (GAC) 中或从其卸载  
  
-   将 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 程序集绑定信息导入到绑定文件或从其导出  
  
若要使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]若要部署的端口和程序集，请参阅[如何导出 BizTalk 应用程序的绑定](../core/how-to-export-bindings-for-a-biztalk-application.md)。  
  
> [!NOTE]
>  用于 JD Edwards EnterpriseOne 的 Microsoft BizTalk 适配器只要求在源（开发）计算机上具有 Visual Studio。 在生产计算机上不要求使用 Visual Studio。  

## <a name="confirm-your-setup"></a>确认你的设置
在使用 BizTalk Server 导入绑定文件之前，必须验证以下各项：  
  
-   CLASSPATH 指向特定于 JD Edwards EnterpriseOne 文件的特定位置。 验证在新计算机上这些文件的位置是否相同，否则编辑绑定文件。  
  
-   用于响应的文件夹存在，并且在新计算机上相同，否则编辑绑定文件。  
  
-   如果在配置中存在 JD Edwards EnterpriseOne 系统密码，则在绑定文件中另存为 *****。 有关详细信息，请参阅**限制**本主题中。

## <a name="clean-the-target-computer"></a>清除目标计算机中的
当你重新绑定文件 （和程序集） 部署的目标计算机上，发送端口和接收位置已替换为 XML 绑定文件中时它们重新导入。  
  
在导入之前，删除发送端口和接收位置绑定到业务流程。 如果未安装目标计算机上安装的 Visual Studio，你可以通过运行脚本中删除的端口︰  
  
- [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\Admin\WMI\Remove Send Port\VBScript\RemoveSendPort.vbs  
  
- [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\Admin\WMI\Remove Receive Port\VBScript\RemoveReceivePort.vbs  

例如，从命令提示符下运行：  
  
```
cscript RemoveSendPort.vbs \<Send port name\>
```
## <a name="limitations"></a>限制
传输适配器密码为星号 （*） 存储在由导出绑定文件[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，并将它传递给相同的格式中的管理组件。 在匯入繫結檔案前先行編輯該檔案，方法是將星號取代為某些垃圾值 (亦即不正確的密碼)。  
  
 當您匯出繫結資訊時，所產生的繫結檔案不會包含傳輸配接器在接收位置/傳送埠中使用的任何密碼。 這可防止密碼資訊以純文字方式出現。 下次您使用檔案匯入繫結資訊時，必須使用傳輸屬性頁使用者介面輸入密碼。  
  
 或者，您可以在匯入前先暫時修改繫結檔案，方法是將密碼輸入繫結檔案。 在這種情況下，您必須在匯入作業順利完成後刪除繫結檔案中的密碼。  
  
### <a name="work-around-the-password-limitation"></a>要解决的密码限制  
  
1.  不使用密碼，改為使用「企業單一登入」。 使用 SSO 選項只需要先匯入繫結檔案，不需要額外操作。  
  
2.  驗證邏輯系統以及「傳輸」和「接收」服務。  


## <a name="next-steps"></a>后续步骤
[使用 BizTalk Server 中的异常处理您的业务流程](../core/using-biztalk-server-exception-handling3.md)