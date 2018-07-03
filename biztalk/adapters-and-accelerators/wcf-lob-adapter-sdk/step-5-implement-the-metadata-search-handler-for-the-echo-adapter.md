---
title: 步骤 5： 实现 Echo 适配器的元数据搜索处理程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1a133a99-1d6c-4634-b928-0f4f23c6f6e4
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 29768fa47fd26f32308d517f175d906ec088ff7b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004086"
---
# <a name="step-5-implement-the-metadata-search-handler-for-the-echo-adapter"></a>步骤 5： 实现 Echo 适配器的元数据搜索处理程序
![步骤 5 9](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-5of9.gif "Step_5of9")  
  
 **完成时间：** 30 分钟  
  
 在本教程的此步骤中，将实现 Echo 适配器的搜索功能。 与不同的浏览、 搜索是可选的。 根据[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]，若要支持搜索功能，必须实现`Microsoft.ServiceModel.Channels.Common.IMetadataSearchHandler`接口。 Echo 适配器[!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)]自动生成一个名为 EchoAdapterMetadataSearchHandler 的派生的类。  
  
 第一次更新 EchoAdapterMetadataSearchHandler 类，以获取更好地了解如何实现此接口，如何填充`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`对象，并且搜索结果中的显示方式[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]工具。  
  
## <a name="prerequisites"></a>必要條件  
 在开始此步骤之前，请完成[步骤 4： 实现 Echo 适配器的元数据浏览处理程序](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-4-implement-the-metadata-browse-handler-for-the-echo-adapter.md)。 您还必须清楚地了解有关以下类：  
  
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
  
 `Microsoft.ServiceModel.Channels.Common.IMetadataSearchHandler.Search%2A`方法返回的数组`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`对象根据搜索条件。 搜索方法的参数定义如下表所述：  
  
|**参数**|**定义**|  
|-------------------|--------------------|  
|nodeId|要从开始搜索的节点 ID。 如果为 null 或空字符串 ("")，将从根节点 （"/"） 检索操作。|  
|searchCriteria|搜索条件，这是特定于适配器的。 如果不指定了任何搜索条件，则适配器应返回所有节点。|  
|maxChildNodes|最大可返回的结果节点数。 使用 Int32.Max 检索所有结果节点。<br /><br /> 不支持 Echo 适配器。|  
|timeout|若要完成该操作允许的最大时间。<br /><br /> 不支持 Echo 适配器。|  
  
 搜索结果中，为您的适配器可以选择返回类别节点和/或操作节点。 将搜索功能的类型由您的适配器支持。  
  
## <a name="echo-adapter-metadata-search"></a>Echo 适配器的元数据搜索  
 根据目标系统的类别和操作，有许多种方法来生成一个数组`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`可以返回的对象。 Echo 适配器实现搜索功能的方法是通过使用其下面的列表中的节点 ID 的每个操作：  
  
```  
Echo/OnReceiveEcho, inbound operation  
Echo/EchoStrings, outbound operation  
Echo/EchoGreetings, outbound operation  
Echo/EchoGreetingFromFile, outbound operation  
```  
  
- 如果节点 ID 然后匹配搜索条件，它将创建`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`对象使用该操作的节点 ID，然后将具有值的属性。 例如，  
  
  ```  
  MetadataRetrievalNode nodeInbound = new MetadataRetrievalNode("Echo/OnReceiveEcho"); //create the MetadataRetrievalNode using the operation's node ID.  
  nodeInbound.DisplayName = "OnReceiveEcho"; //The Display Name shown in the Name column of the Add Adapter Service Reference Visual Studio Plug-in  
  nodeInbound.Description = "This operation echoes the location and length of a file dropped in the specified file system.";  //The Description shown as the tool tip in the Add Adapter Service Visual Studio Plug-in  
  nodeInbound.Direction = MetadataRetrievalNodeDirections.Inbound;    //It is an inbound operation  
  nodeInbound.IsOperation = true;  //It is an operation, not category.  
  ```  
  
- 然后将该对象添加到一系列`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`s，例如，  
  
  ```  
  resultList.Add(nodeInbound);  
  ```  
  
- 最后的数组格式返回的集合。  
  
  ```  
  return resultList.ToArray();  
  ```  
  
  可以使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]和[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]工具执行的搜索基于连接的可用操作。 例如下, 图显示的搜索条件时将字符串**问候**，搜索返回**EchoGreetings**并**EchoGreetingFromFile**操作。  
  
  ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/874c046a-590f-4047-9b9c-bb8074664755.gif "874c046a-590f-4047-9b9c-bb8074664755")  
  
  如果不找到任何匹配项，则这两个工具将返回在下图中显示的错误消息。  
  
  ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/cb1f79a2-a63d-4828-9dce-905c026cd1dc.gif "cb1f79a2-a63d-4828-9dce-905c026cd1dc")  
  
## <a name="implementing-the-imetadatasearchhandler"></a>实现 IMetadataSearchHandler  
 将实现`Microsoft.ServiceModel.Channels.Common.IMetadataSearchHandler.Search%2A`方法的`Microsoft.ServiceModel.Channels.Common.IMetadataSearchHandler`接口。 如果该操作显示名称与搜索条件匹配，则将创建`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`对象对于该操作，并将该对象添加到一个数组`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`对象。  
  
#### <a name="to-update-the-echoadaptermetadatasearchhandler-class"></a>若要更新 EchoAdapterMetadataSearchHandler 类  
  
1.  在解决方案资源管理器中双击**EchoAdapterMetadataSearchHandler.cs**文件。  
  
2.  在 Visual Studio 编辑器中，内部**搜索**方法，用以下代码替换现有的逻辑。 此逻辑将创建`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`对象 Echo/OnReceiveEcho 是否与指定的搜索条件匹配。  
  
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
  
6.  继续添加以下代码以返回一个数组`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`对象。  
  
    ```csharp  
    return resultList.ToArray();  
    ```  
  
7.  在 Visual Studio 中，在**文件**菜单上，单击**全部保存**。  
  
8.  在“生成”  菜单上，单击“生成解决方案” 。 您应已成功编译项目。 如果没有，请确保您已按照上述每个步骤。  
  
    > [!NOTE]
    >  保存所做的工作。 可以安全地关闭 Visual Studio 或转到下一步[步骤 6： 实现 Echo 适配器的元数据解析处理程序](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-6-implement-the-metadata-resolve-handler-for-the-echo-adapter.md)。  
  
## <a name="what-did-i-just-do"></a>我只需做了什么？  
 只需实现通过实现搜索功能的 Echo 适配器的元数据`Microsoft.ServiceModel.Channels.Common.IMetadataSearchHandler.Search%2A`方法的`Microsoft.ServiceModel.Channels.Common.IMetadataSearchHandler`接口。 具体而言，创建`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`对于每个操作与条件匹配，则返回一个数组对象`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`对象。  
  
## <a name="next-steps"></a>后续步骤  
 将实现解析功能和出站和入站消息的 exchange 功能的元数据。 最后，将生成并部署 Echo 适配器。  
  
## <a name="see-also"></a>请参阅  
 [步骤 4： 实现 Echo 适配器的元数据浏览处理程序](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-4-implement-the-metadata-browse-handler-for-the-echo-adapter.md)   
 [步骤 6： 实现 Echo 适配器的元数据解析处理程序](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-6-implement-the-metadata-resolve-handler-for-the-echo-adapter.md)   
 [教程 1：开发 Echo 适配器](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md)