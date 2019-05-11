---
title: 自述文件中 WCF LOB 适配器 SDK 和隐私 |Microsoft Docs
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
ms.openlocfilehash: 0edaa14431f1d75260958c1b145f1ec24ede5b08
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65363398"
---
# <a name="readme-and-privacy-in-the-wcf-lob-adapter-sdk"></a>自述文件和 WCF LOB 适配器 SDK 中的隐私
Windows Communication Foundation (WCF) 行业的业务线 (LOB) 适配器软件开发工具包 (SDK)  
  
## <a name="inside-the-sdk"></a>在 SDK  
 下表显示了 WCF LOB 适配器 SDK 中的各种组件的内容\<安装文件夹\>之后安装程序。  
  
|类型|Location|Description|  
|----------|--------------|-----------------|  
|运行的时|\<Installation Folder\> \Bin\Microsoft.ServiceModel.Channels.dll<br /><br /> \<Installation Folder\> \Bin\Microsoft.ServiceModel.Channels.Tools.MetadataSearchBrowse.dll|这些程序集包含运行时包括工具中使用的主窗体组件的基础。|  
|工具|\<Installation Folder\> \Tools\Microsoft.ServiceModel.Channels.Tools.PlugInPackage.dll<br /><br /> \<Installation Folder\> \Tools\Microsoft.ServiceModel.Channels.Tools.BizTalkExtension.dll<br /><br /> \<Installation Folder\> \Tools\Microsoft.ServiceModel.Channels.Wizards.dll|**添加适配器服务参考 Visual Studio 插件**<br /><br /> （.NET 项目 [右键单击]，添加适配器服务引用）<br /><br /> **使用适配器服务的 BizTalk 项目外接程序**<br /><br /> （BizTalk 项目 [右键单击]，添加，添加生成的项，使用适配器服务）<br /><br /> **WCF LOB 适配器开发向导**<br /><br /> (新文件，项目中，视觉对象C#，WCF LOB 适配器)|  
|文档|\<Installation Folder\> \Documents\WCFLOBAdapterSDK.chm|此文件包含概念内容和此版本的托管的参考内容。|  
|产品标识符文件|\<Installation Folder\>\Documents\pid.txt|此文件包含 WCF LOB 适配器 SDK 的产品标识符。 联系 Microsoft 客户服务和支持 (CSS) 时，请使用此产品标识符作为参考。|  
|示例|\<Installation Folder\> \Documents\Samples\ContosoAdapterSample.zip<br /><br /> \<Installation Folder\> \Documents\Samples\EchoAdapterSample.zip|示例文件夹包含两个示例适配器：Contoso 适配器和 Echo 适配器。|  

## <a name="privacy"></a>隐私
Microsoft 致力于保护最终用户的隐私。 在生成适配器使用[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]，它可能会影响最终用户的隐私。 例如，您的适配器可能显式收集并发送用户凭据，或者它可能会发送和接收来自业务线系统的敏感信息。 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]不发送任何信息向 Microsoft 从你的应用程序除非您或用户选择将其发送给我们。  
  
### <a name="windows-communication-foundation-privacy"></a>Windows Communication Foundation 隐私  
 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]是对扩展[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]，这种情况下依赖于许多提供的服务。 有关详细信息[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]隐私，请参阅[Windows Communication Foundation 隐私信息](https://msdn.microsoft.com/library/ms733927.aspx)。  
  
### <a name="microsoft-wcf-lob-adapter-sdk-privacy"></a>Microsoft WCF LOB 适配器 SDK 隐私  
 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]是一个 API。 作为开发人员，您可以提供自定义日志记录和跟踪功能来便于调试，优化，并审核的适配器中创建。 如果你提供此类功能，必须考虑将记录的信息和信息将如何受限制，以便只有经过授权的个人可以访问的类型。 这可能涉及以下：  
  
-   设置和维护适当访问控制列表 (Acl) 对日志和跟踪文件。  
  
-   写入到文件之前，请筛选敏感数据。  
  
-   写入到文件之前加密敏感数据。  