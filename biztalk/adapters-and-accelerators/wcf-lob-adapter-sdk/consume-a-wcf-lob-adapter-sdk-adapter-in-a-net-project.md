---
title: 使用.NET 项目中的 WCF LOB 适配器 SDK 适配器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6934b96d-5704-4f3c-b53f-4e36e352a338
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a847aeae8c3c6ee564c38acf0b87679cd8469840
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994102"
---
# <a name="consume-a-wcf-lob-adapter-sdk-adapter-in-a-net-project"></a>使用.NET 项目中的 WCF LOB 适配器 SDK 适配器
若要使用使用构建适配器[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]从[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，必须添加到项目的服务引用。 可以执行此操作：  

- 使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]，作为的一部分安装的哪些[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。  

- 使用 svcutil.exe （ServiceModel 元数据实用工具），它作为 Windows SDK 的一部分安装。  

## <a name="add-a-service-reference-using-the-add-adapter-service-reference-plug-in"></a>添加服务引用使用添加适配器服务引用插件  
 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]可用于浏览和搜索元数据，并生成.NET CLR 代理类使用的所选的操作和类型。  


1. 打开.NET 应用程序中的[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]。  

2. 在中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，右键单击**项目**菜单，并单击**添加适配器服务引用**。  

   > [!NOTE]
   >  此选项不会显示为[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]项目。  

3. 在中[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]屏幕上，从**选择绑定**下拉列表中，选择一个适配器的绑定。  

4. 若要配置的所选的适配器绑定的连接 URI 并提供任何凭据、 URI 属性和绑定属性，请单击**配置**。 根据所选的适配器绑定实际要求可能有所不同。  

5. 如果配置了 URI，请单击**确定**。  

6. 单击 **“连接”**。 如果连接 URI 有效并且接受客户端凭据 （如果有），**类别**窗格应填充的类别和适配器提供的操作。  

7. 如果适配器支持搜索，搜索字段将处于活动状态。 否则为您可以按协定类型筛选器中，通过单击中的节点浏览类型和操作**类别**窗格。  

8. 高级的代理生成选项，请单击**高级**。 您的选择包括:   


   |                         选项                         |   等效的 svcutil.exe 选项    |                                                                     Description                                                                     |
   |--------------------------------------------------------|------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------|
   |           **生成异步方法**            |               /async               | 生成这两个同步和异步方法签名。<br /><br /> 默认值 （如果尚未选中）： 生成仅同步方法签名。 |
   |             **生成消息协定**             |          /messageContract          |                                                          生成消息协定类型。                                                          |
   |                **使类型为内部参数**                 |             / 内部              |                   生成标记为内部的类。<br /><br /> 默认值 （如果尚未选中）： 生成公共类。                    |
   |                **启用数据绑定**                 |         /enableDataBinding         |              实现 System.ComponentModel.INotifyPropertyChanged 接口以启用数据绑定的所有数据协定类型。               |
   |     **非数据类型作为 IXmlSerializable 导入**      |          /importXmlTypes           |                        配置数据协定类型作为 IXmlSerializable 类型导入的数据协定序列化程序。                         |
   |             **生成通道接口**             |                                    |                                                          生成通道接口。                                                           |
   |             **标记类可序列化**              |                                    |                                            选择是否生成序列化程序使用的数据类型。                                            |
   |             **不会生成 app.config**             |             /noConfig              |                                                  不会生成应用程序配置文件。                                                  |
   |          **序列化程序**<br /><br /> **Auto**           |          /serializer:Auto          |                                     会自动选择序列化和反序列化的序列化程序。                                      |
   | **序列化程序**<br /><br /> **DataContract 序列化程序** | /serializer:DataContractSerializer |                         生成使用数据协定序列化程序进行序列化和反序列化的数据类型                          |
   |      **序列化程序**<br /><br /> **XmlSerializer**      |     /serializer: xmlserializer      |                               生成使用 XmlSerializer 进行序列化和反序列化的数据类型。                                |


9. 若要生成的代理服务器项目，单击**确定**。 根据协定类型的项目数而异。  


   | 协定类型 |         项目          |                    Description                    |                                                                                                            |
   |---------------|---------------------------|---------------------------------------------------|------------------------------------------------------------------------------------------------------------|
   |   出站    |       CLR WCF 代理       | 包含的协定和服务实现。 |                                                                                                            |
   |   出站    |                           |                    App.config                     |         包含\<终结点\>并\<绑定\>元素\<系统。ServiceModel\>\<客户端\>。         |
   |    入站    | CLR WCF 服务接口 |              包含的协定。               |                                                                                                            |
   |    入站    |                           |          CLR WCF 服务实现           |                            派生自协定的存根实现。                             |
   |    入站    |                           |                    App.config                     | 包含\<终结点\>，\<绑定\>并\<行为\>元素\<系统。ServiceModel\>\<服务\>。 |


10. 现在可以在应用程序中使用该代理。  

## <a name="adding-a-service-reference-by-using-svcutilexe"></a>使用 svcutil.exe 添加服务引用  
 Svcutil.exe 是一个命令行实用工具，可用于检索元数据和生成.NET CLR 代理类，然后添加到[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]项目。 有关 svcutil.exe 的详细信息，请参阅[ServiceModel Metadata Utility Tool (Svcutil.exe)](https://msdn.microsoft.com/library/aa347733.aspx)。 

 若要从适配器在 IIS 中承载生成代理类  

1. 在命令提示符处，输入**svcutil.exe"<http://localhost/adapter/AdapterService.svc?wsdl”> /config:app.config**。HTTP 路径替换为你托管的适配器的正确路径。 这将创建一个.cs 文件包含.NET CLR 代理和其中包含 output.config\<绑定\>和客户端\<终结点\>有关\<system.serviceModel\>。  

   > [!NOTE]
   >  如果您的适配器包含很多操作，则可以限制使用的查询字符串返回的操作 op = 跟你感兴趣的操作的名称。 例如：`svcutil.exe “http://localhost/adapter/AdapterService.svc?wsdl&op=Echo/EchoString&op=Echo/EchoArray”`仅 EchoString 和 EchoArray 操作为生成代理代码。  

2. 打开的项目中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]。  

   1.  在中**解决方案资源管理器**，右键单击项目，依次指向**添加**，然后单击**新项**。 在中**添加现有项**对话框中，选择前面创建的.cs 和 app.config 文件。  单击 **“添加”**。  

   2.  在中**解决方案资源管理器**，右键单击**引用**，然后单击**添加引用**。 上 **.NET**选项卡上，选择**System.ServiceModel**，然后单击**确定**。 现在可以在应用程序中使用该代理。  

## <a name="see-also"></a>请参阅  
 [教程 1： 开发 Echo 适配器](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md)   
 [使用创建使用 WCF LOB 适配器 SDK 的适配器](../../adapters-and-accelerators/wcf-lob-adapter-sdk/consume-an-adapter-created-using-the-wcf-lob-adapter-sdk.md)