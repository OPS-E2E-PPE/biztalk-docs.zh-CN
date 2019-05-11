---
title: LOBWebApplication | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bd28808854b07120cce7b021d27bf1146e23d749
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65283319"
---
# <a name="lobwebapplication"></a>LOBWebApplication
使用 LOBWebApplication 实用工具提交操作消息或响应消息从 ASPX 页向贸易合作伙伴，模拟实际的业务线 Web 应用程序。  
  
 设置 ASPX 页后，起始页，并为一条消息输入参数： 本组织和合作伙伴组织;PIP 代码、 版本和实例 ID;和消息类别。 然后可以修改服务内容，并提交消息。  
  
## <a name="location-in-sdk"></a>在 SDK 中的位置  
 \<*drive*\>\Program Files (86)\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\LOBWebApplication  
  
## <a name="adding-a-virtual-server-for-lobwebapplication"></a>为 LOBWebApplication 添加虚拟服务器  
  
#### <a name="to-add-a-virtual-server"></a>若要添加虚拟服务器  
  
1.  单击**启动**，依次指向**所有程序**，指向**管理工具**，然后单击**Internet Information Services (IIS) Manager**.  
  
2.  在信息服务管理器中，展开**\<计算机名\>（本地计算机）**，展开**网站**，然后右键单击**Default Web Site**.  
  
3.  指向**新建**，然后单击**虚拟目录**。  
  
4.  上**虚拟目录创建向导**页上，单击**下一步**，然后键入别名的站点，如**LOBWebApplication**。  
  
5.  上**网站内容目录**页上，单击**浏览**，将移到\<*驱动器*\>\Program 文件 (x86) \Microsoft BizTalk \<版本\>Accelerator for RosettaNet\SDK\LOBWebApplication，单击**确定**，然后单击**下一步**。  
  
6.  上**虚拟目录访问权限**页上，选择**读取**并**运行脚本**，然后单击**下一步**。 单击 **“完成”**。  
  
7.  添加配置 BTARN，（如 hostsvc) 到 STS_WPG 时所用的服务帐户用户。  
  
8.  删除 C:\WINDOWS\Microsoft.NET\Framework\v2.0.\Temporary ASP.NET Files 中的所有文件。 您可能需要运行 iisreset 程序来解锁文件，然后才能删除它们。  
  
9. 在 IIS 管理器中，将在应用程序池 BTARNHTTPReceivePool 下运行 LOBWebApplication 设置。  
  
10. 在 IIS 管理器中 LOBWebApplication 实用工具的目录安全属性部分禁用以匿名运行的虚拟目录的选项。  
  
## <a name="building-lobwebapplication"></a>生成 LOBWebApplication  
  
#### <a name="to-build-lobwebapplication"></a>生成 LOBWebApplication  
  
1. 启动 Visual Studio。  
  
2. 上**文件**，依次指向**打开**，然后单击**打开的解决方案**。  
  
3. 将移动到\<*驱动器*\>\Program 文件 (x86) \Microsoft BizTalk\<版本\>Accelerator for RosettaNet\SDK\LOBWebApplication，选择**LOBWebApplication.sln**，然后单击**打开**。  
  
   > [!NOTE]
   >  如果未为 LOBWebApplication 添加虚拟服务器，将不会打开该解决方案中正确地[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]。  
  
4. 右键单击**引用**，然后单击**添加引用**。  
  
5. 在中**添加引用**对话框中，单击**浏览**，将移到\<*驱动器*\>: \Program 文件 (x86) \Microsoft BizTalk \<版本\>Accelerator for RosettaNet\Bin，选择 Microsoft.Solutions.BTARN.ConfigurationManager.dll 和 Microsoft.Solutions.BTARN.Shared.dll 文件，然后单击**打开**。  
  
6. 右键单击**LOBWebApplication**，然后单击**生成**。  
  
## <a name="running-lobwebapplication"></a>运行 LOBWebApplication  
  
#### <a name="to-run-lobwebapplication-and-submit-a-message"></a>运行 LOBWebApplication 并提交一条消息  
  
1.  单击**启动**，依次指向**所有程序**，然后单击**Internet Explorer**。  
  
2.  在 Internet Explorer 中，在**地址**框中，键入 http://localhost/LOBWebApplication ，然后单击**转**。  
  
3.  在中**提交消息**对话框框中，键入本组织、 合作伙伴组织、 PIP 代码、 PIP 版本、 PIP 实例 ID 和消息类别。  
  
4.  根据需要修改服务内容。  
  
5.  单击“提交”。  
  
## <a name="remarks"></a>备注  
 LOBWebApplication 实用工具从指定的 PIP 生成消息实例，并生成的消息实例的服务内容输入到 ASPX 页。 若要执行此操作，该实用程序所用的技术，使用它来直接从 PIP 生成格式正确的消息实例。 有关详细信息，请参阅[根据 PIP 创建格式正确的消息实例](../../adapters-and-accelerators/accelerator-rosettanet/creating-a-well-formed-message-instance-from-a-pip.md)。 您可以填充 ASPX 页的实际数据来生成实际的消息实例中的服务内容的任何字段。  
  
 使用 LOBWebApplication 实用工具来模拟业务线 Web 应用程序提交一条消息。 使用 LOBApplication 实用工具来模拟业务线桌面应用程序提交消息。  
  
## <a name="see-also"></a>请参阅  
 [实用程序](../../adapters-and-accelerators/accelerator-rosettanet/utilities1.md)   
 [LOBApplication](../../adapters-and-accelerators/accelerator-rosettanet/lobapplication.md)
