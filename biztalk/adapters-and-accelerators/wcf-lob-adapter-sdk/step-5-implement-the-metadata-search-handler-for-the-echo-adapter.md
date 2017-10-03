---
title: "步骤 5： 为 Echo 适配器实现的元数据搜索处理程序 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1a133a99-1d6c-4634-b928-0f4f23c6f6e4
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8d241499e10a944eb1941b680bc73b97ce6ffd93
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-5-implement-the-metadata-search-handler-for-the-echo-adapter"></a>步骤 5： 为 Echo 适配器实现的元数据搜索处理程序
![步骤 5 9](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-5of9.gif "Step_5of9")  
  
 **完成时间：** 30 分钟  
  
 在本教程的此步骤中，你可以实现 Echo 适配器的搜索功能。 与浏览，不同搜索是可选的。 根据[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]，若要支持搜索功能，则必须实现`Microsoft.ServiceModel.Channels.Common.IMetadataSearchHandler`接口。 为 Echo 适配器[!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)]自动生成一个调用 EchoAdapterMetadataSearchHandler 的派生的类。  
  
 第一次更新 EchoAdapterMetadataSearchHandler 类，以获取更好地了解如何实现此接口，如何填充`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`对象，并且搜索结果中的显示方式[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]工具。  
  
## <a name="prerequisites"></a>先决条件  
 在开始此步骤之前，完成[步骤 4： 为 Echo 适配器实现的元数据浏览处理程序](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-4-implement-the-metadata-browse-handler-for-the-echo-adapter.md)。 您还必须清楚地了解有关以下类：  
  
-   `Microsoft.ServiceModel.Channels.MetadataRetrievalNode`
  
-   `Microsoft.ServiceModel.Channels.Common.IMetadataSearchHandler`  
  
-   `Microsoft.ServiceModel.Channels.MetadataRetrievalNodeDirections`  
  
## <a name="the-imetadatasearchhandler-interface"></a>IMetadataSearchHandler 接口  
 `Microsoft.ServiceModel.Channels.Common.IMetadataSearchHandler`定义为：  
  
```  
public interface IMetadataSearchHandler : IConnectionHandler, IDisposable  
{  
    MetadataRetrievalNode[] Search(string nodeId, string searchCriteria, int maxChildNodes, TimeSpan timeout);  
}  
```  
  
 `Microsoft.ServiceModel.Channels.Common.IMetadataSearchHandler.Search%2A`方法返回的数组`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`对象基于搜索条件。 Search 方法的参数定义如下表所述：  
  
|**参数**|**定义**|  
|-------------------|--------------------|  
|nodeId|从其开始搜索的节点 ID。 如果为 null 或空字符串 ("")，将从根节点 （"/"） 检索操作。|  
|searchCriteria|是特定于适配器的搜索条件。 如果指定未搜索条件，该适配器应返回所有节点。|  
|maxChildNodes|要返回的结果节点最大数量。 使用 Int32.Max 检索结果的所有节点。<br /><br /> 不支持 Echo 适配器。|  
|timeout|允许此操作完成的最大时间。<br /><br /> 不支持 Echo 适配器。|  
  
 搜索结果，对于你的适配器可以选择返回类别节点和 / 或操作节点。 将搜索功能的类型由您的适配器支持。  
  
## <a name="echo-adapter-metadata-search"></a>Echo 适配器元数据搜索  
 根据目标系统的类别和操作中，有许多方法来生成的数组`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`要返回的对象。 Echo 适配器实现的搜索功能的方式是通过其节点 id 为以下列表中每个操作：  
  
```  
Echo/OnReceiveEcho, inbound operation  
Echo/EchoStrings, outbound operation  
Echo/EchoGreetings, outbound operation  
Echo/EchoGreetingFromFile, outbound operation  
```  
  
-   如果节点 ID 然后匹配搜索条件，它将创建`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`对象使用该操作的节点 ID，然后将分配具有值的属性。 例如：  
  
    ```  
    MetadataRetrievalNode nodeInbound = new MetadataRetrievalNode("Echo/OnReceiveEcho"); //create the MetadataRetrievalNode using the operation's node ID.  
    nodeInbound.DisplayName = "OnReceiveEcho"; //The Display Name shown in the Name column of the Add Adapter Service Reference Visual Studio Plug-in  
    nodeInbound.Description = "This operation echoes the location and length of a file dropped in the specified file system.";  //The Description shown as the tool tip in the Add Adapter Service Visual Studio Plug-in  
    nodeInbound.Direction = MetadataRetrievalNodeDirections.Inbound;    //It is an inbound operation  
    nodeInbound.IsOperation = true;  //It is an operation, not category.  
    ```  
  
-   然后将该对象添加到的集合`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`s，例如，  
  
    ```  
    resultList.Add(nodeInbound);  
    ```  
  
-   最后返回的集合的数组格式。  
  
    ```  
    return resultList.ToArray();  
    ```  
  
 你可以使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]和[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]工具来执行基于连接的可用操作搜索。 例如下, 图显示搜索条件时字符串**问候**，搜索返回**EchoGreetings**和**EchoGreetingFromFile**操作。  
  
 ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/874c046a-590f-4047-9b9c-bb8074664755.gif "874c046a-590f-4047-9b9c-bb8074664755")  
  
 如果不找到任何匹配项，则这两个工具将返回如下图中显示的错误消息。  
  
 ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/cb1f79a2-a63d-4828-9dce-905c026cd1dc.gif "cb1f79a2-a63d-4828-9dce-905c026cd1dc")  
  
## <a name="implementing-the-imetadatasearchhandler"></a>实现 IMetadataSearchHandler  
 将实现`Microsoft.ServiceModel.Channels.Common.IMetadataSearchHandler.Search%2A`方法`Microsoft.ServiceModel.Channels.Common.IMetadataSearchHandler`接口。 如果该操作的显示名称匹配搜索条件，则将创建`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`对于该操作，对象，然后将该对象添加到的数组`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`对象。  
  
#### <a name="to-update-the-echoadaptermetadatasearchhandler-class"></a>若要更新 EchoAdapterMetadataSearchHandler 类  
  
1.  在解决方案资源管理器中，双击**EchoAdapterMetadataSearchHandler.cs**文件。  
  
2.  在 Visual Studio 编辑器中，内部**搜索**方法，用以下代码替换现有的逻辑。 此逻辑创建`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`对象 Echo/OnReceiveEcho 是否与指定的搜索条件匹配。  
  
    ```csharp  
    List<MetadataRetrievalNode> resultList = new List<MetadataRetrievalNode>();  
    if ("OnReceiveEcho".ToLower().Contains(searchCriteria.ToLower()))  
    {  
        MetadataRetrievalNode nodeInbound = new MetadataRetrievalNode("Echo/OnReceiveEcho");  
        nodeInbound.DisplayName = "OnReceiveEcho";  
        nodeInbound.Description = "This operation echoes the location and length of a file dropped in the specified file system.";  
        nodeInbound.Direction = MetadataRetrievalNodeDirections.Inbound;  
        nodeInbound.IsOperation = true;  
        resultList.Add(nodeInbound);  
    }  
    ```  
  
3.  继续添加以下逻辑创建`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`对象 Echo/EchoStrings 是否与指定的搜索条件匹配。  
  
    ```csharp  
    if ("EchoStrings".ToLower().Contains(searchCriteria.ToLower()))  
    {  
        MetadataRetrievalNode outOpNode1 = new MetadataRetrievalNode("Echo/EchoStrings");  
        outOpNode1.DisplayName = "EchoStrings";  
        outOpNode1.Description = "This operation echoes the incoming string COUNT number of times in a string array.";  
        outOpNode1.Direction = MetadataRetrievalNodeDirections.Outbound;  
        outOpNode1.IsOperation = true;  
        resultList.Add(outOpNode1);  
    }  
    ```  
  
4.  继续添加以下逻辑创建`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`对象 Echo/EchoGreetings 是否与指定的搜索条件匹配。  
  
    ```csharp  
    if ("EchoGreetings".ToLower().Contains(searchCriteria.ToLower()))  
        {  
            MetadataRetrievalNode outOpNode2 = new MetadataRetrievalNode("Echo/EchoGreetings");  
            outOpNode2.DisplayName = "EchoGreetings";  
            outOpNode2.Description = "This operation echoes the incoming Greeting object COUNT number of times in an array of type Greeting.";  
            outOpNode2.Direction = MetadataRetrievalNodeDirections.Outbound;  
            outOpNode2.IsOperation = true;  
            resultList.Add(outOpNode2);  
        }  
    ```  
  
5.  继续添加以下代码以创建`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`对象 Echo/EchoGreetingFromFile 是否与指定的搜索条件匹配。  
  
    ```csharp  
    if ("EchoCustomGreetingFromFile".ToLower().Contains(searchCriteria.ToLower()))  
    {  
        MetadataRetrievalNode outOpNode3 = new MetadataRetrievalNode("Echo/EchoCustomGreetingFromFile");  
        outOpNode3.DisplayName = "EchoCustomGreetingFromFile";  
        outOpNode3.Description = "This operation echoes the greeting object by reading its instance from a file. The Greeting object's metadata is obtained from a predefined XSD file.";  
        outOpNode3.Direction = MetadataRetrievalNodeDirections.Outbound;  
        outOpNode3.IsOperation = true;  
        resultList.Add(outOpNode3);  
    }  
    ```  
  
6.  继续添加下面的代码返回的数组`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`对象。  
  
    ```csharp  
    return resultList.ToArray();  
    ```  
  
7.  在 Visual Studio 中，在**文件**菜单上，单击**保存所有**。  
  
8.  在“生成”  菜单上，单击“生成解决方案” 。 你应已成功编译项目。 如果没有，请确保您已按照上述每个步骤。  
  
    > [!NOTE]
    >  保存所做的工作。 你可以安全地在此时关闭 Visual Studio 或转到下一步，[步骤 6： 为 Echo 适配器实现的元数据解析处理程序](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-6-implement-the-metadata-resolve-handler-for-the-echo-adapter.md)。  
  
## <a name="what-did-i-just-do"></a>未我只需做什么？  
 只需实现搜索功能 Echo 适配器，通过实现的元数据`Microsoft.ServiceModel.Channels.Common.IMetadataSearchHandler.Search%2A`方法`Microsoft.ServiceModel.Channels.Common.IMetadataSearchHandler`接口。 具体而言，创建`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`对象的匹配条件，然后返回数组的每个操作`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`对象。  
  
## <a name="next-steps"></a>后续步骤  
 将实现解决功能和出站和入站消息 exchange 功能的元数据。 最后，将生成并部署 Echo 适配器。  
  
## <a name="see-also"></a>另请参阅  
 [步骤 4： 为 Echo 适配器实现元数据浏览的处理程序](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-4-implement-the-metadata-browse-handler-for-the-echo-adapter.md)   
 [步骤 6： 为 Echo 适配器实现的元数据解析处理程序](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-6-implement-the-metadata-resolve-handler-for-the-echo-adapter.md)   
 [教程 1： 开发 Echo 适配器](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md)