---
title: 阅读有关 BizTalk 适配器用于 Siebel 绑定属性 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- binding properties, setting
- binding properties, adapter
- how to, set binding properties
ms.assetid: 48c77a2d-091c-40e0-aaf3-dc2ec34c55f2
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3237be098ea19fc7ff35770ddcb38a10d1e85c1c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22224037"
---
# <a name="read-about-biztalk-adapter-for-siebel-binding-properties"></a>阅读有关 BizTalk 适配器用于 Siebel 绑定属性
[!INCLUDE[adaptersiebel_md](../../includes/adaptersiebel-md.md)]面，使您可以控制某些其运行时和设计时行为的多个绑定属性。 本节描述了这些绑定属性，并提供一些链接，这些主题介绍如何设置它们。  
  
## <a name="the-siebel-adapter-binding-properties"></a>Siebel 适配器绑定属性  
 下表显示[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]绑定属性按类别分组。 类别是指在其下每个绑定属性将显示在提供的不同应用程序可配置的适配器 （或绑定） 的对话框中的节点。  
  
|绑定属性|类别|Description|.NET 类型|  
|----------------------|--------------|-----------------|---------------|  
|EnableBizTalkCompatibilityMode|常规|指定是否应加载 BizTalk 分层通道绑定元素。<br /><br /> 将其设置为**True**加载的绑定元素。 否则，将其设置为**False**。<br /><br /> 使用从适配器时[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，始终必须将属性设置为**True**。 使用从适配器时[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，始终必须将属性设置为**False**。|bool (System.Boolean)|  
|Name|常规|指定生成的文件的名称[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]来保存[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]客户端类。 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]窗体的值通过追加"客户端"的文件名称**名称**属性默认值是"SiebelBinding"; 对于此值，生成的文件将被命名为"SiebelBindingClient"。|string|  
|CloseTimeout|常规|指定[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]连接关闭超时。 默认值为 1 分钟。|System.DateTime|  
|OpenTimeout|常规|指定[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]连接打开超时。 默认值为 1 分钟。|System.DateTime|  
|ReceiveTimeout|常规|指定[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]消息接收超时。 默认值为 10 分钟。|System.DateTime|  
|SendTimeout|常规|指定[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]消息发送超时。 默认值为 1 分钟。|System.DateTime|  
|EnableConnectionPooling|连接|指定是否[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]启用连接池。 默认值是**true**，它指定是否启用了连接池。|bool (System.Boolean)|  
|IdleConnectionTimeout|连接|指定[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]空闲连接超时。 当连接超过此超时的时间段内处于空闲状态时，则将释放连接。 默认值为 1 分钟。|System.DateTime|  
|MaxConnectionsPerSystem|连接|指定的最大中的连接数[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]连接池。 默认值为 5。 **MaxConnectionsPerSystem**是应用程序域中的静态属性。 这意味着，当你更改**MaxConnectionsPerSystem**对于应用程序域中的一个绑定实例，新值适用于从该应用程序域中的所有绑定实例创建的所有对象。|int (System.Int32)|  
|EnablePerformanceCounters|诊断|指定是否[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]性能计数器和[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]LOB 延迟性能计数器已启用。 默认值是**true**; 启用性能计数器。 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] LOB 延迟性能计数器测量适配器在中对 Siebel 系统进行调用所花的总时间。|bool (System.Boolean)|  
|日志数据|诊断|指定是否捕获跟踪中的业务数据。 默认值是**false**; 不捕获业务数据。|bool (System.Boolean)|  
|AcceptCredentialsInUri|不显示[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]或[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。|指定是否 Siebel 连接 URI 可包含 Siebel 系统的用户凭据。 默认值是**false**，这将禁用连接 URI 中的用户凭据。 如果**AcceptCredentialsInUri**是**false**和连接 URI 包含用户凭据[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]引发异常。 你可以设置**AcceptCredentialsInUri**到**true**如果必须在 URI 中指定凭据。 有关详细信息，请参阅[创建 Siebel 系统连接 URI](../../adapters-and-accelerators/adapter-siebel/create-the-siebel-system-connection-uri.md)。|bool (System.Boolean)|  
  
## <a name="how-do-i-set-siebel-binding-properties"></a>如何设置绑定属性的 Siebel？  
 配置 Siebel 系统连接时，你可以设置 Siebel 绑定属性。 有关如何设置绑定属性的信息时您：  
  
-   使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]或[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]，请参阅[连接到 Visual Studio 中的 Siebel 系统](../../adapters-and-accelerators/adapter-siebel/connect-to-the-siebel-system-in-visual-studio.md)。  
  
    > [!IMPORTANT]
    >  在使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]或[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]，如果未指定的字符串类型的绑定属性的值，并且其默认值为 null，则该绑定属性将不可用绑定文件 （XML 文件） 或 app.config 文件中分别。 你必须手动添加绑定属性，并且其值在绑定文件或 app.config 文件中，如果需要。  
  
-   配置发送端口或接收端口 （位置） 中[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]解决方案，请参阅[配置物理端口绑定使用的端口绑定文件，以便 Siebel](../../adapters-and-accelerators/adapter-siebel/configure-a-physical-port-binding-using-a-port-binding-file-to-siebel.md)。
  
-   使用编程解决方案中的 WCF 通道模型，请参阅[创建一个通道，使用 Siebel](../../adapters-and-accelerators/adapter-siebel/create-a-channel-using-siebel.md)。  
  
-   使用 WCF 服务模型编程解决方案中，请参阅[为 Siebel 系统配置 WCF 客户端](../../adapters-and-accelerators/adapter-siebel/configure-a-wcf-client-for-a-siebel-system.md)。  
  
-   使用 WCF ServiceModel 元数据实用工具 (svcutil.exe)，请参阅[用于 Siebel eBusiness Applications ServiceModel 元数据实用工具使用 BizTalk 适配器](../../adapters-and-accelerators/adapter-siebel/use-the-servicemodel-metadata-utility-with-the-siebel-adapter.md)。  
  
## <a name="see-also"></a>另请参阅  
[开发 Siebel 应用程序](../../adapters-and-accelerators/adapter-siebel/develop-your-siebel-applications.md)