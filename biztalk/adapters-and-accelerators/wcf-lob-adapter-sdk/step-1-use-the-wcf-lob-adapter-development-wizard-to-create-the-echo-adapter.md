---
title: 步骤 1： 使用 WCF LOB 适配器开发向导创建 Echo 适配器项目 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 634a6498-55b0-462d-a5ca-16507b3787f5
caps.latest.revision: 23
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 86b55bdfe771eb571a999668fc8ef7d2003ddf56
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976910"
---
# <a name="step-1-use-the-wcf-lob-adapter-development-wizard-to-create-the-echo-adapter-project"></a>步骤 1： 使用 WCF LOB 适配器开发向导创建 Echo 适配器项目
![步骤 1 部分，共 9](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-1of9.gif "Step_1of9")  

 **完成时间：** 15 分钟  

 在此步骤中，您将创建项目使用[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]和[!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)]。 [!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)]将指导你完成在开发系统的自定义适配器所涉及的步骤。 它收集有关消息交换模式、 元数据功能、 适配器属性和连接属性的信息。 在向导成功完成时，它会生成一组文件。  

## <a name="prerequisites"></a>必要條件  
 你必须拥有中所述的知识[在开始本教程之前](../../core/before-you-begin-the-tutorial.md)并已成功设置通过使用计算机中的适配器开发[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。  

## <a name="choose-wcf-lob-adapter-plug-in-in-visual-studio"></a>选择 WCF LOB 适配器在 Visual Studio 插件  

1.  启动 Visual Studio，然后在**文件**菜单，依次指向**新建**，然后单击**项目**。  

2.  在中**新的项目**对话框框中，执行以下操作：  

    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**项目类型**|单击**Visual C#**。|  
    |**模板**|单击**WCF LOB 适配器**。|  
    |**名称**|类型**EchoAdapter**。|  
    |**位置**|类型**C:\Tutorials**。|  
    |**创建解决方案的目录**|选中此复选框以便为解决方案文件创建目录。|  
    |**解决方案名称**|类型**EchoAdapterSampleV2**。|  

     下图显示**新的项目**对话框。  

     ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/3a349be4-1a7d-480a-8e9d-cfcba63cd14a.gif "3a349be4-1a7d-480a-8e9d-cfcba63cd14a")  

3.  单击“确定” 。  

4.  上**欢迎**页上，单击**下一步**。 下图显示**欢迎使用**页。  

     ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/0b8ef97f-044d-481f-8c7c-0d034fdba37d.gif "0b8ef97f-044d-481f-8c7c-0d034fdba37d")  

5.  单击“下一步” 。  

## <a name="enter-the-scheme-and-namespace-information"></a>输入的方案和命名空间信息  

1.  上**方案、 Namespace 和 URI 信息**页上，执行以下操作：  

    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**方案**|类型**echov2**。|  
    |**项目命名空间**|类型**Microsoft.Adapters.Samples.EchoV2**。|  

     下图显示**方案、 Namespace 和 URI 信息**页。  

     ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/0d72dab2-7992-47e4-bc4e-3e720b1cde38.gif "0d72dab2-7992-47e4-bc4e-3e720b1cde38")  

2.  单击“下一步” 。  

## <a name="enter-the-data-flow-and-metadata-features"></a>输入数据的流和元数据功能  

1.  上**的数据流动**并**元数据功能**页上，执行以下操作：  

     **消息交换模式**  

    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**出站同步**|选中“允许其他人查看并订阅此警报” 复选框。|  
    |**同步入站**|选中“允许其他人查看并订阅此警报” 复选框。|  

     **元数据功能**  

    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**检索**|选中“允许其他人查看并订阅此警报” 复选框。|  
    |**“浏览”**|选中“允许其他人查看并订阅此警报” 复选框。|  
    |**搜索**|选中“允许其他人查看并订阅此警报” 复选框。|  

    > [!NOTE]
    >  在此上下文中的数据流意味着消息交换模式，与相同的概念性主题中使用的术语。  

     下图显示**的数据流动**并**元数据功能**页。  

     ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/4fa6f67d-4703-41db-b5f3-28cf9d6a40d2.gif "4fa6f67d-4703-41db-b5f3-28cf9d6a40d2")  

2.  单击“下一步” 。  

## <a name="enter-the-adapter-properties"></a>输入适配器属性  

1. 上**适配器属性**页上，执行以下操作：  

2. 添加一个名为属性**计数**。 Echo 适配器的每个操作使用此号码。 每个操作将返回输入的值**计数**次数。  


   |     使用此选项      |               执行的操作               |
   |-------------------|----------------------------------------|
   | **属性名称** |            类型**计数**。             |
   |   **Data type**   |        选择**System.Int32**。        |
   | **默认值** |              类型**5**。               |
   |      **“添加”**      | 单击此项可添加新的适配器属性。 |


3. 添加一个名为属性**EnableConnectionPooling**。 通过使用此标志[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]启用或禁用运行时连接池。  


   |     使用此选项      |               执行的操作               |
   |-------------------|----------------------------------------|
   | **属性名称** |   类型**EnableConnectionPooling**。    |
   |   **Data type**   |       选择**System.Boolean**。       |
   | **默认值** |             类型 **，则返回 true**。             |
   |      **“添加”**      | 单击此项可添加新的适配器属性。 |


4. 添加一个名为属性**InboundFileFilter**。 此属性是 FileSystemWatcher 用于监视此扩展名的文件。 此属性是适用于入站方案。  


   |     使用此选项      |               执行的操作               |
   |-------------------|----------------------------------------|
   | **属性名称** |      类型**InboundFileFilter**。       |
   |   **Data type**   |       选择**System.String**。        |
   | **默认值** |            类型 **\*.txt**。            |
   |      **“添加”**      | 单击此项可添加新的适配器属性。 |


5. 添加一个名为属性**InboundFileSystemWatcherFolder**。 此属性用于设置其中会为 FileSystemWatcher 引发通知到适配器中删除文件的文件夹。 此属性是适用于入站方案。  

   |使用此选项|执行的操作|  
   |--------------|----------------|  
   |**属性名称**|类型**InboundFileSystemWatcherFolder**。|  
   |**Data type**|选择**System.String**。|  
   |**默认值**|类型**c:\\\inbound\\\watcher**。|  
   |**“添加”**|单击此项可添加新的适配器属性。|  

    下图显示**适配器属性**页。  

    ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/84de11a5-a737-4aa5-96c8-61922e704f2b.gif "84de11a5-a737-4aa5-96c8-61922e704f2b")  

6. 单击“下一步” 。  

## <a name="enter-the-connection-properties"></a>输入连接属性  

1.  上**连接属性**页上，执行以下操作：  

2.  添加一个名为属性**应用程序**。 为演示目的仅是此属性。 Echo 适配器不涉及任何 LOB 系统。  

    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**属性名称**|类型**应用程序**。|  
    |**Data type**|选择**System.String**。|  
    |**默认值**|类型**lobapplication**。|  
    |**“添加”**|单击此项可添加新的适配器属性。|  

3.  添加一个名为属性**EnableAuthentication**。 当`true`，适配器需要客户端凭据中用户名字段中的值。  

    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**属性名称**|类型**EnableAuthentication**。|  
    |**Data type**|选择**System.Boolean**。|  
    |**默认值**|类型**false**。|  
    |**“添加”**|单击此项可添加新的适配器属性。|  

4.  添加一个名为属性**主机名**。 此属性是用于演示目的，类似于属性**应用程序**。  

    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**属性名称**|类型**主机名**。|  
    |**Data type**|选择**System.String**。|  
    |**默认值**|类型**lobhostname**。|  
    |**“添加”**|单击此项可添加新的适配器属性。|  

5.  添加一个名为属性**EchoInUpperCase**。 此属性控制是否某些操作将转换回显字符串转换为大写，或将它们保留在其原始格式。  

    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**属性名称**|类型**EchoInUpperCase**。|  
    |**Data type**|选择**System.Boolean**。|  
    |**默认值**|类型**False**。|  
    |**“添加”**|单击此项可添加新的适配器属性。|  

6.  单击“下一步” 。  

## <a name="end-the-wizard"></a>结束此向导  

1.  上**摘要**页上，单击**完成**。 下图显示**解决方案资源管理器**与**EchoAdapter**项目。  

     ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/06b45c3e-d056-48f4-a246-642d9ac5e23e.gif "06b45c3e-d056-48f4-a246-642d9ac5e23e")  

     你的项目应包含相同的文件。 如果不存在，退出 Visual Studio，请删除**EchoAdapterSampleV2**文件夹，然后重新启动本教程的此步骤。  

2.  在 Visual Studio 中，在**文件**菜单上，单击**全部保存**。  

    > [!NOTE]
    >  保存所做的工作。 可以安全地关闭 Visual Studio 或转到下一步[步骤 2： 将适配器和连接属性分类](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-2-categorize-the-adapter-and-connection-properties.md)。  

## <a name="what-did-i-just-do"></a>我只需做了什么？  
 通过使用 Visual Studio 在此步骤中，创建 echo 适配器解决方案和[!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)]。 下表包含一组文件和每个文件是什么。  

|**文件名**|**Description**|  
|-------------------|---------------------|  
|EchoAdapter.cs|这是主适配器类，该类继承自`Microsoft.ServiceModel.Channels.Common.Adapter`。<br /><br /> Echo 适配器所需不进行任何更改。|  
|EchoAdapterBinding.cs|这是创建的适配器的绑定时使用的类。<br /><br /> Echo 适配器所需不进行任何更改。|  
|EchoAdapterBindingCollectionElement.cs|这是实现的绑定集合元素类`System.ServiceModel.Configuration.StandardBindingCollectionElement`。<br /><br /> Echo 适配器所需不进行任何更改。|  
|EchoAdapterBindingElement.cs|此配置元素提供基类。<br /><br /> 若要将分类 echo 适配器的适配器和连接属性，请按照[步骤 2： 将适配器和连接属性分类](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-2-categorize-the-adapter-and-connection-properties.md)。|  
|EchoAdapterBindingElementExtensionElement.cs|此类用于表示适配器为绑定元素，以便可以在用户定义的 WCF 自定义绑定中使用它。<br /><br /> 若要将分类 echo 适配器的适配器和连接属性，请按照[步骤 2： 将适配器和连接属性分类](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-2-categorize-the-adapter-and-connection-properties.md)。|  
|EchoAdapterHandlerBase.cs|这是用于存储由基类公开的常见属性/帮助程序函数的处理程序类的基类。<br /><br /> 若要将分类 echo 适配器的适配器和连接属性，请按照[步骤 2： 将适配器和连接属性分类](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-2-categorize-the-adapter-and-connection-properties.md)。|  
|EchoAdapterConnection.cs|此定义的连接到目标系统。<br /><br /> 若要支持 echo 适配器连接到目标系统，请按照[步骤 3： 实现 Echo 适配器的连接](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-3-implement-the-connection-for-the-echo-adapter.md)。|  
|EchoAdapterConnectionFactory.cs|这会定义目标系统的连接工厂。<br /><br /> 若要支持 echo 适配器连接到目标系统，请按照[步骤 3： 实现 Echo 适配器的连接](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-3-implement-the-connection-for-the-echo-adapter.md)。|  
|EchoAdapterConnectionUri.cs|这是用于表示 Uri 的适配器连接类。<br /><br /> 若要支持 echo 适配器连接到目标系统，请按照[步骤 3： 实现 Echo 适配器的连接](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-3-implement-the-connection-for-the-echo-adapter.md))。|  
|EchoAdapterMetadataBrowseHandler.cs|从目标系统的元数据执行基于连接的浏览操作时使用此类。<br /><br /> 若要支持浏览 echo 适配器的功能的元数据，请按照[步骤 4： 实现 Echo 适配器的元数据浏览处理程序](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-4-implement-the-metadata-browse-handler-for-the-echo-adapter.md)。|  
|EchoAdapterMetadataSearchHandler.cs|此类用于从目标系统中执行基于连接的元数据的搜索。<br /><br /> 若要支持搜索 echo 适配器的功能的元数据，请按照[步骤 5： 实现 Echo 适配器的元数据搜索处理程序](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-5-implement-the-metadata-search-handler-for-the-echo-adapter.md)。|  
|EchoAdapterMetadataResolve.cs|此类用于从目标系统中执行基于连接的元数据检索。<br /><br /> 若要支持解决 echo 适配器的功能的元数据，请按照[步骤 6： 实现 Echo 适配器的元数据解析处理程序](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-6-implement-the-metadata-resolve-handler-for-the-echo-adapter.md)。|  
|EchoAdapterOutboundHandler.cs|此类用于将数据发送到目标系统。<br /><br /> 若要支持 echo 适配器的出站消息交换，请按照[步骤 7： 实现 Echo 适配器的同步出站处理程序](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-7-implement-the-synchronous-outbound-handler-for-the-echo-adapter.md)。|  
|EchoAdapterInboundHandler.cs|此类实现用于监听或轮询以查找数据的接口。<br /><br /> 若要支持 echo 适配器的入站的消息交换，请按照[步骤 8： 实现 Echo 适配器的同步入站处理程序](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-8-implement-the-synchronous-inbound-handler-for-the-echo-adapter.md)。|  
|EchoAdapterTrace.cs|此类实现适配器跟踪，用于调试和故障排除。|  

## <a name="next-steps"></a>后续步骤  
 你对其 UI 的逻辑分组，适配器和连接属性进行分类，然后实现连接、 元数据浏览、 搜索和解析功能和出站和入站消息交换。 最后，您生成并部署 echo 适配器。  

## <a name="see-also"></a>请参阅  
 [步骤 2： 将分类的适配器和连接属性](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-2-categorize-the-adapter-and-connection-properties.md)   
 [教程 1：开发 Echo 适配器](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md)