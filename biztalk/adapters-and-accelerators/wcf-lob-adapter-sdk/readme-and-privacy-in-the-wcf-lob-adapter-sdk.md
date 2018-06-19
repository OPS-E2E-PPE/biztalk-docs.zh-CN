---
title: 自述文件和 WCF LOB 适配器 SDK 中的隐私 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 539a88f9-ce59-46e6-8c9a-418484eabff4
caps.latest.revision: 29
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9b0e66bb7f13fd0a7cc39e983ac891708183662b
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25965163"
---
# <a name="readme-and-privacy-in-the-wcf-lob-adapter-sdk"></a>自述文件和 WCF LOB 适配器 SDK 中的隐私
Windows Communication Foundation (WCF) 行的业务 (LOB) 适配器软件开发工具包 (SDK)  
  
## <a name="inside-the-sdk"></a>在 SDK  
 下表显示 WCF LOB 适配器 SDK 中的各个组件内容\<安装文件夹\>之后安装程序。  
  
|类型|位置|Description|  
|----------|--------------|-----------------|  
|运行的时|\<安装文件夹\>\Bin\Microsoft.ServiceModel.Channels.dll<br /><br /> \<安装文件夹\>\Bin\Microsoft.ServiceModel.Channels.Tools.MetadataSearchBrowse.dll|这些程序集包含运行时间包括在工具中使用的主窗体组件的基。|  
|工具|\<安装文件夹\>\Tools\Microsoft.ServiceModel.Channels.Tools.PlugInPackage.dll<br /><br /> \<安装文件夹\>\Tools\Microsoft.ServiceModel.Channels.Tools.BizTalkExtension.dll<br /><br /> \<安装文件夹\>\Tools\Microsoft.ServiceModel.Channels.Wizards.dll|**添加适配器服务引用 Visual Studio 插件**<br /><br /> （.NET 项目 [右键单击]，添加适配器服务引用）<br /><br /> **使用适配器 BizTalk Project 外接程序服务**<br /><br /> （BizTalk 项目 [右键单击]，添加，添加生成的项，使用适配器服务）<br /><br /> **WCF LOB 适配器开发向导**<br /><br /> （文件、 新的项目，Visual C#，WCF LOB 适配器）|  
|文档|\<安装文件夹\>\Documents\WCFLOBAdapterSDK.chm|此文件包含概念内容和此版本中受管理的参考内容。|  
|产品标识符文件|\<安装文件夹\>\Documents\pid.txt|此文件包含 WCF LOB 适配器 SDK 的产品标识符。 联系 Microsoft 客户服务和支持 (CSS) 时，请使用此产品标识符作为参考。|  
|示例|\<安装文件夹\>\Documents\Samples\ContosoAdapterSample.zip<br /><br /> \<安装文件夹\>\Documents\Samples\EchoAdapterSample.zip|示例文件夹包含两个示例适配器： Contoso 适配器和 Echo 适配器。|  

## <a name="privacy"></a>隐私
Microsoft 致力于保护最终用户的隐私。 当你生成适配器使用[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]，它可能会影响最终用户的隐私。 例如，你的适配器可能显式收集并发送用户的凭据，或它可能发送和接收来自业务线系统敏感信息。 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]不任何向 Microsoft 发送信息从你的应用程序除非您或用户选择将其发送给我们。  
  
### <a name="windows-communication-foundation-privacy"></a>Windows Communication Foundation 隐私  
 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]是扩展[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]，因此依赖于许多提供的服务。 有关详细信息[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]隐私，请参阅[Windows Communication Foundation 隐私信息](https://msdn.microsoft.com/library/ms733927.aspx)。  
  
### <a name="microsoft-wcf-lob-adapter-sdk-privacy"></a>Microsoft WCF LOB 适配器 SDK 隐私  
 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]是 API。 作为开发人员，你可以提供自定义日志记录和跟踪功能，为了便于调试，优化，并在适配器审核创建。 如果你提供此类功能，你必须考虑的一种将记录的信息和如何信息将受到限制，以便只有经过授权的个人具有访问权限。 这可能涉及以下：  
  
-   设置和维护适当访问控制列表 (Acl) 对日志和跟踪文件。  
  
-   在写入到文件之前，请筛选敏感数据。  
  
-   在写入到文件之前，请加密敏感数据。  