---
title: "LOBWebApplication |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows SharePoint Services, LOBWebApplication
- ASPX pages, LOBWebApplication utility
- virtual servers
- ASPX pages, submitting actions
- LOBWebApplication
- ASPX pages, response messages
- LOBWebApplication utility
ms.assetid: 2d578efd-72a9-4621-9274-30792bf94b6c
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a9be49eab2560cc9e9eab5a29456a27f92760e5d
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="lobwebapplication"></a>LOBWebApplication
使用 LOBWebApplication 实用工具可以将 ASPX 页中的操作或响应消息提交给贸易合作伙伴，从而模拟实际的业务线 Web 应用程序。  
  
 设置 ASPX 页后，您启动该页，输入消息的参数：本组织和合作伙伴组织；PIP 代码、版本和实例 ID；以及消息类别。 然后你可以修改服务内容并提交消息。  
  
## <a name="location-in-sdk"></a>在 SDK 中的位置  
 \<*驱动器*\>files\microsoft BizTalk 2013 Accelerator for RosettaNet\SDK\LOBWebApplication  
  
## <a name="adding-a-virtual-server-for-lobwebapplication"></a>为 LOBWebApplication 添加虚拟服务器  
  
#### <a name="to-add-a-virtual-server"></a>添加虚拟服务器  
  
1.  单击**启动**，指向**所有程序**，指向**管理工具**，然后单击**Internet Information Services (IIS) Manager**.  
  
2.  在信息服务管理器中，展开**\<计算机名称\>（本地计算机）**，展开**网站**，然后右键单击**Default Web Site**.  
  
3.  指向**新建**，然后单击**虚拟目录**。  
  
4.  上**虚拟目录创建向导**页上，单击**下一步**，，然后键入的别名站点，例如**LOBWebApplication**。  
  
5.  上**网站内容目录**页上，单击**浏览**，将移到\<*驱动器*\>files\microsoft BizTalk 2013 Accelerator 为RosettaNet\SDK\LOBWebApplication，单击**确定**，然后单击**下一步**。  
  
6.  上**虚拟目录访问权限**页上，选择**读取**和**运行脚本**，然后单击**下一步**。 单击 **“完成”**。  
  
7.  将用于配置 BTARN 的服务帐户用户（如 hostsvc）添加到 STS_WPG。  
  
8.  删除 C:\WINDOWS\Microsoft.NET\Framework\v2.0.\Temporary ASP.NET Files 中的所有文件。 在删除这些文件之前，你可能需要运行 iisreset 程序来取消这些文件的锁定。  
  
9. 在 IIS 管理器中，将 LOBWebApplication 设置为在应用程序池 BTARNHTTPReceivePool 下运行。  
  
10. 在 IIS 管理器中 LOBWebApplication 实用工具的“目录安全性属性”部分中，禁用以匿名运行虚拟目录的选项。  
  
## <a name="building-lobwebapplication"></a>构建 LOBWebApplication  
  
#### <a name="to-build-lobwebapplication"></a>生成 LOBWebApplication  
  
1.  启动 Visual Studio。  
  
2.  上**文件**，指向**打开**，然后单击**打开的解决方案**。  
  
3.  将移动到\<*驱动器*\>files\microsoft BizTalk 2013 Accelerator for RosettaNet\SDK\LOBWebApplication，选择**LOBWebApplication.sln**，然后单击**打开**。  
  
    > [!NOTE]
    >  如果你不具有 LOBWebApplication 添加虚拟服务器，将不会打开该解决方案中正确[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]。  
  
4.  右键单击**引用**，然后单击**添加引用**。  
  
5.  在**添加引用**对话框中，单击**浏览**，将移到\<*驱动器*\>: files\microsoft BizTalk 2013 Accelerator 为RosettaNet\Bin，选择 Microsoft.Solutions.BTARN.ConfigurationManager.dll 和 Microsoft.Solutions.BTARN.Shared.dll 文件，然后单击**打开**。  
  
6.  右键单击**LOBWebApplication**，然后单击**生成**。  
  
## <a name="running-lobwebapplication"></a>运行 LOBWebApplication  
  
#### <a name="to-run-lobwebapplication-and-submit-a-message"></a>运行 LOBWebApplication 并提交消息  
  
1.  单击**启动**，指向**所有程序**，然后单击**Internet Explorer**。  
  
2.  在 Internet Explorer 中，在**地址**框中，键入 http://localhost/LOBWebApplication，，然后单击**转**。  
  
3.  在**提交消息**对话框框中，键入主组织、 合作伙伴组织、 PIP 代码、 PIP 版本、 PIP 实例 ID 和消息类别。  
  
4.  根据需要修改服务内容。  
  
5.  单击“提交”。  
  
## <a name="remarks"></a>注释  
 LOBWebApplication 实用工具从指定的 PIP 生成消息的实例，并将所生成的消息实例的服务内容输入到 ASPX 页。 为此，该实用工具采用直接从 PIP 生成格式正确的消息实例时所用的技术。 有关详细信息，请参阅[PIP 从创建格式正确消息实例](../../adapters-and-accelerators/accelerator-rosettanet/creating-a-well-formed-message-instance-from-a-pip.md)。 你可以使用实际数据填充 ASPX 页中服务内容的任何字段，以生成实际消息实例。  
  
 使用 LOBWebApplication 实用工具还可以模拟业务线 Web 应用程序提交消息的过程。 使用 LOBApplication 实用工具还可以模拟业务线桌面应用程序提交消息的过程。  
  
## <a name="see-also"></a>另请参阅  
 [实用程序](../../adapters-and-accelerators/accelerator-rosettanet/utilities1.md)   
 [LOBApplication](../../adapters-and-accelerators/accelerator-rosettanet/lobapplication.md)