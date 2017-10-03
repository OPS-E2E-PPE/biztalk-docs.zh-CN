---
title: "使用.NET 项目中的 WCF LOB 适配器 SDK 适配器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6934b96d-5704-4f3c-b53f-4e36e352a338
caps.latest.revision: "19"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fb6208395813c7e4be25964d9949d2f909e4806d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="consume-a-wcf-lob-adapter-sdk-adapter-in-a-net-project"></a>使用.NET 项目中的 WCF LOB 适配器 SDK 适配器
若要使用使用构建适配器[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]从[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，你必须添加到项目的服务引用。 可以执行此操作：  
  
-   使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]，作为的一部分安装的哪些[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。  
  
-   使用 svcutil.exe （ServiceModel 元数据实用工具），作为 Windows SDK 的一部分安装。  
  
## <a name="add-a-service-reference-using-the-add-adapter-service-reference-plug-in"></a>添加服务引用使用添加适配器服务引用插件  
 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]可以用于浏览和搜索元数据，并生成使用所选的操作和类型的.NET CLR 代理类。  
  
 
1.  打开.NET 应用程序中的[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]。  
  
2.  在[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，右键单击**项目**菜单，，然后单击**添加适配器服务引用**。  
  
    > [!NOTE]
    >  此选项未显示为[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]项目。  
  
3.  在[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]屏幕上，从**选择的绑定**下拉列表中，选择适配器绑定。  
  
4.  若要配置所选的适配器绑定的连接 URI 并提供任何凭据、 URI 属性和绑定属性，单击**配置**。 根据所选的适配器绑定实际要求可能有所不同。  
  
5.  当你配置了 URI 时，则单击**确定**。  
  
6.  单击 **“连接”**。 连接 URI 是否有效并且接受客户端凭据 （如果有），**类别**窗格中应使用的类别和操作提供的适配器来填充。  
  
7.  如果适配器支持搜索，搜索字段将处于活动状态。 否则为你可以按协定类型进行筛选，通过单击中的节点浏览类型和操作**类别**窗格。  
  
8.  有关高级的代理生成选项，请单击**高级**。 您的选择包括:   
  
    |选项|等效的 svcutil.exe 选项|Description|  
    |------------|-----------------------------------|-----------------|  
    |**生成异步方法**|/async|同时生成同步和异步方法签名。<br /><br /> 默认值 （如果尚未选中）： 生成仅同步方法签名。|  
    |**生成消息协定**|/messageContract|生成消息协定类型。|  
    |**使类型内部**|/ 内部|生成标记为内部的类。<br /><br /> 默认值 （如果尚未选中）： 生成公共类。|  
    |**启用数据绑定**|/enableDataBinding|实现 System.ComponentModel.INotifyPropertyChanged 接口以启用数据绑定的所有数据协定类型。|  
    |**将非数据类型作为 IXmlSerializable 导入**|/importXmlTypes|配置数据协定序列化程序将非数据协定类型作为 IXmlSerializable 类型导入。|  
    |**生成通道接口**||生成的通道接口。|  
    |**标记类可序列化**||选择是否生成的序列化的数据类型。|  
    |**不生成 app.config**|/noConfig|不生成应用程序配置文件。|  
    |**序列化程序**<br /><br /> **Auto**|/serializer:Auto|会自动选择序列化程序进行序列化和反序列化。|  
    |**序列化程序**<br /><br /> **DataContract 序列化程序**|/serializer:DataContractSerializer|生成使用数据协定序列化程序进行序列化和反序列化的数据类型|  
    |**序列化程序**<br /><br /> **XmlSerializer**|/serializer: xmlserializer|生成使用 XmlSerializer 进行序列化和反序列化的数据类型。|  
  
9. 若要生成的代理服务器项目，请单击**确定**。 根据协定类型的项目数而有所不同。  
  
    |协定类型|项目|Description||  
    |-------------------|--------------|-----------------|-|  
    |出站|CLR WCF 代理|包含的协定和服务实现。||  
    |出站||App.config|包含\<终结点 > 和\<绑定 > 元素\<系统。ServiceModel >\<客户端 >。|  
    |入站|CLR WCF 服务接口|包含的协定。||  
    |入站||CLR WCF 服务实现|派生自协定的存根实现。|  
    |入站||App.config|包含\<终结点 >，\<绑定 > 和\<行为 > 元素\<系统。ServiceModel >\<服务 >。|  
  
10. 你现在可以在你的应用程序中使用代理。  
  
## <a name="adding-a-service-reference-by-using-svcutilexe"></a>通过使用 svcutil.exe 添加服务引用  
 Svcutil.exe 是可以用于检索元数据和生成.NET CLR 代理类，然后添加到命令行实用工具[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]项目。 Svcutil.exe 有关的详细信息，请参阅[ServiceModel 元数据实用工具 (Svcutil.exe)](https://msdn.microsoft.com/library/aa347733.aspx)。 
  
 若要从承载于 IIS 中的适配器生成代理类  
  
1.  在命令提示符处，输入**svcutil.exe"http://localhost/adapter/AdapterService.svc?wsdl"/config:app.config**。将 HTTP 路径替换为你托管的适配器的正确路径。 这将创建包含.NET CLR 代理和 output.config 其中包含的.cs 文件\<绑定 > 和客户端\<终结点 > 为\<system.serviceModel >。  
  
    > [!NOTE]
    >  如果你的适配器包含许多操作，你可以限制通过使用的查询字符串返回的操作 op = 跟感兴趣的操作的名称。 例如：`svcutil.exe “http://localhost/adapter/AdapterService.svc?wsdl&op=Echo/EchoString&op=Echo/EchoArray”`生成仅 EchoString 和 EchoArray 操作的代理代码。  
  
2.  打开你的项目中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]。  
  
    1.  在**解决方案资源管理器**，右键单击项目，指向**添加**，然后单击**新项**。 在**添加现有项**对话框中，选择前面创建的.cs 和 app.config 文件。  单击 **“添加”**。  
  
    2.  在**解决方案资源管理器**，右键单击**引用**，然后单击**添加引用**。 上**.NET**选项卡上，选择**System.ServiceModel**，然后单击**确定**。 你现在可以在你的应用程序中使用代理。  
  
## <a name="see-also"></a>另请参阅  
 [教程 1： 开发 Echo 适配器](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md)   
 [使用使用 WCF LOB 适配器 SDK 创建的适配器](../../adapters-and-accelerators/wcf-lob-adapter-sdk/consume-an-adapter-created-using-the-wcf-lob-adapter-sdk.md)