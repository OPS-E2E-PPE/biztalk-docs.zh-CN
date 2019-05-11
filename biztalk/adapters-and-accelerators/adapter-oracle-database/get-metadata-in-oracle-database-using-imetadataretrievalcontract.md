---
title: 在 Oracle 数据库中使用 IMetadataRetrievalContract 获取元数据 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- metadata, retrieving using IMetadataRetrievalContract
ms.assetid: 7d32694f-4384-4c2f-be72-ac52c7b2e9f5
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 679a1be842b27431669e60089143c1972aaa0693
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65376568"
---
# <a name="get-metadata-in-oracle-database-using-imetadataretrievalcontract"></a>在 Oracle 数据库中使用 IMetadataRetrievalContract 获取元数据
[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]公开**IMetadataRetrievalContract**，可以使用浏览和搜索 Oracle 数据库项目并检索窗体的 Web 服务描述语言 (WSDL 中的操作的元数据终结点) 文档。  
  
 **IMetadataRetrievalContract**接口由实现[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]，并提供元数据浏览、 搜索和检索功能。 除了**IMetadataRetrievalContract**接口，[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]公开**MetadataRetrievalClient**类，该类实现接口。 你可以使用**IMetadataRetrievalContract**通道或**MetadataRetrievalClient**以使用元数据; 浏览、 搜索和检索元数据公开的方法是相同的每种情况下。  
  
 以下部分提供有关如何使用信息**IMetadataRetrievalContract**接口。  
  
## <a name="the-imetadataretrievalcontract-interface"></a>IMetadataRetrievalContract 接口  
 下表提供了有关在使用时使用的重要类的信息**IMetadataRetrievalContract**接口。  
  
|类或接口|Description|  
|------------------------|-----------------|  
|**IMetadataRetrievalContract**接口<br /><br /> (Microsoft.ServiceModel.Channels)|定义**浏览**，**搜索**，并**GetMetadata**方法。 调用这些方法是通过**IMetadataRetrievalContract**通道或**MetadataRetrievalClient**若要使用的适配器元数据。|  
|**MetadataRetrievalClient**类<br /><br /> (Microsoft.ServiceModel.Channels)|实现**IMetadataRetrievalContract**接口。 您可以创建此类的实例并将其用于 Oracle 数据库配置，从而**OracleDBBinding**和一个**EndpointAddress**。 然后可以调用其方法来处理的元数据。|  
|**MetadataRetrievalNode**类<br /><br /> (Microsoft.ServiceModel.Channels)|表示在适配器上的元数据节点。 **浏览**并**搜索**方法将返回此类型的节点和**GetMetadata**方法采用一个参数为此类型的节点。|  
|**ServiceDescription**类<br /><br /> (System.Web.Services.Description)|提供了一种创建和格式设置的有效的 WSDL 文档文件。 **GetMetadata**方法将返回**ServiceDescription**对象。|  
  
 
### <a name="metadata-node-ids"></a>元数据节点 Id  
 该适配器将其元数据组织为层次结构树的节点。 在此树结构中，有两种类型的元数据节点：  
  
- **操作节点**表示，它会将适配器显示在 Oracle 数据库项目上的操作。 操作节点均为树的叶。  
  
- **类别节点**表示 Oracle 数据库项目并不直接对应的 Oracle 数据库项目的分组到在适配器上的操作。 类别节点是树的分支它们包含其他类别节点和/或操作节点。 例如，Oracle 表和包表示为类别节点。  
  
  适配器提供的每个元数据节点标识的唯一节点 id。 有关元数据节点 Id 适配器提供的详细信息，请参阅[元数据节点 Id](../../adapters-and-accelerators/adapter-oracle-database/metadata-node-ids3.md)。 使用这些节点 Id 来指定目标 Oracle 数据库项目时使用**IMetadataRetrievalContract**接口以浏览、 搜索和检索元数据。  
  
### <a name="binding-properties"></a>绑定属性  
 无论是使用**IMetadataRetrievalContract**通道或**IMetadataRetrievalClient**若要使用的元数据，必须指定**OracleDBBinding**时您创建该实例。  
  
 有几个影响适配器如何生成元数据的绑定属性。 这些属性包括：  
  
-   **EnableSafeTyping**  
  
-   **UseSchemaInNamespace**  
  
-   **PollingStatement**  
  
> [!IMPORTANT]
>  如果你想要检索 POLLINGSTMT 操作的元数据必须设置**PollingStatement**属性绑定。  
  
 应确保这些绑定属性设置为所需的应用程序之前打开元数据检索对象的值。 有关详细信息[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]绑定属性，请参阅[阅读有关 Oracle 数据库适配器绑定属性](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md)。  
  
### <a name="browsing-metadata-nodes"></a>浏览元数据节点  
 您使用**浏览**方法以返回所包含的所有元数据节点中的父节点。 对于对 Oracle 数据库的前三个架构浏览下面的示例。 在此示例中，**客户端**的一个实例**MetadataRetrievalClient**。  
  
```  
// The first parameter is the node ID.   
// The second parameter is the start index.  
// The third parameter is the maximum number of nodes to return.  
                MetadataRetrievalNode[] nodes = client.Browse(MetadataRetrievalNode.Root.NodeId, 0, 3);  
```  
  
> [!IMPORTANT]
>  您只能浏览类别节点，则无法浏览操作节点。  
  
### <a name="searching-for-metadata-nodes"></a>搜索元数据节点  
 您使用**搜索**方法来执行所包含的父节点的节点的搜索。 适配器支持通配符搜索表达式; 中例如，您可以指定百分比 （%）要匹配零个或多个字符的通配符字符。 下面的示例显示包含字符串"EMP"SCOTT 架构中的所有表的搜索。 在此示例中，**客户端**的一个实例**MetadataRetrievalClient**。  
  
```  
// Search for all nodes that contain "EMP" under the SCOTT.Table node.  
// The parameters are the parent node ID, the search expression, and   
// the maximum number of nodes to return.  
IMetadataRetrievalNode[] nodes = client.Search("http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table", "%EMP%", 3);  
  
```  
  
> [!IMPORTANT]
>  仅支持有限的一组节点上进行搜索。 有关在其支持搜索的节点以及搜索表达式中支持的通配符字符的详细信息，请参阅[元数据节点 Id](../../adapters-and-accelerators/adapter-oracle-database/metadata-node-ids3.md)。  
  
### <a name="retrieving-metadata-wsdl-for-operations"></a>检索操作的元数据 (WSDL)  
 您使用**GetMetadata**方法来检索服务说明 （WSDL 文档） 的一组的操作节点。 下面的示例检索包含所有适配器显示为 SCOTT 的操作的服务说明。EMP 表通过指定其节点 id。 在此示例中，**客户端**的一个实例**MetadataRetrievalClient**。  
  
```  
// Get a service description that contains all of the operations   
// surfaced for the SCOTT.EMP table. The IsOperation  
// property is set false because this is a category node.  
nodes = new MetadataRetrievalNode[1];  
nodes[0] = new MetadataRetrievalNode();  
nodes[0].NodeId = "http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP";  
nodes[0].IsOperation = false;  
System.Web.Services.Description.ServiceDescription description = client.GetMetadata(nodes);  
  
```  
  
> [!IMPORTANT]
>  **IsOperation**属性应为 false 的类别节点和操作节点为 true。  
  
### <a name="using-a-metadataretrievalclient"></a>使用 MetadataRetrievalClient  
 创建和使用**MetadataRetrievalClient**是任何其他 WCF 客户端，大致相同。 通过指定终结点和的实例创建客户端**OracleDBBinding**。 可以以声明方式在配置中或在代码中以强制方式执行此操作。 然后，可以调用的方法**MetadataRetrievalClient**浏览、 搜索和检索来自适配器的元数据。  
  
 下面的示例演示如何使用**MetadataRetrievalClient**以浏览、 搜索和检索元数据从[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。 此示例演示：  
  
-   浏览 Oracle 数据库架构的元数据树的根节点。  
  
-   搜索名称包含字符串"EMP"SCOTT 架构中的表。  
  
-   检索所有支持的 SCOTT 操作的元数据。通过将传递到类别节点的 EMP 表**GetMetadata**方法。  
  
-   通过传递到 POLLINGSTMT 操作节点检索 POLLINGSTMT 操作元数据**GetMetadata**方法...  
  
```  
using System;  
using System.Collections.Generic;  
using System.Text;  
  
using System.ServiceModel;  
using Microsoft.Adapters.OracleDB;  
using Microsoft.ServiceModel.Channels;  
  
using System.Web.Services.Description;  
  
namespace OracleMetadataRetrieval  
{  
    class NodeWriter  
    {  
        // This method writes the value of a collection of metadata retrieval nodes  
        // to the console  
        public void Write(string title, MetadataRetrievalNode[] nodes)  
        {  
            Console.WriteLine(title);  
            Console.WriteLine();  
  
            //write all the nodes returned to the console.  
            foreach (MetadataRetrievalNode node in nodes)  
            {  
                Console.WriteLine("NodeId = " + node.NodeId);  
                Console.WriteLine("\tDirection   = " + node.Direction.ToString());  
                Console.WriteLine("\tIsOperation = " + node.IsOperation.ToString());  
                Console.WriteLine("\tDisplayName = " + node.DisplayName);  
                Console.WriteLine("\tDescription = " + node.Description);  
            }  
            Console.WriteLine();  
        }  
    }  
  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            MetadataRetrievalClient client = null;  
            NodeWriter nodeWriter = new NodeWriter();  
  
            try  
            {  
                // create a binding and   
                // set the PollingStatement binding property if you want to  
                // return metadata for the POLLINGSTMT operation  
                OracleDBBinding binding = new OracleDBBinding();  
                binding.PollingStatement = "SELECT * FROM EMP";  
  
                // Set PollingId parameter if you want to alter the namespace of the POLLINGSTMT operation  
                EndpointAddress address = new EndpointAddress("oracledb://ADAPTER?PollingId=1");  
  
                client = new MetadataRetrievalClient(binding, address);  
                client.ClientCredentials.UserName.UserName = "SCOTT";  
                client.ClientCredentials.UserName.Password = "TIGER";  
                client.Open();  
  
                // Browse for the first 3 (schema) nodes directly under the root  
                // The parameters are the parent Node ID, the start index, and the maximum number  
                // of nodes to return  
                MetadataRetrievalNode[] nodes = client.Browse(MetadataRetrievalNode.Root.NodeId, 0, 3);  
                nodeWriter.Write("Browse results for the root node:", nodes);  
  
                // Search for first 3 tables that contain "EMP" in the SCOTT schema  
                // The parameters are the parent node ID, the search expression, and the maximum number  
                // of nodes to return  
                nodes = client.Search("http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table", "%EMP%", 3);  
                nodeWriter.Write(String.Format("Search results for \"%EMP%\" under {0} node:", "http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table"), nodes);  
  
                // Get a WSDL document that specifies a contract that contains the operations  
                // surfaced for the SCOTT.EMP table. The IsOperation property is set false  
                // because this is a category node.  
                nodes = new MetadataRetrievalNode[1];  
                nodes[0] = new MetadataRetrievalNode();  
                nodes[0].NodeId = "http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP";  
                nodes[0].IsOperation = false;  
                System.Web.Services.Description.ServiceDescription description = client.GetMetadata(nodes);  
                description.Write("EmpTableContract.wsdl");  
  
                // Get a WSDL document that specifies a contract that contains the   
                // the POLLINGSTMT operation. The IsOperation property is set true  
                // because this is an operation node.  
                // Note that the operation NodeId is equivalent to the message action.  
                nodes = new MetadataRetrievalNode[1];  
                nodes[0] = new MetadataRetrievalNode();  
                nodes[0].NodeId = "http://Microsoft.LobServices.OracleDB/2007/03/POLLINGSTMT";  
                nodes[0].IsOperation = true;  
                description = client.GetMetadata(nodes);  
                description.Write("PollingContract.wsdl");  
  
            }  
            catch (Exception ex)  
            {  
                Console.WriteLine("Exception is: " + ex.Message);  
            }  
            finally  
            {  
                if (client != null)  
                {  
                    if (client.State == CommunicationState.Opened)  
                        client.Close();  
                    else  
                        client.Abort();  
                }  
            }  
        }  
    }  
}  
```  
  
 下图显示在控制台上该程序的输出。 可以看到每个方法返回的元数据检索节点的结构。 该程序还将两个 WSDL 文档写入到文件。  
  
```  
Browse results for the root node:  
  
NodeId = http://Microsoft.LobServices.OracleDB/2007/03/ADAPTERTEST  
        Direction   = Outbound  
        IsOperation = False  
        DisplayName = ADAPTERTEST  
        Description = Owned By ADAPTERTEST  
NodeId = http://Microsoft.LobServices.OracleDB/2007/03/ADAPTEST  
        Direction   = Outbound  
        IsOperation = False  
        DisplayName = ADAPTEST  
        Description = Owned By ADAPTEST  
NodeId = http://Microsoft.LobServices.OracleDB/2007/03/ADMIN123  
        Direction   = Outbound  
        IsOperation = False  
        DisplayName = ADMIN123  
        Description = Owned By ADMIN123  
  
Search results for "%EMP%" under http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table node:  
  
NodeId = http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/AEMP  
        Direction   = Outbound  
        IsOperation = False  
        DisplayName = AEMP  
        Description = Table.AEMP  
NodeId = http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP  
        Direction   = Outbound  
        IsOperation = False  
        DisplayName = EMP  
        Description = Table.EMP  
NodeId = http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP1  
        Direction   = Outbound  
        IsOperation = False  
        DisplayName = EMP1  
        Description = Table.EMP1  
```  
  
## <a name="using-an-imetadataretrievalcontract-channel"></a>使用 IMetadataRetrievalContract 通道  
 此外可以创建**IMetadataRetrievalContract**通道，然后使用此通道来浏览、 搜索和检索来自适配器的元数据。 (方法签名均为适用于**MetadataRetrievalClient**类。)下面的示例演示如何执行此操作。  
  
```  
…  
//Create a binding and endpoint address.  
OracleDBBinding binding = new OracleDBBinding();  
EndpointAddress address = new EndpointAddress("oracledb://ADAPTER/");  
  
//Create and open a channel factory that will return an IMetadataRetrievalContract object, on which browse, search, and get can be performed.  
ChannelFactory<IMetadataRetrievalContract> factory = new ChannelFactory<IMetadataRetrievalContract>(binding, address);  
factory.Credentials.UserName.UserName = "SCOTT";  
factory.Credentials.UserName.Password = "TIGER";  
factory.Open();  
  
//Obtain an IMetadataRetrievalContract channel from the factory.  
IMetadataRetrievalContract channel = factory.CreateChannel();  
  
//Perform a search using the channel.  
MetadataRetrievalNode[] nodes = channel.Search("http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table", "%EMP%", int.MaxValue);  
…  
```  
  
## <a name="see-also"></a>请参阅  
 [从 Oracle 数据库中以编程方式获取元数据](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-programmatically-from-the-oracle-database.md)