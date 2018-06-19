---
title: 步骤 4： 为 Echo 适配器实现元数据浏览的处理程序 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d31fc6c1-e4b5-4529-ba3e-2a8cfb8ece1c
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f93b4efeb65092c4ca61ab1fc2ef58a0ac53ae4a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22226981"
---
# <a name="step-4-implement-the-metadata-browse-handler-for-the-echo-adapter"></a>步骤 4： 为 Echo 适配器实现元数据浏览的处理程序
![9 的第 4 步](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-4of9.gif "Step_4of9")  
  
 **完成时间：** 45 分钟  
  
 在此步骤中，你可以实现 Echo 适配器的浏览功能。 此功能允许您执行基于连接的浏览，获取元数据从目标系统的适配器。 无论你适配器的功能，你的适配器必须支持浏览功能。  
  
 根据[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]，若要支持浏览功能，则必须实现`Microsoft.ServiceModel.Channels.Common.IMetadataBrowseHandler`接口。 为 Echo 适配器[!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)]自动生成调用 EchoAdapterMetadataBrowseHandler 派生的类。  
  
 在以下步骤中，更新此类，以更好地理解如何实现`Microsoft.ServiceModel.Channels.Common.IMetadataBrowseHandler.Browse%2A`方法，如何设置的各种属性`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`对象，并在的操作和适配器支持的类别节点的显示方式[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]工具。  
  
## <a name="prerequisites"></a>先决条件  
 在开始此步骤之前，你必须已成功完成[步骤 3： 实现 Echo 适配器的连接](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-3-implement-the-connection-for-the-echo-adapter.md)。 您还必须了解以下类：  
  
-   `Microsoft.ServiceModel.Channels.MetadataRetrievalNode`  
  
-   `Microsoft.ServiceModel.Channels.MetadataRetrievalNodeDirections`  
  
-   `Microsoft.ServiceModel.Channels.Common.IMetadataBrowseHandler`  
  
## <a name="the-imetadatabrowsehandler-interface"></a>IMetadataBrowseHandler 接口  
 `Microsoft.ServiceModel.Channels.Common.IMetadataBrowseHandler`接口如下定义：  
  
```  
public interface IMetadataBrowseHandler : IConnectionHandler, IDisposable  
{  
    MetadataRetrievalNode[] Browse(string nodeId, int childStartIndex, int maxChildNodes, TimeSpan timeout);  
}  
```  
  
 `Microsoft.ServiceModel.Channels.Common.IMetadataBrowseHandler.Browse%2A`方法返回的数组`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`对象基于方法的参数。 参数定义`Microsoft.ServiceModel.Channels.Common.IMetadataBrowseHandler.Browse%2A`方法以下表所述。  
  
> [!NOTE]
>  Echo 适配器实现使用仅的节点 ID，并忽略其他三个参数，因为 Echo 适配器支持仅在几个节点。  
  
|**参数**|**定义**|  
|-------------------|--------------------|  
|nodeId|层次结构中的元数据资源管理器的每个项 ([!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]和<br /><br /> [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]) 具有 nodeId。 每个节点 ID 必须唯一，并且可以是一个类别或运算。 类别具有子类别。 **注意：** 如果 null 或空字符串 ("")，从根节点 （"/"） 默认情况下检索操作。|  
|childStartIndex|若要返回的第一个子级的索引。<br /><br /> 不支持 Echo 适配器。|  
|maxChildNodes|要返回的结果节点最大数量。 使用 Int32.Max 检索结果的所有节点。<br /><br /> 不支持 Echo 适配器。|  
|timeout|允许此操作完成的最大时间。<br /><br /> 不支持 Echo 适配器。|  
  
 在实现时`Microsoft.ServiceModel.Channels.Common.IMetadataBrowseHandler.Browse%2A`方法，必须将每个类别和操作的节点添加到的数组`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`对象。 若要指定的节点作为类别，设置`Microsoft.ServiceModel.Channels.MetadataRetrievalNode.IsOperation%2A`到`false`。 若要指定作为操作的节点，将设置`Microsoft.ServiceModel.Channels.MetadataRetrievalNode.IsOperation%2A`到`true`。  
  
## <a name="echo-adapter-metadata-browse"></a>Echo 适配器元数据浏览  
 根据目标系统的类别和操作中，有许多方法来生成的数组`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`对象。 操作和你选择的类别应表示你想要公开的操作。 但对于 Echo 适配器，它只需创建`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`对象具有节点 ID 的以下节点的每个列出：  
  
```  
EchoMainCategory  (node under the root node)  
        Echo/EchoStrings   (outbound operation)  
        Echo/EchoGreetings(outbound operation)  
        Echo/EchoCustomGreetingFromFile(outbound operation)  
        Echo/OnReceiveEcho (inbound operation)  
```  
  
 EchoMainCategory 是根节点 （"/"） 下的类别节点。 此节点还作为类别用于入站和出站操作。 因此，在创建时`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`对象该类别中，你可以执行以下操作：  
  
```  
MetadataRetrievalNode node = new MetadataRetrievalNode("EchoMainCategory");  
node.IsOperation = false; //category  
node.Direction = MetadataRetrievalNodeDirections.Inbound | MetadataRetrievalNodeDirections.Outbound  //for both inbound and outbound  
```  
  
 对于如属于 EchoMainCategory/Echo EchoString 出站操作，可以执行以下操作：  
  
```  
if( "EchoMainCategory".CompareTo(nodeId) == 0 ) //category is EchoMainCategory  
      {  
          // Outbound operations  
          MetadataRetrievalNode outOpNode1 = new MetadataRetrievalNode("Echo/EchoStrings");  
          outOpNode1.DisplayName = "EchoStrings";  
          outOpNode1.Description = "This operation echoes the incoming string COUNT number of times in a string array.";  
          outOpNode1.Direction = MetadataRetrievalNodeDirections.Outbound;  
          outOpNode1.IsOperation = true;  
```  
  
 对于入站回显/OnReceiveEcho 属于 EchoMainCategory 如操作，可以执行以下操作：  
  
```  
  if( "EchoMainCategory".CompareTo(nodeId) == 0 ) //category is EchoMainCategory  
        {             
// Inbound operations  
            MetadataRetrievalNode inOpNode1 = new MetadataRetrievalNode("Echo/OnReceiveEcho");  
            inOpNode1.DisplayName = "OnReceiveEcho";  
            inOpNode1.Description = "This operation echoes the location and length of a file dropped in the specified file system.";  
            inOpNode1.Direction = MetadataRetrievalNodeDirections.Inbound;  
            inOpNode1.IsOperation = true;  
```  
  
 当[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]和[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]工具浏览 Echo 适配器元数据，默认情况下，它将启动从根节点 （"/"）。  
  
 下图显示 EchoMainCategory 节点显示在根节点 （"/"）：  
  
 ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/e4b9d0b8-f07f-4342-815f-9ef1507b0980.gif "e4b9d0b8-f07f-4342-815f-9ef1507b0980")  
  
 浏览中的三个出站操作，[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]工具，在**选择协定类型**下拉列表中，选择**客户端 （出站操作）** 选项。 请参阅中的这些操作**可用类别和操作**列表框中，如下所示：  
  
 ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/c8755805-cbb0-40f1-887a-a3123f71ae7e.gif "c8755805-cbb0-40f1-887a-a3123f71ae7e")  
  
 在上图中，注意`Microsoft.ServiceModel.Channels.MetadataRetrievalNode.DisplayName%2A`值出现在**名称**列**可用类别和操作**列表框。 参数传递到`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`构造函数将出现在**节点 ID**列**可用类别和操作**列表框中，与`Microsoft.ServiceModel.Channels.MetadataRetrievalNode.Description%2A`值会显示为工具提示包含说明中，右键单击时`Microsoft.ServiceModel.Channels.MetadataRetrievalNode.DisplayName%2A`。  
  
 若要查看的入站的操作，在[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]工具，在**选择协定类型**下拉列表中，选择**服务 （入站操作）** 选项。 请参阅中的入站的 OnReceiveEcho 操作**可用类别和操作**列表框中下, 图中所示：  
  
 ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/26b7b3c7-bc39-46f8-bc73-7d76fd3c02eb.gif "26b7b3c7-bc39-46f8-bc73-7d76fd3c02eb")  
  
## <a name="implementing-the-imetadatabrowsehandler"></a>实现 IMetadataBrowseHandler  
 在此步骤中，更新 EchoAdapterMetadataBrowseHandler 类，它是实现 Echo 适配器的元数据浏览，以实现`Microsoft.ServiceModel.Channels.Common.IMetadataBrowseHandler.Browse%2A`方法`Microsoft.ServiceModel.Channels.Common.IMetadataBrowseHandler`接口。 具体而言，创建`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`每个类别和操作对象，设置适当的值为该对象，然后返回的数组`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`类别和操作的对象。 请记住，当你创建`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`对象，你需要传入的节点 ID，而不是显示名称。  
  
#### <a name="to-update-the-echoadaptermetadatabrowsehandler-class"></a>若要更新 EchoAdapterMetadataBrowseHandler 类  
  
1.  在解决方案资源管理器中，双击**EchoAdapterMetadataBrowseHandler.cs**文件。  
  
2.  在 Visual Studio 编辑器中，右键单击任意位置在编辑器中，在上下文菜单中，依次指向**大纲**，然后单击**停止大纲显示**。  
  
3.  在 Visual Studio 编辑器中，内部**浏览**方法，将替换为以下创建的现有逻辑`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`EchoMainCategory 的对象。  
  
    ```csharp  
    if (MetadataRetrievalNode.Root.NodeId.Equals(nodeId))  
    {  
        MetadataRetrievalNode node = new MetadataRetrievalNode("EchoMainCategory");  
        node.DisplayName = "Main Category";  
        node.IsOperation = false;  
        node.Description = "This category contains inbound and outbound categories.";  
        node.Direction = MetadataRetrievalNodeDirections.Inbound | MetadataRetrievalNodeDirections.Outbound;  
        return new MetadataRetrievalNode[] { node };  
    }  
    ```  
  
4.  继续添加以下逻辑创建`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`Echo/OnReceiveEcho 的对象。  
  
    ```csharp  
    if( "EchoMainCategory".CompareTo(nodeId) == 0 )  
    {  
        // Inbound operations  
        MetadataRetrievalNode inOpNode1 = new MetadataRetrievalNode("Echo/OnReceiveEcho");  
        inOpNode1.DisplayName = "OnReceiveEcho";  
        inOpNode1.Description = "This operation echos the location and length of a file dropped in the specified file system.";  
        inOpNode1.Direction = MetadataRetrievalNodeDirections.Inbound;  
        inOpNode1.IsOperation = true;  
    ```  
  
5.  继续添加以下逻辑创建`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`Echo/EchoStrings 的对象。  
  
    ```csharp  
    // Outbound operations  
    MetadataRetrievalNode outOpNode1 = new MetadataRetrievalNode("Echo/EchoStrings");  
    outOpNode1.DisplayName = "EchoStrings";  
    outOpNode1.Description = "This operation echoes the incoming string COUNT number of times in a string array.";  
    outOpNode1.Direction = MetadataRetrievalNodeDirections.Outbound;  
    outOpNode1.IsOperation = true;  
    ```  
  
6.  继续添加以下代码以创建`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`Echo/EchoGreetings 的对象。  
  
    ```csharp  
    MetadataRetrievalNode outOpNode2 = new MetadataRetrievalNode("Echo/EchoGreetings");  
    outOpNode2.DisplayName = "EchoGreetings";  
    outOpNode2.Description = "This operation echoes the incoming Greeting object COUNT number of times in an array of type Greeting.";  
    outOpNode2.Direction = MetadataRetrievalNodeDirections.Outbound;  
    outOpNode2.IsOperation = true;  
    ```  
  
7.  继续添加以下代码以创建`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`回显的对象 / EchoGreetingFromFile。  
  
    ```csharp  
    MetadataRetrievalNode outOpNode3 = new MetadataRetrievalNode("Echo/EchoCustomGreetingFromFile");  
    outOpNode3.DisplayName = "EchoCustomGreetingFromFile";  
    outOpNode3.Description = "This operation echoes the greeting object by reading its instance from a file. The Greeting object's metadata is obtained from a predefined XSD file.";  
    outOpNode3.Direction = MetadataRetrievalNodeDirections.Outbound;  
    outOpNode3.IsOperation = true;  
    ```  
  
8.  继续添加下面的代码返回的数组`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`对象或 null 如果不匹配。  
  
    ```  
        return new MetadataRetrievalNode[] { inOpNode1, outOpNode1, outOpNode2, outOpNode3 };  
    }  
    return null;  
    ```  
  
9. 在 Visual Studio 中，在**文件**菜单上，单击**保存所有**。  
  
10. 在“生成”  菜单上，单击“生成解决方案” 。 你应已成功生成项目。 如果没有，请确保您已按照上述每个步骤。  
  
> [!NOTE]
>  保存所做的工作。 你可以安全地在此时关闭 Visual Studio 或转到下一步，[步骤 5： 为 Echo 适配器实现的元数据搜索处理程序](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-5-implement-the-metadata-search-handler-for-the-echo-adapter.md)。  
  
## <a name="what-did-i-just-do"></a>未我只需做什么？  
 只需实现通过实现浏览 Echo 适配器，适配器的功能的元数据`Microsoft.ServiceModel.Channels.Common.IMetadataBrowseHandler.Browse%2A`方法`Microsoft.ServiceModel.Channels.Common.IMetadataBrowseHandler`接口。 具体而言，创建`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`针对类别中，对象，然后将它返回数组的形式`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`对象。 您为每个操作，创建`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`对象，以及然后在一个数组中返回所有这些对象`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`。  
  
## <a name="next-steps"></a>后续步骤  
 你可实现元数据搜索和解析功能和出站消息交换。 最后，生成并部署 Echo 适配器。  
  
## <a name="see-also"></a>另请参阅  
 [教程 1： 开发 Echo 适配器](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md)   
 [步骤 3： 实现 Echo 适配器的连接](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-3-implement-the-connection-for-the-echo-adapter.md)   
 [步骤 5： 为 Echo 适配器实现的元数据搜索处理程序](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-5-implement-the-metadata-search-handler-for-the-echo-adapter.md)